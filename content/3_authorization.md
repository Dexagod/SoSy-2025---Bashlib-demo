## Authorization
{:#authorization}

<!-- * As Solid supports two authorization specifications, we support the management using both specifications, using the INRUPT AUthentication libraries. -->
<!-- * The AC mechanism is discovered on the fly -->
<!-- * For managing Access Control Resources, we do not support the full suite of functionality yet, only the Universal API by INRUPT tooling. -->

The Solid authorization mechanism determines how resource access is granted and managed.
The current Solid ecosystem supports two distinct authorization systems: 
The [Web Access Control (WAC)](cite:cites WAC) specification and 
the [Access Control Policy (ACP)](cite:cites ACP) specification. 
The coexistence of these two specification in the Solid ecosystem 
adds complexity in having to support seamless integration between
these competing authorization standards.

Bashlib integrates the core functionality of both authorization mechanisms 
in their management of individual resources based on the identity of the
requesting party. The used authorization system is recognized dynamically
and the management interface is chosen accordingly.
Where the ACP specification is more elaborate in its functionality than the
WAC specification, only the resource-specific management of identity-based
access control is supported. managing resources on a WAC-based Solid Server
implementation, group identities and recursive authorization management is supported.

<!-- Should we mention Inrupt here? -->
<!-- leveraging the [Inrupt authentication library](todo: footnote) to implement permission management, -->
<!-- 

For modifying access permissions, BashLib currently supports the Universal API provided by Inrupt’s tooling. While this does not yet encompass the full range of functionality available for managing Access Control Resources (ACRs), it provides a streamlined way to handle common authorization tasks. This allows users to interact with Solid’s access control models without needing to manually configure complex permission structures. -->

Simplifying the authorization management to resource-based authentication management
command-line workflows can integrate all Solid compatible systems into their flows,
and provide authorization management based on external systems such as cron jobs.

Continuing the example, Ben needs both a public location to 
publish completed presentations and a private location 
where work in progress can be shared with colleagues.
To achieve this, Ben creates a public Solid container
in which the final publications are published, 
and a private Solid container to store in-progress work
to be shared with their colleagues Pieter and Ruben as shown in [](#auth-listing).

<figure id="auth-listing" class="listing">
<pre style="font-size: 14px"><code># Initializing the public workspace
npx bashlib-solid mkdir base:/public/presentations/
npx bashlib-solid access set --default 
    base:/public/presentations/ p=[r]

# Intializing the private workspace
npx bashlib-solid mkdir base:/private/presentations/
npx bashlib-solid access set --default 
    base:/private/presentations/ https://pieter.myPodProvider.org/profile/card#me=r
npx bashlib-solid access set --default 
    base:/private/presentations/ https://ruben.myPodProvider.org/profile/card#me=r
</code></pre>
<figcaption markdown="block">
The researcher creates a public presentations container located at https://ben.myPodProvider.org/public/presentations/
where public read permissions are set (p=r).
Next a private container is created at https://ben.myPodProvider.org/private/presentations/
where only the colleagues are given read access (<id>=r).
The --default flag sets up recursive permissions for all child resources in WAC-based Solid Servers.
When using ACP-based Solid pods, individual resource permissions have to be assigned in Bashlib.
</figcaption>
</figure>