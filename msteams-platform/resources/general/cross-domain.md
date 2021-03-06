---
title: Cross-domain redirects
description: Describes the process of redirecting across domains in Microsoft Teams
keywords: teams crossdomain redirect
---
# Redirect across domains in a Microsoft Teams tab

In some cases, you might need to redirect the configuration or content page to a location on a different domain or subdomain. For example, suppose your configuration page begins on www.example.com. However, after a user who works for the Contoso Company signs in, your app needs to redirect to www.contoso.example.com (or perhaps even a different domain altogether, like www.anotherexample.com). If your app performs the redirects itself, it can no longer use the Microsoft Teams JavaScript library to receive or send information to Microsoft Teams.

Instead, you should request that Microsoft Teams perform the cross-domain redirects itself:

* Ensure that the URL is included in the `validDomains` list in your [manifest](~/concepts/apps/apps-package). For more information, see [validDomains](~/resources/schema/manifest-schema#validdomains) in the manifest schema reference.
* Call `microsoftTeams.navigateCrossDomain(yourNewUrl)` on the [Microsoft Teams JavaScript client SDK](/javascript/api/overview/msteams-client) to request that the iframe containing your page is redirected to the specified URL.
