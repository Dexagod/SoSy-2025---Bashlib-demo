## Authentication
{:#authentication}

<!-- * Solid authentication is the core on which its privacy systems are built. -->
<!-- * Bashlib supports interactive browser login flows -->
<!-- * Bashlib supports hot-swapping authentication sessions on the fly to quickly swap between professional and personal identities. -->
<!-- * As interactive authentication flows are essential for back-end tasks, we support the latest client credentials implementations from both the CSS and ESS implementations. -->

Authentication is a fundamental component of the Solid protocol, serving as the foundation for its privacy mechanisms.
The Solid access control systems that allow users to manage their Solid pods and share data with actors in the network
is based on the identity of the user and the actors with whom data is being shared. 
To design capabilities for Solid authentication management on the CLI needs to take into account the following requirements:

(i) Bashlib supports the OpenID Connect defined in the Solid specification [todo: cite? or footnote]()
to authenticate users through an interactive browser logion flow. 
This opens up an identical interface as when authenticating a Solid session 
using Web applications. Where this flow is compatible with all Solid Server 
implementations, the interactive nature of the authentication flow makes 
it jarring for most CLI integrations.

(ii) Building authentication systems for multiple identities is a core requirement for many workflows. 
Bashlib internally caches any authenticated sessions, 
making it possible to quickly swap between sessions in workflows.
This feature is particularly useful for professionals managing both personal 
and enterprise-level Solid interactions, allowing for smooth transitions between identities.

(iii) Where Bashlib supports the interactive OpenID Connect login flow in the browser,
this is not usable for automated systems that need to synchronize, manage and exchange 
data via the Solid protocol. For this reason, both the [Community Solid Server](cite:cites van2024community)[^CSS]
and the [Enterprise Solid Server]()[^ESS] implementations of the Solid Server provide support for a Client Credentials flow,
that enable authenticated sessions to be dynamically setup in the background without user interaction.
By integrating these credential-based authentication methods, 
BashLib enables backend services to securely access Solid resources without manual intervention, 
expanding the potential for Solid adoption in automated and infrastructure-level applications.

[^CSS]: The [Community Solid Server]([cite:cites van2024community](https://communitysolidserver.github.io/CommunitySolidServer/latest/)) is a research project developed by the [KNoWS team](https://knows.idlab.ugent.be/) at Ghent University.
[^ESS]: The [Enterprise Solid Server](https://www.inrupt.com/) is a Solid Server implementation by [Inrupt](https://www.inrupt.com/).


Going back to the example, our researcher Ben is hosting their own Solid pod 
on a Community Solid Server instance[](cite:cites van2024community).
To setup bashlib to work without needing user interaction, Ben sets up
a credential flow for Bashlib to enable the automated creation of 
authenticated sessions where needed. For this, Ben executes the code
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