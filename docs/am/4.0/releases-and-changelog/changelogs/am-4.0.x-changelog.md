---
description: >-
  This page contains the changelog entries for AM 4.0.x and any future minor or
  patch AM 4.0.x releases
---

# AM 4.0.x

## Gravitee Access Management 4.0.9 - January 24, 2024



<details>
<summary>Bug fixes</summary>







</details>


## Gravitee Access Management 4.0.8 - January 19, 2024

<details>
<summary>Bug fixes</summary>

**Gateway**

* Avoid BodyHandler processing for GET request [#9352](https://github.com/gravitee-io/issues/issues/9352)
* WebAuthnCredentialId is null into the EL context [#9455](https://github.com/gravitee-io/issues/issues/9455)

</details>


## Gravitee Access Management 4.0.7 - December 22, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Session expired problem - X-XRF-TOKEN [#9398](https://github.com/gravitee-io/issues/issues/9398)
* 500 response received on creating user with /scim endpoint with duplicate externalId [#9421](https://github.com/gravitee-io/issues/issues/9421)
* Exclude null value from SCIM UserMapper [#9427](https://github.com/gravitee-io/issues/issues/9427)

**Management API**

* Unable to list users [#9125](https://github.com/gravitee-io/issues/issues/9125)

</details>

## Gravitee Access Management 4.0.6 - December 11, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Excessive number of ExpiredJWTException errors in Gravitee logs [#9261](https://github.com/gravitee-io/issues/issues/9261)
* Original Parameters lost during redirect using SAML Handler [#9393](https://github.com/gravitee-io/issues/issues/9393)
* Avoid logging GeoIP error stackstrace [#9401](https://github.com/gravitee-io/issues/issues/9401)

**Other**

* Invalid value in Issuer for Response [#9409](https://github.com/gravitee-io/issues/issues/9409)
* MessageDigest Encoder is not ThreadSafe [#9413](https://github.com/gravitee-io/issues/issues/9413)
* Configuration files are being overwritten during YUM update [#9368](https://github.com/gravitee-io/issues/issues/9368)

</details>

## Gravitee Access Management 4.0.5 - November 10, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Deadlock during generate AccessToken [#9238](https://github.com/gravitee-io/issues/issues/9238)

**Other**

* Upgrade Groovy policy [#9229](https://github.com/gravitee-io/issues/issues/9229)
* EnrollmentMFA policy doesn't manage the useVariableFactorSecurity setting [#9365](https://github.com/gravitee-io/issues/issues/9365)

</details>

## Gravitee Access Management 4.0.4 - October 27, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Application error when using an undefined translation [#9237](https://github.com/gravitee-io/issues/issues/9237)
* Registration confirmation Javascript error (anti-XSRF token) [#9276](https://github.com/gravitee-io/issues/issues/9276)
* Quotes are lost in Gravitee AM forms [#9326](https://github.com/gravitee-io/issues/issues/9326)
* When a resource plugin has been removed from the installation, other resources may not be loaded [#9344](https://github.com/gravitee-io/issues/issues/9344)

**Management API**

* Management API hangs completely [#9339](https://github.com/gravitee-io/issues/issues/9339)

**Other**

* EnrichProfile reset factor defined by EnrollMFA policy [#9161](https://github.com/gravitee-io/issues/issues/9161)

</details>

## Gravitee Access Management 4.0.3 - October 16, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* Align XSRF token TTL to the user session TTL [#9282](https://github.com/gravitee-io/issues/issues/9282)

**Management API**

* Wrong values returned by Gravitee AM Management API [#9141](https://github.com/gravitee-io/issues/issues/9141)
* AM Management API should start even with missing or unknown Identity Provider plugins [#9230](https://github.com/gravitee-io/issues/issues/9230)

**Other**

* MS SqlServer 10.2 onwards driver support [#9178](https://github.com/gravitee-io/issues/issues/9178)
* Upgrade script for 3.21.6 does not work as expected [#9288](https://github.com/gravitee-io/issues/issues/9288)
* Update Mongo script to create indices [#9291](https://github.com/gravitee-io/issues/issues/9291)

</details>

## Gravitee Access Management 4.0.2 - September 29, 2023

<details>

<summary>Bug fixes</summary>

**Gateway**

* AM allows invalid emails during MFA enrollment which prevents future logins and presents an attack vector [#8887](https://github.com/gravitee-io/issues/issues/8887)
* Gravitee AM: Search users using SCIM query [#9109](https://github.com/gravitee-io/issues/issues/9109)
* 500 internal server error due to invalid HTML template in enroll, login , challenge form [#9111](https://github.com/gravitee-io/issues/issues/9111)
* AM: Invalid encoding value after multiple redirects [#9154](https://github.com/gravitee-io/issues/issues/9154)
* Filter is not implemented in SCIM group endpoint [#9183](https://github.com/gravitee-io/issues/issues/9183)
* Key usage is always "enc" [#9236](https://github.com/gravitee-io/issues/issues/9236)

**Management API**

* Multiple concurrent requests create users with duplicated usernames [#9117](https://github.com/gravitee-io/issues/issues/9117)

**Console**

* After a migration, the IDP checkbox `Allow CRUD operation` is not shown as enabled in the UI but is enabled in the backend [#9123](https://github.com/gravitee-io/issues/issues/9123)

**Other**

* When the pre-registration option is set, we are not able to finish the registration properly [#9221](https://github.com/gravitee-io/issues/issues/9221)
* Allow the bypass of MongoDB indices creation [#9232](https://github.com/gravitee-io/issues/issues/9232)
* Map of claims unusable in EL [#9240](https://github.com/gravitee-io/issues/issues/9240)
* Alerts Dashboard is not retaining the alert channel selection/deselection [#9253](https://github.com/gravitee-io/issues/issues/9253)

</details>

## Gravitee Access Management 4.0.0 - July 20, 2023

For more in-depth information on what's new, please refer to the [Gravitee AM 4.0 release notes](../release-notes/).

<details>

<summary>What's new</summary>

**Enterprise Edition**

Some plugins are now part of the Enterprise Edition:

* idp-saml2
* idp-ldap
* idp-azure-ad
* idp-franceconnect
* idp-salesforce
* factor-call
* factor-sms
* factor-fido2
* factor-http
* factor-recovery-code
* factor-otp-sender
* resource-twilio

**Community Edition**

If you use the Community Edition, for each enterprise feature you will have a dedicated pop-up to suggest the enterprise version.

* Password: Password salt format option
* Flows: Add new TOKEN flow
* MFA: Initiate MFA Enrollment via OpenID Connect 1.0
* Send email verification link
* Ability to re-trigger verification email
* Passwordless: Name passwordless device

**Gateway**

* It is impossible to see the user that consented the user consent in the audit log: [#9049](https://github.com/gravitee-io/issues/issues/9049)
* Allow OTP factor to handle clock drift issues: [#9074](https://github.com/gravitee-io/issues/issues/9074)

**Management API**

* Create account with uppercase username: [#8966](https://github.com/gravitee-io/issues/issues/8966)

**Other**

* Index name is too long: [#8814](https://github.com/gravitee-io/issues/issues/8814)
* Allow Enrich User Profile policy to accept objects as new claims
* WebAuthn post login flow does not contain webAuthnCredentialId
* Column messages in `i18n_dictionary_entries` table has too few characters

</details>

<details>

<summary>Breaking Changes</summary>

**NOTE:** To take advantage of these new features and incorporate these breaking changes, use the [migration guide](../../getting-started/install-and-upgrade-guides/upgrade-guide.md).

**MongoDB index names**

Starting from AM 4.0, the MongoDB indices are now named using the first letters of the fields that compose the index. This change will allow the automatic management of index creation on DocumentDB. This change requires the execution of a MongoDB script to delete and then recreate AM indices. See the [migration guide](../../getting-started/install-and-upgrade-guides/upgrade-guide.md).

**Enterprise Edition plugins**

As mentioned in the [changelog](am-4.0.x-changelog.md), some plugins are now only available to Enterprise Edition and to use them requires a license.

</details>
