## Introduction
{:#introduction}

* Integrating Solid in workflows requires intensive knowledge of libraries and programming languages.
* Where BASH allows for straightforward integration in existing workflows, Solid has little tooling to support this.
* Authentication flows exceed the 
* We present BashLib as a Solid authentication wrapper for common BASH functionality and Solid-specific additions
* Goal to enable CLI flows to integrate Solid in their workflow

## Authentication
{:#authentication}

* Solid authentication is the core on which its privacy systems are built.
* Bashlib supports interactive browser login flows
* Bashlib supports hot-swapping authentication sessions on the fly to quickly swap between professional and personal identities.
* As interactive authentication flows are essential for back-end tasks, we support the latest client credentials implementations from both the CSS and ESS implementations.
  
## Authorization
{:#authorization}

* As Solid supports two authorization specifications, we support the management using both specifiations, using the INRUPT AUthentication libraries.
* The AC mechanism is discovered on the fly
* For managing Access Control Resources, we do not support the full suite of functionality yet, only the Universal API by INRUPT tooling.


## Tooling Suite
{:#suite}

* Bashlib supports most of the common tooling
  * curl (authenticated)
  * ls
  * tree
  * cp / mv
  * touch / rm
  * mkdir
  * find - finding specific resources starting from provided root
  * query - (non) federated querying of contained resources starting from provided root
  * edit
  * (access & auth as mentioned above)

## Conclusion
{:#conclusion}

* Bashlib provides the necessary functionality to integrate Solid in CLI workflows.
* Bashlib can perform automated background tasks for multiple profiles.