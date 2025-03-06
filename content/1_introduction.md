## Introduction
{:#introduction}

<!-- * Integrating Solid in workflows requires intensive knowledge of libraries and programming languages. -->
<!-- * Where BASH allows for straightforward integration in existing workflows, Solid has little tooling to support this. -->
<!-- * We present BashLib as a Solid authentication wrapper for common BASH functionality and Solid-specific additions -->
<!-- * Goal to enable CLI flows to integrate Solid in their workflow -->



The [Solid Protocol](cite:cites sambra_solid_2016) introduced a framework 
for decentralized data storage and sharing, 
empowering users with control over their data in an interoperable web environment.
However, driving integration for Solid into existing workflows remains challenging, 
as its adoption is mainly focused integration in Web applications.
In contrast, many professional and personal workflows are built on exchanging 
data as documents via the command line, which could benefit from the Solid ecosystem
approach to data sharing and integration. However, with Solid integration lacking
the necessary tooling in the command line ecosystem, this remains challenging.

To address this lack of tooling, we introduce BashLib as a command line utility to
integrate Solid authentication and data sharing functionality into the command line ecosystem. 
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