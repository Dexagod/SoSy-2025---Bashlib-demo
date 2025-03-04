## Authorization
{:#authorization}

<!-- * As Solid supports two authorization specifications, we support the management using both specifications, using the INRUPT AUthentication libraries. -->
<!-- * The AC mechanism is discovered on the fly -->
<!-- * For managing Access Control Resources, we do not support the full suite of functionality yet, only the Universal API by INRUPT tooling. -->


The Solid authorization mechanism determines how access to data is granted and managed, 
ensuring that users and applications interact with resources according to predefined permissions. 
Solid currently supports two distinct authorization specifications: 
The [Access Control Lists (ACLs)](todo: cite / footnote) specification and 
the [Access Control Policies (ACP)](todo: cite / footnote) specification. 
The coexistence of these two specification in the Solid ecosystem adds complexity
to streamline permission management for Solid workflows, 
requiring seamless support for both authorization mechanisms.

To address this, BashLib integrates support for both authorization specifications, 
based on automated discovery of the used mechanism and adapting the used permission API
on the fly.
However, as the ACP specification diverges far from the WAC specification, 
permission management is restricted to the resource level when automating 
discovery of the authorization method used by the Solid Server interacted with.
When prior knowledge of the use of WAC is known, recursive permission management
can be enabled.

<!-- Should we mention Inrupt here? -->
<!-- leveraging the [Inrupt authentication library](todo: footnote) to implement permission management, -->
<!-- 

For modifying access permissions, BashLib currently supports the Universal API provided by Inrupt’s tooling. While this does not yet encompass the full range of functionality available for managing Access Control Resources (ACRs), it provides a streamlined way to handle common authorization tasks. This allows users to interact with Solid’s access control models without needing to manually configure complex permission structures. -->

By simplifying authorization management fpr command-line workflows requiring data sharing, 
and the ability to integrate these systems into command line flows such as cron jobs [](todo: footnote / cite?), 
BashLib lowers the integration barrier for automated data sharing in the Solid ecosystem.