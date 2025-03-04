## Introduction
{:#introduction}

<!-- * Integrating Solid in workflows requires intensive knowledge of libraries and programming languages. -->
<!-- * Where BASH allows for straightforward integration in existing workflows, Solid has little tooling to support this. -->
<!-- * We present BashLib as a Solid authentication wrapper for common BASH functionality and Solid-specific additions -->
<!-- * Goal to enable CLI flows to integrate Solid in their workflow -->



The [Solid Protocol](cite:cites sambra_solid_2016), designed for decentralized data storage and sharing, offers powerful capabilities to enable user-centric data management and ownership in an interoperable Web setting.
However, adoption of the Solid ecosystem into existing workflows remains challenging, mainly due to the reliance on Web-based applications to integrate Solid in their design.
Where existing workflows that exchange data as documents via the command line provide are an interesting target to adopt Solid practices, where these are often already integrated with cloud systems, the availability of Solid tooling for the command line is lacking as Solid’s tooling is primarily designed for web-based applications rather than command-line environments.

In contrast to Web environments, the CLI shell ecosystem provides a straightforward adoption base for Solid to automate integration and sharing of data in an ecosystem, built on simple yet effective scripted workflows. Many existing systems rely on the shell for executing tasks, handling data, and orchestrating processes. 

To address this lack of tooling for Solid in the CLI ecosystem, we introduce BashLib as a lightweight CLI wrapper for Solid functionality in the BASH ecosystem. Bashlib provides functionality for Solid authentication and authorization to manage data sharing in the target ecosystem, while providing functionality for data management to integrate existing data flows, making it more accessible to developers, system administrators, and researchers.

By bridging the gap between Solid and BASH, BashLib aims to facilitate broader adoption of Solid principles in automated workflows, enhancing interoperability and enabling new possibilities for decentralized data management.


