## Resource management
{:#suite}

To support the resource management requirements of command-line based workflows,
Bashlib integrates a set of command-line utilities for resource management
with the Solid resource interface.

<!-- Basic Shell Utilities -->
Bashlib implements the following set of utility functions that align with their command-line 
counterparts: 
The `curl` utility uses the authenticated Solid session to add outgoing Authentication headers.
The `ls` utility provides directory listings of the target Solid container.
The `tree` utility provides a recursive tree listing starting from the targeted Solid container.
The `cp` and `mv` utilities provide functionality to move and copy resources between both the 
local file system and Solid pods, automatically recognizing the source and target destinations
as being local or URIs and managing the transfer of resources accordingly.
The `touch`, `mkdir` and `rm` utilities provide functionality to create and remove resources and
containers on a Solid pod.
Finally, the `find` utility enables the searching of resources 
on a Solid pod based on their resource URI.
Note that in the above implemented set of utilities, 
exact formatting of output may vary from their native counterparts
and not all flags are implemented.

Additionally, some Solid specific utility functions have been added.
The `query` utility executes a SPARQL query either over the individual resources
or the federated set of resources in the target Solid container, 
using the [Comunica](https://comunica.dev/)[](cite:cites taelman2018comunica) query engine. 
The `edit` utility is used to load an external resource in a local editor,
and update the resulting resource when saved.

Providing the above set of CLI utilities,
Bashlib provides a base set of functionality 
that is required to integrate existing 
command line workflows into the Solid ecosystem.


In our running example, having created the Solid containers
for in-progress work and public presentations in [](#auth-listing),
Ben now sets up the scripts to sync his work to
the in-progress container [](#private-publishing)
that will be visible for Jos and Ella to read
for feedback, and the sync script for the finished 
presentation in [](#public-publishing)
that makes the result public.


<figure id="private-publishing" class="listing">
<pre style="font-size: 14px"><code>> publish-private.sh
#!/bin/bash
npx bashlib-solid cp sosy-presentation/ base:/private/publication/
</code></pre>
<figcaption markdown="block">
Publish work in progress in the restricted access container on the user Solid pod.
</figcaption>
</figure>


<figure id="public-publishing" class="listing">
<pre style="font-size: 14px"><code>> publish-public.sh
#!/bin/bash
npx bashlib-solid cp sosy-presentation/ base:/public/publication/
</code></pre>
<figcaption markdown="block">
Publish finished work in the public access container on the user Solid pod.
</figcaption>
</figure>