## Abstract
<!-- Context      -->
The current integration of Solid is to this day often restricted to
programming-heavy integrations into Web applications.
<!-- Need         -->
Where existing process flows often use the command line for data 
pipelining between processes, support for Solid integration in this
ecosystem is lacking.
<!-- Task         -->
To enable integration of Solid into such tooling, 
we developed a CLI wrapper that provides functioanlity
for interactions between Solid Pods and the local file system.
<!-- Object       -->
The Bashlib program provides a CLI wrapper around
authentication, authorization and resource management
functionality for Solid. 
By caching sessions for multiple profiles, it can 
swap authentication on the fly to support mutliple 
profiles for different workflows.   
<!-- Findings     -->
<!-- ## No findings ## -->
<!-- Conclusion   -->
Supporting Solid functionality in the command line opens up many
workflows to cheap integration, both for managing local data in
a cloud-like fashion, as well as for automated data sharing 
between parties based on the Solid authentication and authorization stack.
<!-- Perspectives -->
<!-- ## No perspectives ## -->

Integrating Solid in workflows requires intensive knowledge of libraries and programming languages.
Where BASH allows for straightforward integration in existing workflows, Solid has little tooling to support this.
Authentication flows exceed the
We present BashLib as a Solid authentication wrapper for common BASH functionality and Solid-specific additions
Goal to enable CLI flows to integrate Solid in their workflow