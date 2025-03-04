## Tooling Suite
{:#suite}

The main part of the functionality provided by Bashlib is aimed at data management.
This functionality is aimed at align commonly used command-line utilities to the
Solid [Linked Data Platform](todo: cite) specification used for data management
in an authenticated session.

<!-- Basic Shell Utilities -->
A large section of the provided Bashlib functionality aligns with core shell utilities,
making use of the authenticated session to authenticate the user in outgoing requests.
The `curl` mimics its namesake's functionality with added outgoing Authentication headers.
The `ls` utility provides directory listings of the target Solid container.
The `tree` utility provides a recursive tree listing starting from the targeted Solid container.
The `cp` and `mv` utilities provide functionality to move and copy resources between both the 
local file system and Solid pods, automatically recognizing the source and target destinations
as being local or URIs and managing the transfer of resources accordingly.
The `touch`, `mkdir` and `rm` utilities provide functionality to create and remove resources and
containers on a Solid pod.
Finally, the `find` utility enables the searching of resources on a Solid pod based on their resource
URI.

Additionally, some Solid specific utility functions have been added.
The `query` utility executes a SPARQL query either over the individual resources
or the federated set of resources in the target Solid container.
The `edit` utility is used to load an external resource in a local editor,
and update the resulting resource when saved.


By providing the set of CLI utilities defined above,
Bashlib provides a base set of functionality to integrate
CLI workflows with the Solid ecosystem.