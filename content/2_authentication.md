## Authentication
{:#authentication}

<!-- * Solid authentication is the core on which its privacy systems are built. -->
<!-- * Bashlib supports interactive browser login flows -->
<!-- * Bashlib supports hot-swapping authentication sessions on the fly to quickly swap between professional and personal identities. -->
<!-- * As interactive authentication flows are essential for back-end tasks, we support the latest client credentials implementations from both the CSS and ESS implementations. -->

Authentication is a fundamental component of the Solid protocol, 
serving as the foundation for its privacy and data sharing mechanism.
As different workflows impose different constraints on the management
of user identity and authentication, Bashlib supports the following authentication capabilities:


1. Compatibility with the [Solid OpenID Connect](https://solidproject.org/TR/oidc)[^solid-oidc]
speficiation is integrated in Bashlib, proving an interactive authentication flow via the browser.
As this is the standardized login flow, it is compatible with all Solid Server implementations, 
but it comes with a downside of requiring user interaction to authenticate
which can make it undesirable in automated command-line workflows.
   
2. Alternatively, support is added for token-based authentication options that are 
provided by both the [Community Solid Server (CSS)](cite:cites van2024community)[^CSS]
and the [Enterprise Solid Server (ESS)](cite:cites ess)[^ESS] implementations of the Solid Server.
These token-based authentication options do not require any user interaction after
generating the client token when setting up new authenticated sessions, 
making them ideal for automated background workflows or commonly used routines.
As these token-based authentication options are not standardized 
and differ between implementations, they can break at any point
and are advised only for server hosting does not update their
underlying implementation or that is under user control.

3. Finally, support is provided for switching authenticated sessions.
As different workflows may have different identity requirements, as is often the case
when combining professional and personal data management tasks, 
authentication systems need to take this into account.
Bashlib performs internal caching of authenticated sessions and provides support
for passing an identity parameter to any call, or opening an interactive
form to swap out the active session identity.

Returning to the example, researcher Ben has their Solid Pod hosted
on a CSS instance.
To setup bashlib to work without needing user interaction, 
Ben sets up the token-based authentication flow to prevent interruptions
from authentication popups during work. For this, Ben executes the code
in [](#authentication-listing) and provides their email and password
information via the interactive command line form.

<figure id="authentication-listing" class="listing">
<pre style="font-size: 14px"><code>npx bashlib-solid auth create-token-css 
    --webid https://bob.myPodProvider.org/profile/card#me
</code></pre>
<figcaption markdown="block">
The researcher creates a credential token to setup automated authentication for their workflows. Email and password info is provided in the interactive cli form.
</figcaption>
</figure>



[^CSS]: The [Community Solid Server]([cite:cites van2024community](https://communitysolidserver.github.io/CommunitySolidServer/latest/)) is a research project developed by the [KNoWS team](https://knows.idlab.ugent.be/) at Ghent University.
[^ESS]: The [Enterprise Solid Server](https://www.inrupt.com/) is a Solid Server implementation by [Inrupt](https://www.inrupt.com/).
[^solid-oidc]: [https://solidproject.org/TR/oidc](https://solidproject.org/TR/oidc)