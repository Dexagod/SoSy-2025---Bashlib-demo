## Conclusion
{:#conclusion}

<!-- * Bashlib provides the necessary functionality to integrate Solid in CLI workflows. -->
<!-- * Bashlib can perform automated background tasks for multiple profiles. -->

In this paper we introduced BashLib, a command-line program that provides 
a base set of utilities to help integrate command-line workflows in the Solid ecosystem.
It provides a simple interface for the management of Solid authentication and authorization
functions and a mapping for commonly used utilities for data management that integrate the Solid protocol.
Supporting both the specification compliant flow and
the implementation dependent token-based flows for authentication,
Bashlib aims to be both future-proof and feature-complete in its implementation.
Similarly, supporting both authorization systems allows integration 
independent of the used server implementation.
This way, BashLib lowers the barrier for developers and systems administrators
to integrate both new and existing workflows into the Solid ecosystem.
