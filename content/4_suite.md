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

Providing the above set of CLI utilities,
Bashlib provides a base set of functionality 
that is required to integrate existing 
command line workflows into the Solid ecosystem.


In our running example, having created the Solid containers
for in-progress work [](#private-auth-listing) 
and public presentations [](#public-auth-listing),
Ben now sets up the scripts to sync his work to
the in-progress container [](#private-publishing)
that will be visible for Pieter and Ruben to read
for feedback, and the sync script for the finihsed 
presentation in [](#public-publishing)
that makes the result public.


<figure id="private-publishing" class="listing">
<pre style="font-size: 14px"><code>
> publish-private.sh
#!/bin/bash
npx bashlib-solid cp sosy-presentation/ base:/private/publication/
</code></pre>
<figcaption markdown="block">
The researcher publishes the presentation directory to their private publications container on their Solid pod.
</figcaption>
</figure>


<figure id="public-publishing" class="listing">
<pre style="font-size: 14px"><code>
> publish-public.sh
#!/bin/bash
npx bashlib-solid cp sosy-presentation/ base:/public/publication/
</code></pre>
<figcaption markdown="block">
The researcher publishes the presentation directory to their public publications container on their Solid pod.
</figcaption>
</figure>