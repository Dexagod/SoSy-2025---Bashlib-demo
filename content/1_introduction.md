## Introduction
{:#introduction}

<!-- * Integrating Solid in workflows requires intensive knowledge of libraries and programming languages. -->
<!-- * Where BASH allows for straightforward integration in existing workflows, Solid has little tooling to support this. -->
<!-- * We present BashLib as a Solid authentication wrapper for common BASH functionality and Solid-specific additions -->
<!-- * Goal to enable CLI flows to integrate Solid in their workflow -->



The [Solid Protocol](cite:cites sambra_solid_2016), designed for decentralized data storage and sharing, empowers users with control over their data in an interoperable web environment.

However, integrating Solid into existing workflows remains challenging, 
primarily as its adoption is mainly focused on its integration in Web applications.
In contrast, many professional and personal workflows that exchange data 
as documents via the command line could benefit from Solid's principles. 
However, as the Solid tooling is primarily focused on web applications, 
support for command line workflows is currently lacking.

To address this lack of tooling for Solid in the CLI ecosystem, 
we introduce BashLib as a CLI wrapper for Solid functionality in the command line ecosystem. 
Bashlib integrates Solid functionality for authentication, authorization and resource management.
This enables the integration of existing flows of data with the Solid ecosystem by 
providing integrations for resource sharing, querying and integration fpr the Solid ecosystem.

By bridging the gap between Solid and the command line, 
BashLib aims to facilitate broader adoption of Solid principles in automated workflows, 
widening the target audience of the Solid ecosystem 
and providing new capabilities for command-line based decentralized data management.

To set the example, we take the case of a researcher that is making a presentation
for an upcoming conference. We will look at how Bashlib supports the flow of 
a researcher named Ben, who wants to integrate their workflow of getting feedback
from colleagues on a presentation in development and publishing the resulting 
presentation, using their Solid pod.