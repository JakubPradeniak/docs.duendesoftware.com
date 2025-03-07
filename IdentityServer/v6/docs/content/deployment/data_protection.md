---
title: "ASP.NET Core Data Protection"
date: 2020-09-10T08:22:12+02:00
weight: 20
---

Duende IdentityServer relies on the built-in [data protection](https://docs.microsoft.com/en-us/aspnet/core/security/data-protection/) feature of ASP.NET for

* protecting signing keys at rest (if [automatic key management]({{< ref "/fundamentals/keys" >}}) is used and enabled)
* protecting [persisted grants]({{< ref "/data/operational/grants" >}}) at rest (if enabled)
* protecting [server-side session]({{< ref "/ui/server_side_sessions" >}}) data at rest (if enabled)
* protecting [the state parameter]({{< ref "/ui/login/external#state-url-length-and-isecuredataformat" >}}) for external OIDC providers (if enabled)
* protecting message payloads sent between pages in the UI (e.g. [logout context]({{< ref "/ui/logout/logout_context" >}}) and [error context]({{< ref "/ui/error" >}})).
* session management (because the ASP.NET Core cookie authentication handler requires it)

It is crucial that you setup ASP.NET Core data protection correctly before you start using your IdentityServer in production. Please consult the Microsoft [documentation](https://docs.microsoft.com/en-us/aspnet/core/security/data-protection/configuration/overview) for more details.
