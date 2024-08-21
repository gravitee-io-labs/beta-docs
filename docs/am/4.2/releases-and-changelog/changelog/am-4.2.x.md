---
description: >-
  This page contains the changelog entries for AM 4.2.x and any future minor or
  patch AM 4.2.x releases
---

# AM 4.2.x

## Gravitee Access Management 4.2.19 - August 21, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Not double dash "--" in the returned code from an OAuth2 authentication flow [#9910](https://github.com/gravitee-io/issues/issues/9910)
* Secrets in responses of SSAM [#9926](https://github.com/gravitee-io/issues/issues/9926)

**Management API**

* Audits present twice during user creation [#9837](https://github.com/gravitee-io/issues/issues/9837)
* MFA - Invalid 2FA code  [#9929](https://github.com/gravitee-io/issues/issues/9929)

</details>


## Gravitee Access Management 4.2.18 - August 19, 2024

{% hint style="warning" %}

Due to technical issues during release process, 4.2.18 version should be ignored. Please skip these this version and upgrade straight to 4.2.19&#x20;

{% endhint %}


## Gravitee Access Management 4.2.17 - August 2, 2024

<details>

<summary>Bug fixes</summary>







**Other**

* [AM][GW] Set tl client header name behind reverse proxy through helm chart [#9874](https://github.com/gravitee-io/issues/issues/9874)
* Cannot save UserInfo Endpoint in UI - Save Button Disabled [#9879](https://github.com/gravitee-io/issues/issues/9879)
* Configuration via la console AM non prise en compte sur les gateways [#9888](https://github.com/gravitee-io/issues/issues/9888)
* MFA - weird behavior when user is going back to the previous enroll step [#9897](https://github.com/gravitee-io/issues/issues/9897)
* Error "ERR_TOO_MANY_REDIRECTS" when hide login form is enabled. [#9898](https://github.com/gravitee-io/issues/issues/9898)

</details>


## Gravitee Access Management 4.2.16 - July 19, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Propagate Message from Error Condition of HTTP IdP to Audit log. [#9841](https://github.com/gravitee-io/issues/issues/9841)
* Passwordless KO - Certificate provider is required to sign JWT [#9864](https://github.com/gravitee-io/issues/issues/9864)

**Management API**

*  Redirect to login when device credentials are deleted [#9859](https://github.com/gravitee-io/issues/issues/9859)

**Console**

* A switch has an incorrect state when revisiting page - Application Settings [#9433](https://github.com/gravitee-io/issues/issues/9433)

**Other**

* Switching between environments is broken when multiple environments linked in cockpit [#9844](https://github.com/gravitee-io/issues/issues/9844)
* "Rotate System Key" modifies application remember-device setting [#9857](https://github.com/gravitee-io/issues/issues/9857)

</details>


## Gravitee Access Management 4.2.15 - July 5, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* OTPFactorProvider - An error occurs while validating 2FA code [#9725](https://github.com/gravitee-io/issues/issues/9725)
* null-1 entry in auth_flow_ctx table should not be stored in database [#9803](https://github.com/gravitee-io/issues/issues/9803)





**Other**

* When creating user with preregistratoin, the password creation steps are skipped [#9839](https://github.com/gravitee-io/issues/issues/9839)

</details>


## Gravitee Access Management 4.2.14 - June 21, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Heml duplication of configuration [#9778](https://github.com/gravitee-io/issues/issues/9778)


**Other**

* Improve the ingress configuration to redirect HTTPS [#9712](https://github.com/gravitee-io/issues/issues/9712)
* AM Gateway pod is not starting due to StackOverflowError [#9794](https://github.com/gravitee-io/issues/issues/9794)

</details>


## Gravitee Access Management 4.2.13 - June 6, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* [AM] [3.21.18] User don't receive the email to recover his password with an uppercase email [#9624](https://github.com/gravitee-io/issues/issues/9624)
* Exception on start-up in Spring Boot applications after upgrade to AM 4.3.1 [#9667](https://github.com/gravitee-io/issues/issues/9667)
* Error Azure SCIM user update  [#9674](https://github.com/gravitee-io/issues/issues/9674)
* DCR new client using Template doesn't copy all parameters [#9691](https://github.com/gravitee-io/issues/issues/9691)
* Brute Force Detection not working to IDPs with Account Linking Policy [#9713](https://github.com/gravitee-io/issues/issues/9713)
* Source IP and user agent missing from FORGOT_PASSWORD_REQUESTED audit log [#9724](https://github.com/gravitee-io/issues/issues/9724)
* Domain not available into the ExpresionLanguage context [#9745](https://github.com/gravitee-io/issues/issues/9745)

**Management API**

* Not able to configure email notifier using Gravitee [#9581](https://github.com/gravitee-io/issues/issues/9581)

**Console**

* AM - Change error message when admin user tries to remove certificate tied to an application [#8952](https://github.com/gravitee-io/issues/issues/8952)

**Other**

* Editing HTTP Provider selects wrong password encoder [#9627](https://github.com/gravitee-io/issues/issues/9627)

</details>


## Gravitee Access Management 4.2.12 - May 24, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Error with MFA Challenge policy in Reset Password Flow [#9735](https://github.com/gravitee-io/issues/issues/9735)

**Other**

* Unable to remove a FORM at organization level [#9124](https://github.com/gravitee-io/issues/issues/9124)
* Application - Forms - Page not found error when enabling custom form again after being 'cleared' [#9492](https://github.com/gravitee-io/issues/issues/9492)
* \[DCR] improve client sanitizeTemplate method [#9687](https://github.com/gravitee-io/issues/issues/9687)
* Password Policy Blank value in dropbox when selecting value Unlimited

</details>

## Gravitee Access Management 4.2.11 - May 9, 2024

<details>

<summary>Bug fixes</summary>

**Other**

* There are no MFA logs [#9629](https://github.com/gravitee-io/issues/issues/9629)
* \_node/health endpoint is not accessible [#9698](https://github.com/gravitee-io/issues/issues/9698)
* Plugin "Orange Contact Everyone" is not compatible with version 4.3.2 [#9704](https://github.com/gravitee-io/issues/issues/9704)

</details>

## Gravitee Access Management 4.2.10 - April 29, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Issue with MFA and silent refresh token [#9622](https://github.com/gravitee-io/issues/issues/9622)
* \[WebAuthn] Problèmatique Authenticator "SecurityError : The operation is insecure." [#9686](https://github.com/gravitee-io/issues/issues/9686)

**Management API**

* Not able to add new attribute to User’s profile through AM REST Api when using Google Identity provider [#8434](https://github.com/gravitee-io/issues/issues/8434)
* AM - Application Analytics Timeout [#9405](https://github.com/gravitee-io/issues/issues/9405)

**Other**

* La vérification a échoué + email pas envoyé automatiquement [#9659](https://github.com/gravitee-io/issues/issues/9659)

</details>

## Gravitee Access Management 4.2.9 - April 12, 2024

<details>

<summary>Bug fixes</summary>

**Console**

* Error when notifications are acknowledged [#9661](https://github.com/gravitee-io/issues/issues/9661)

**Other**

* Enrollment Flow Logic Bug [#9518](https://github.com/gravitee-io/issues/issues/9518)
* Improve CORS Domain settings and replace default values [#9531](https://github.com/gravitee-io/issues/issues/9531)

</details>

## Gravitee Access Management 4.2.8 - April 5, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Disable Application [#9584](https://github.com/gravitee-io/issues/issues/9584)

**Other**

* Expired records present in table ciba\_auth\_requests. Cron is not taken into account. [#9499](https://github.com/gravitee-io/issues/issues/9499)
* Logs too verbose in AM when GeoIP plugin is not available [#9633](https://github.com/gravitee-io/issues/issues/9633)
* Support SAML mixing response binding protocol [#9648](https://github.com/gravitee-io/issues/issues/9648)

</details>

## Gravitee Access Management 4.2.7 - March 29, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Login - MFA challenge should be prompted when prompt=login is used [#9497](https://github.com/gravitee-io/issues/issues/9497)
* Revert: Passwordless authentication doesn't take the IDP status into account (#9494) [#9615](https://github.com/gravitee-io/issues/issues/9615)
* User unable to authenticate when linked to different identities [#9616](https://github.com/gravitee-io/issues/issues/9616)
* Addition of WebAuthn Credentials info into the context [#9620](https://github.com/gravitee-io/issues/issues/9620)

**Console**

* No space between source IP and user agent in audit logs [#9458](https://github.com/gravitee-io/issues/issues/9458)
* User agent showing 'undefined' in audit logs [#9459](https://github.com/gravitee-io/issues/issues/9459)
* Fetch user group doesn't persist [#9609](https://github.com/gravitee-io/issues/issues/9609)

**Other**

* Linked accounts are not listed in the UI when using SQL database [#9610](https://github.com/gravitee-io/issues/issues/9610)

</details>

## Gravitee Access Management 4.2.6 - March 15, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Redirect executed with jwt-bearer grant\_type [#9505](https://github.com/gravitee-io/issues/issues/9505)
* Invalid Phone Number [#9519](https://github.com/gravitee-io/issues/issues/9519)

</details>

## Gravitee Access Management 4.2.5 - February 29, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Passwordless authentication doesn't take the IDP status into account [#9494](https://github.com/gravitee-io/issues/issues/9494)
* State parameter encoded twice with response\_mode set to form\_post [#9528](https://github.com/gravitee-io/issues/issues/9528)
* Passwordless registration appearing for users who have already authenticated with step up [#9568](https://github.com/gravitee-io/issues/issues/9568)

</details>

## Gravitee Access Management 4.2.4 - February 19, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Unable to finalize SAML authentication using HTTP-POST binding [#9485](https://github.com/gravitee-io/issues/issues/9485)
* Security Domain may not be loaded on Gateway startup [#9496](https://github.com/gravitee-io/issues/issues/9496)
* Custom email not being sent when resending account registered verification email [#9500](https://github.com/gravitee-io/issues/issues/9500)
* Do not log stack trace when user has to provide password after webauthn authentication [#9503](https://github.com/gravitee-io/issues/issues/9503)

**Console**

* Missing read password policy role [#8924](https://github.com/gravitee-io/issues/issues/8924)

**Other**

* SAML 2.0 Identity Provider requires AM dependency update [#9515](https://github.com/gravitee-io/issues/issues/9515)

</details>

## Gravitee Access Management 4.2.3 - February 8, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Invalid form parameter when ResponseMode is set to form\_post [#9179](https://github.com/gravitee-io/issues/issues/9179)
* SCIM search operator PR doesn't work as expected [#9265](https://github.com/gravitee-io/issues/issues/9265)
* Authentication flow rejected due to redirect\_uri when PAR is used [#9478](https://github.com/gravitee-io/issues/issues/9478)
* MFA challenge should be prompted before registering a passwordless device [#9479](https://github.com/gravitee-io/issues/issues/9479)
* Remember Device Not Functioning with Conditional MFA [#9484](https://github.com/gravitee-io/issues/issues/9484)
* WebAuthn: "Force authenticator integrity" - LastCheckedAt systematically updated at each webauthn login [#9327](https://github.com/gravitee-io/issues/issues/9327)

**Management API**

* Apply timeout on blockingGet in ManagementAPI filters [#9476](https://github.com/gravitee-io/issues/issues/9476)

</details>

## Gravitee Access Management 4.2.2 - January 30, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Passwordless not working for iOS v17.2.1 [#9470](https://github.com/gravitee-io/issues/issues/9470)
* Flow - Add WebAuthn credential register flow (improvement)

</details>

## Gravitee Access Management 4.2.1 - January 17, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Avoid BodyHandler processing for GET request [#9352](https://github.com/gravitee-io/issues/issues/9352)
* WebAuthnCredentialId is null into the EL context [#9455](https://github.com/gravitee-io/issues/issues/9455)

**Other**

* AEConnector not initialized properly since AM 4.1 [#9454](https://github.com/gravitee-io/issues/issues/9454)

</details>

## Gravitee Access Management 4.2 - December 21, 2023

For more in-depth information on what's new, please refer to the [Gravitee AM 4.2 release notes](../release-notes/am-4.2.md).

<details>

<summary>What's new</summary>

**Enterprise Edition**

New SMS resource provider based on the SFR vendor. Administrators can set up their SFR credentials to link Gravitee AM to SFR SMS service and activate the MFA SMS factor for selected applications.

A new Secret Management plugin that uses the Key/Value engine of HashiCorp Vault.

**Community Edition**

A new Secret Management plugin that fetches secret and TLS pairs from Kubernetes.io.

Gravitee AM 4.2 enhancements to the Remember Device feature that provides login authentication.

It is now possible to improve the security of a client secret by storing a hashed value.

Password Policy can be reset at the domain level to fallback to the default policy defined in the `gravitee.yaml`.

</details>

<details>

<summary>Breaking changes</summary>

The client secret will no longer be available through the AM Console or Management API. The secret will be provided only once, after the application creation or after the secret renewal. Before upgrading to AM 4.2, make sure to copy the client secret of your existing applications.

</details>
