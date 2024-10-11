# 4.1 Upgrade Guide

{% hint style="danger" %}
**Make sure you upgrade your license file**

If you are an existing Gravitee Enterprise customer upgrading to 4.x, please make sure that you upgrade your Gravitee license file. Reach out to your Customer Success Manager or Support team in order to receive a new 4.x license.
{% endhint %}

## Overview

Upgrading to APIM 4.1 is deployment-specific. The 4.0 breaking changes cited below must be noted and/or adopted for a successful upgrade.

{% hint style="warning" %}
* **If your upgrade will skip versions:** Read the version-specific upgrade notes for each intermediate version. You may be required to perform manual actions as part of the upgrade.
* **Run scripts on the correct database:** `gravitee` is not always the default database. Run `show dbs` to return your database name.
* **Ensure that you are aware of the breaking changes and deprecated functionality:** For more information about the breaking changes and deprecated functionality, see [Breaking changes and deprecated functionality for API Management](https://documentation.gravitee.io/apim/getting-started/upgrading-gravitee-api-management/breaking-changes-and-deprecated-functionality).
{% endhint %}

## EE plugins

* Starting with APIM 4.0, particular plugins are only available to enterprise customers. [See Gravitee APIM Enterprise Edition](../../overview/ee-vs-oss/) for additional information.

## Running APIM

* APIM now requires a minimum of JDK 17.
* Starting with 4.0.0, there will no longer be enterprise tags (i.e. suffixed by `-ee`).
* Cluster managers are now available as plugins. Therefore, Hazelcast Cluster Manager has been removed from the default distribution.
* TLS 1.0 and TLS 1.1 protocols are disabled by default. You can still enable these protocols with the proper TCP SSL configuration of the Gateway:

{% code title="gravitee.yaml" %}
```yaml
http:
  ssl:
    tlsProtocols: TLSv1.0, TLSv1.1, TLSv1.2
```
{% endcode %}

or using environment variables:

```bash
GRAVITEE_HTTP_SSL_TLSPROTOCOLS=TLSv1.0,TLSv1.1,TLSv1.2
```

## **Monitoring APIM**

* The name of the sync probe has been changed from `api-sync` to `sync-process` to make it explicit when all sync processes have been completed.
* The content of the sync handler has changed slightly to align with new concepts:
  * `initialDone`: `true` if the first initial synchronization is done
  * `counter`: The number of iterations
  * `nextSyncTime`: Time of the next synchronization
  * `lastOnError`: The latest synchronization with an error
  * `lastErrorMessage`: If `lastOnError` is `true`, the content of the error message
  * `totalOnErrors`: The number of iterations with an error
* v4 APIs currently only support the ElasticSearch reporter. If any other reporter is configured at the Gateway level, each v4 API call will produce an error log.
  * When using a different reporter, it remains possible to disable analytics on a per-API basis to avoid generating error logs for v4 APIs.

## **Managing APIs**

*   The endpoint configuration is now split into:

    * A shared configuration that can be used at the group level
    * A configuration dedicated to the endpoint that can override the shared configuration.&#x20;

    Existing v4 APIs need to be updated and reconfigured accordingly.
* An unused and outdated feature regarding file synchronization known as `localregistry` has been removed.
* Subscriptions with `type: SUBSCRIPTION` have been renamed to `type: PUSH`. Plans have a new field called `mode` that is `STANDARD` by default but needs to be `PUSH` for all Push plans.
  * A [mongo script](https://github.com/gravitee-io/gravitee-api-management/tree/master/gravitee-apim-repository/gravitee-apim-repository-mongodb/src/main/resources/scripts/4.0.0) is available to migrate the data in MongoDB.
* Jupiter mode has been replaced with the v4 emulation engine:
  * `jupiterModeEnabled` configuration has been removed and can no longer be disabled.
  * By default, any v2 API created or imported will emulate V4 Engine.
  * All new requests will use the new `HttpProtocolVerticle` introduced with the V4 engine. The old `ReactorVerticle` has been removed.
  * The default timeout is set to 30s for any request.
*   Security policies such as Keyless, ApiKey, JWT, and Oauth2 have been updated to return a simple Unauthorized message in case of an error. No additional details are provided to protect against a potential attacker. **This impacts both v2 and v4 APIs.** Error keys remain available for error templating. Here is a list of error keys by policy:

    **ApiKey**

    * API\_KEY\_MISSING
    * API\_KEY\_INVALID
    * JWT
      * JWT\_MISSING\_TOKEN
      * JWT\_INVALID\_TOKEN

    **Oauth2**

    * OAUTH2\_MISSING\_SERVER
    * OAUTH2\_MISSING\_HEADER
    * OAUTH2\_MISSING\_ACCESS\_TOKEN
    * OAUTH2\_INVALID\_ACCESS\_TOKEN
    * OAUTH2\_INVALID\_SERVER\_RESPONSE
    * OAUTH2\_INSUFFICIENT\_SCOPE
    * OAUTH2\_SERVER\_UNAVAILABLE
*   Plan selection has been changed to reflect the actual security applied on the API:

    **Keyless**

    * Will ignore any type of security (API key, Bearer token, etc.).
    * **If another plan has detected a security token, valid or invalid, all flows assigned to the Keyless plan will be ignored.**

    **API Key**

    * Retrieve the API key from the request header or query parameters (default header: `X-Gravitee-Api-Key` and default query parameter: `api-key`).
    * While it was previously ignored, **an empty API key is now considered invalid**.

    **JWT**

    * Retrieve JWT from `Authorization` header or query parameters.
    * Ignore empty `Authorization` header or any type other than Bearer.
    * While it was previously ignored, **an empty Bearer token is now considered invalid**.

    **OAuth2**

    * Retrieve OAuth2 from `Authorization` header or query parameters.
    * Ignore empty `Authorization` header or any type other than Bearer.
    * While it was previously ignored, **an empty Bearer token is now considered invalid**.
* Plugins are now overridden when duplicates (id/type) are found. The plugin zip file with the most recent modified time is kept and others are ignored. Notably, this allows `additionalPlugins` for Helm chart-based deployment to operate efficiently without the need to remove bundled plugins.
* The v4 API definition now expects a `FlowExecution` object instead of a `FlowMode` enumeration.
* The Gravitee Expression Language (EL) syntax to access custom API properties has changed from `{#properties}` to `{#api.properties}`.
* The `Endpoint` schema is now split into two schemas and the `Endpoint` object contains two string fields to manage both the configuration specific to the endpoint and the configuration that may be overridden from the `EndpointGroup`.
* Endpoint name and endpoint group name must be unique.
*   Analytics have been introduced and the old logging configuration has been moved. **For v4 APIs only**, a new `Analytics` object is available on the API allowing you to configure all aspects of analytics:

    ```json
    "analytics": {
      "enabled" : true|false,
      "logging": { ... },
      "messageSampling" : { ... }
    }
    ```
* The Webhook subscription configuration structure has changed.
* `ApiType` enumeration has been renamed: `SYNC` becomes `PROXY` and `ASYNC` becomes `MESSAGE`). v4 APIs and PUBLISH\_API events related to V4 APIs with old values may prevent the service to start properly. **The following script migrates data for MongoDB:**

```
print('Rename ApiType from SYNC & ASYNC to PROXY & MESSAGE');
// Override this variable if you use prefix
const prefix = "";

let apisCollection = db.getCollection(`${prefix}apis`);
apisCollection.find({"definitionVersion": "V4"}).forEach((api) => {
	if (api.type == "SYNC") {
		api.definition = api.definition.replace('"type" : "sync"', '"type" : "proxy"');
		api.type = "PROXY";
        	apisCollection.replaceOne({ _id: api._id }, api);
	}
	if (api.type == "ASYNC") {
		api.definition = api.definition.replace('"type" : "async"', '"type" : "message"');
		api.type = "MESSAGE";
	        apisCollection.replaceOne({ _id: api._id }, api);
	}
});


let eventsCollection = db.getCollection(`${prefix}events`);
eventsCollection.find({"type": "PUBLISH_API"}).forEach((event) => {

       event.payload = event.payload.replace('\\"type\\" : \\"sync\\"', '\\"type\\" : \\"proxy\\"');
       event.payload = event.payload.replace('\\"type\\" : \\"async\\"', '\\"type\\" : \\"message\\"');
	event.payload = event.payload.replace('"type" : "sync"', '"type" : "proxy"');
	event.payload = event.payload.replace('"type" : "async"', '"type" : "message"');
		
       eventsCollection.replaceOne({ _id: event._id }, event);
});
```

## Introduction of USER_TOKEN Permission for Token Management

Starting with version 4.1.26, there is a new permission called USER_TOKEN. This permission controls which users have the ability to read, create, update, and delete user tokens.

Previously, these actions were governed by the broader 'USER' permission. As part of the migration from version 4.1.25 to 4.1.26, no breaking changes have been introduced. Users who previously had the permission to manage user tokens under the 'USER' permission will retain their access automatically.

However, this new 'USER_TOKEN' permission gives administrators more granular control. They can now selectively determine which users truly need access to manage user tokens, allowing for better security and role-based management within the system.
