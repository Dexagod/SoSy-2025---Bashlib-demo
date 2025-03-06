## Introduction
{:#introduction}

<!-- * Integrating Solid in workflows requires intensive knowledge of libraries and programming languages. -->
<!-- * Where BASH allows for straightforward integration in existing workflows, Solid has little tooling to support this. -->
<!-- * We present BashLib as a Solid authentication wrapper for common BASH functionality and Solid-specific additions -->
<!-- * Goal to enable CLI flows to integrate Solid in their workflow -->

The [Solid Specification](cite:cites sambra_solid_2016) defines a protocol for
managing and exchanging data as resources on the Web, to empower its users 
with control over their data and providing data interoperability in the Web ecosystem.
By focussing support on the Web application ecosystem, workflows that do not use the 
browser ecosystem for data management and exchange are restricted in their options to integrate
with the Solid ecosystem.
Where the command line ecosystem is a rich ecosystem of workflows that orchestrate 
data management, sharing, and integration, both for private and professional workflows,
providing integration options for the Solid protocol can enable straightforward
mapping of these existing command line workflows to the Solid ecosystem.

To address this lack of tooling, we introduce BashLib as a Solid compatibility wrapper
for the command line. It provides commonly used command line utilities for resource management 
and integrates them with Solid functionality for authentication, authorization, and managing 
resource sharing on the Web. Additional solid specific functionality such as evaluating
SPARQL queries over remote resources and local editing of remote resources are also included.
By bridging the gap between Solid and the command line, 
BashLib aims to facilitate broader adoption 
of the Solid ecosystem in non-Web workflows.

To set an example, we take the case of a researcher who is making a presentation
for an upcoming conference. We will look at how Bashlib supports the flow of 
a researcher named Ben, who wants to integrate their workflow of getting feedback
from colleagues on a presentation in development and publishing the resulting 
presentation, using their Solid pod.