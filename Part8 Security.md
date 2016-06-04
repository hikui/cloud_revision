# Authenticaton

Authentication is the establishment and propagation of a user’s ==identity== in the system. (Prove who you are) (Doesn't check what user is allowed to do (this is achieved by authorization))

Traditionally: username / password

Solution on clouds: Public Key Infrastructure (PKI)

# Public Key Cryptography

https://en.wikipedia.org/wiki/Public-key_cryptography

Benefits: Public Key Cryptography simplifies key management. Users don’t need to have many keys for long time.

# Shibboleth and Federated Identity (Single Sign-On / Decentralized Authentication) 

![](img/sso.png)

Single Sign-on (SSO) allows users to access multiple services with a single login. (e.g. 微博一键登录)

Federated Identity (FID) refers to where the user stores their credentials. Alternatively, FID can be viewed as a way to ==connect Identity Management systems together==. In FID, a user's credentials are always stored with the =="home" organization (the "identity provider")==. When the user logs into a service, instead of providing credentials to the service provider, ==the service provider **trusts** the identity provider to validate the credentials.== So the user never provides credentials directly to anybody but the identity provider.

## Benefits

> Copied from Wikipedia

Ease of use: 

* Reducing password fatigue from different user name and password combinations
* Reducing time spent re-entering passwords for the same identity

## Drawbacks (Security problems)

> Copied from Wikipedia

* It increases the negative impact in case the ==credentials are available to other persons and misused==.
* It makes the authentication systems highly critical; a loss of their availability can result in denial of access to all systems unified under the SSO. 

---

# Authorization

Authorisation is concerned with controlling access to resources based on policy.