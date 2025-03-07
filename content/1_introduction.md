## Introduction
{:#introduction}

<!-- * Integrating Solid in workflows requires intensive knowledge of libraries and programming languages. -->
<!-- * Where BASH allows for straightforward integration in existing workflows, Solid has little tooling to support this. -->
<!-- * We present BashLib as a Solid authentication wrapper for common BASH functionality and Solid-specific additions -->
<!-- * Goal to enable CLI flows to integrate Solid in their workflow -->

The [Solid Specification](cite:cites sambra_solid_2016) defines a protocol for
managing and exchanging data as resources on the Web, to empower its users 
with control over their data and providing data interoperability 
in the Web ecosystem[](cite:cites verborgh_timbl_chapter_2023).
By focusing support on the Web application ecosystem, 
workflows for data management and exchange that are 
outside the browser ecosystem are restricted in their options 
to integrate with the Solid ecosystem.
The command line supports a rich ecosystem of workflows that orchestrate 
data management, sharing, and integration for both private and professional use cases.
Providing support for Solid in this command line ecosystem can enable straightforward
integration pathways for these workflows into the Solid ecosystem.

To address this lack of tooling, we introduce BashLib as a Solid compatibility wrapper
for the command line. It provides commonly used command line utilities for resource management 
and integrates them with Solid functionality for authentication, authorization, and managing 
resource sharing on the Web. 
Additional capabilities such as evaluation of SPARQL queries over the document structure 
of a Solid pod and local editing of remote resources are also provided.
By bridging the gap between Solid and the command line, 
BashLib aims to facilitate broader adoption of the Solid outside the browser ecosystem.

Setting an example use-case, we have the case of a researcher making a presentation
for an upcoming conference. We look at how Bashlib can support our researcher Ben 
to integrate their workflow of receiving feedback from colleagues on a presentation 
in development and the public publishing the resulting presentation using their Solid pod.

The full tutorial of Bashlib can be found on the [website](https://solidlabresearch.github.io/Bashlib/tutorial/)[^tutorial].

[^tutorial]: [https://solidlabresearch.github.io/Bashlib/tutorial/](https://solidlabresearch.github.io/Bashlib/tutorial/)
