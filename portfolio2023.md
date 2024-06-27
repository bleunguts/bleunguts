**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2023-2021](https://bleunguts.github.io/bleunguts/portfolio2023)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)** 
# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2021 – 2023._

# (Credit Suisse) Counterparty Credit Risk CVA desk

_ **Period** __:_ Mar '22 – Apr '23

_ **Length** __:_ 1 year

_ **Team Members** _ **:** 8 Analyst Developers, 1 Project Manager

_ **Technologies** _ **:** C#, ASP.NET Core, Dapper DAO, SpecFlow, SQL Server, SSRS, Redgate SQL

React 7, Jest, Enzyme, Hooks, State management, Pagination, mobx, AG Grid (Group & Pivot, Server-Side chunking), Typescript, Bootstrap, Node JS

In-house .NET business tasks and workflow MessageBus, Primo Server, JANE Quant Analytics, MonteCarlo Valuations

_ **Environments** _ **:** Windows

_ **Methodology** _ **:** User Story-Driven Development, Agile, Micro Services, BDD, TDD

_ **Consultancy Experience:** _ Analyst Developer, Credit Valuation Adjustments, FRTB CVA, Basel III

_ **Description** _ **:**

The FRTB CVA technology team integrates the bank's distributed risk analytics engines with the FRTB application layer to meet Basel III Regulatory CVA risk requirements. 

Main goal of FRTB CVA programme is to capture risk drivers of CVA risk to better align capital standards with accounting practices. (credit risk analysis, risk reporting, market data interfaces and trade data interfaces)

[Responsiblities:](#)
The role demanded end-to-end ownership of stories, from technical business analysis (breaking down tasks into manageable sub-stories and tickets), full-stack development (React UI, ASP.NET Web API, DB changes, changes to calc workflow and quant analytics layer), triggering calculation workflow & batch management carefully configured pricing parameters and manual UI acceptance testing and automated unit tests/BDD Specflow acceptance tests. Ensured cohesive end-to-end delivery of each user story. 
I must stand behind my delivery and the risk results produced to be ready to answer any questions that arrive from the desk and project management.

[Involvement:](#)
Worked on FRTB capital requirements calculation, including SA-CVA and BA-CVA methodologies. Responsibilities included sourcing model inputs such as risk sensitivities, credit hedges for SA-CVA, Expected Exposure and maturities for BA-CVA, and managing counterparty reference data UI screens (hedge allocations, counterparty regions, and credit quality). Also, managed the rule-based 'controls' engine to classify raw trade populations for the correct calculation methodology.

[Skills Required:](#)
The role demanded a risk functional background; the understanding of risk management principles and calculations, self-drive and ownership; proactive enthusiasm and sense of responsiblity, broad technical abilities; including working closely with quant analysts, market data folks, primo infrastructure and project management teams.

The role demanded a comprehensive understanding of FRTB capital requirements, strong analytical skills, and the ability to collaborate effectively with various teams to ensure accurate and efficient risk calculations and reporting.

_ **Projects** _ **:**

_FRTB Capital Requirements Breakdown story_

[Objective:](#) Computation of capital requirements is one of the main drivers of FRTB CVA; the trading desk is required to hedge against the huge capital numbers produced in compliance with Basel III. Produce portfolio level capital requirements for SA-CVA, BA-CVA against the bank's netting agreements. Ongoing responsibility of this story involved root cause analysis on capital number discrepancies and working with various team members and quants to take issues to resolution.

- Extended batch workflow to source hedge allocation reference data and funnelled it to the capital calculator (Backend C#, SQL stored procs, Batch workflow XAML)
- Implemented Capital Breakdown UI screen, displaying capital breakdown by legal entity and capital request (Gross Capital, Hedges applied, and Net Capital). (React UI, Backend C#)
- Investigated and fix issues with the hedge risks backend sourcing of Accounting CVA trade-level hedges did not account for the fact that FRTB CVA specific calcs aggregate tenors at a yearly level. Fixed backend server to implement correct grouping of risk hedges to be supplied to the capital calc
- Investigating valuation batch workflow pricing parameters to be used to debug quant capital calculator (via COM interop) producing incorrect capital. Fixed by working with team members to fix the pricing model parameters in the pricing configuration store

_FRTB Capital Calculator Hedge Risk verification story_

[Objective:](#) Expose key inputs of the capital calculator for capital calculation batch runs to end users

- Implemented Hedge Verification MI screen exposing key inputs of the capital calculator such as credit spread hedges, credit quality per netting set. (React, Backend C#)
- Involved understanding and execution of capital calc workflows for testing, analysing valuation snapshot cache service for correct calc input parameters for the COM interop quant capital calculator
- Implemented the sourcing of published reference data (credit quality, region) in the backend and conducted thorough user acceptance testing simulating trader usage of the UI to assign and publish credit quality, region to cpty for the valuation batch and the analytics to process (Backend C#, SQL)

_Exclusion by book routing rule story_

[Objective:](#) Enable the buesiness to run capitcal calculations with specific trading books routed to BA-CVA or excluded for impact analysis scenarios.

- Implemented Book Exclusion UI screen to allow users to route trading books to BA-CVA or excluded (React)
- Enhanced trade loading sub-workflow by extending TRADES interface to support books and added a new control to route selected books to the assigned valuation methodology. Gained experience through thorough user acceptance testing; setting up book sourcing, netting set enrichment with the TRADES interface (Backend C#, Analytics workflow, SQL)
- Enhanced netting set trade drill down screen to expose book column for the business to verify the calc methodology post routing

_IMM EE Curve story_

[Objective:](#) Source EE curve data, a key input to the BA-CVA calculation

- Implemented a popup dialog that displays EE curve data up to fifty future horizon dates. Overcame user design challenges faced due to high volume of curve data by discussing with team resulting in a single curve per netting set design, driven by modifying the netting set-\>drill into screen. (React UI, Backend C#)
- Extended backend changes and batch workflow to source EE curves from the in-house EPE REST service
- Implemented batch comparison that compare EE curves between batch runs

_React AG-GRID risk summary story_

[Objective:](#) Innovate the UI to leverage AG-GRID features for managing large capital data sets efficiently.  Huge capital data sets (10 million record set)

[Respnsiblitilies:](#) Spearheaded UI changes using AG-GRID group & pivot, advanced excel exports, server-side chunking (vast data sets). We piloted the innovation by converting FRTB CVA risk results summary page with success and not only were we able to build out the capital requirements screen efficiently, it gave the desk ability to address advanced reporting needs with AG-GRID group and pivots. (React 7 tables, AG-GRID)

  - look and feel changes using ag-grid styles, loading overlay screens using both AG-GRID client side, server-side chunking data models
  - designed comparison column templates, baseline/selected/delta which allowed traders to compare data between two batches
  - designed various system specific cell templates slashing future development costs for rollout plan for the rest of the UI screens at the same time complying with the UI styling and prompts required by the business (templates included: risk values selector between batches, money cell supporting number/RWA scaling, error cell supporting clickable quant stack trace popup, counterparty cell supporting none found)

_Other features_

  - Implemented Hedge Allocation validation that validated that all counterparties are 100% hedged before publication to SA-CVA calculators. (React, C# backend)
- Implemented Risk Selection Modal that allows users to select risk results from a selection of batch runs as inputs for capital batch runs.
- Implemented calc exception drill-in screen that sources detailed exception stack-trace from backend (React, Backend C#)
- Fixed issue with applied controls returning incorrect comparison values due to flaws in comparison logic (React, Backend)
- Enhanced batch comparison screens so that risk values shows column filter (React 7 tables)
- Enhanced Risk Web Api with dotnet metrics that helped identify high memory usage resulting to server crashes and missing data in UI (Backend C#, dotnet tools visualization)
- Commended for having proactive drive, tenacity and working with internal and external team members (as knowledge was scattered) for the successful set up of the risk system ecosystem to run on a local PC. (Launching the following: cluster of calc workers, in-house Kubernetics service discovery/management service, valuation snapshot server, results server, risk and trades SQL DBs, and analytics pricing/system configs in order to achieve successful FRTB CVA valuation batch execution. Delivered confluence documentation and acted as go to support for local env runs as per necessary.

# (Credit Suisse) Giraffe Real Time Intraday Risk

_ **Period** __:_ Sep '21 - Mar '22

_ **Length** __:_ 6 month

_ **Team Members** _ **:** 5 developers, 6 Business Analysts / Project Managers

_ **Technologies** _ **:** C#, WPF, .NET 4.7.2, Redis Cache 6.0, Nancy IoC, .NET sockets, Google ProtoBuf, Windows Service, SQL 18, Consul

Java/C# real-time OLAP relational algebra library, GoLang, Kotlin, Scala, Postgres, Linux, Openshift, Kubernetes, GIT feature branches, Shell scripting

_ **Environments** _ **:** Windows, Linux, OpenShift/Kubernetes for Linux

_ **Methodology** _ **:** Scrum/Agile, Pair Programming, Micro-services, Legacy code patterns

_ **Consultancy Experience** _: Risk system rationalisation & system integrations, Ticking OLAP relational table transformations, incomplete testing and lengthy releases

_ **Description** _ **:** The GRT platform processes vast streams of financial data in real-time, delivering unified intraday risk results for Equities and Rates. It provides a gold standard in automated, tested releases, leveraging the CS ticking OLAP relational algebra platform to handle immense financial data in real-time.

This program involved migrating CS's FX intraday system which publishes real-time P&L for the FX market (spot/forwards/spot ladder) into the larger GRT ecosystem.

This migration met an unprecedented challenge, the FX system (C#/Java/Windows) used a different quant stack, was tightly coupled to the quant .NET interfaces requring Risk functional expertise compared to the strategic loosely coupled GRT (Java/Golang/C#/Linux) which had a loosely coupled JSON .NET interface to the quant stack. Also, the difference in the velocity of trading and huge volumes (3 million trades per day) in FX posed a technical challenge,topped off with the high availability NFR from the FX desk (30 traders Zurich alone, 90+ users globally).

The scope for this phase of the migration programme involved lifting the real-time risk results aggregation engine from the logical architecture; cluster of RT CS OLAP services on windows (40+ Windows hosts) and building it into the GRT shell (80+ linux hosts). This involved development work in particular porting table shapes, projections, filters, pivots into the GRT shell (Java/Scala/GoLang) to leverage linux stability/easier to scale/powered monitoring, extending the WPF UI service discovery comms layer to hook into these new backend services (WPF/ C#) and modifications to the FX RiskServer to support the transport piping to redis cache in Linux and the direct transport pipe from RiskServer to the new Linux OLAP services (C#/Google ProtoBuf GRPC/Java).

In addition we implemented a regression system validating risk numbers cross environments (Windows vs Linux) leveraging GRT regression components and patterns (GoLang, Java/Scala, Openshift/Kubernetes).

_ **Projects** _ **:**

_Risk Server migration_

[Objective:](#) Migrate components of the main risk engine (Risk Server, C# WebApi) that serves risk results to the WPF UI via its various connectors (through the CS OLAP services cluster including DB/Redis, Grpc connector to RiskServer).

-  Migrated and ported sourcing/pivots/groupings/aggregations table definitions written in CS OLAP DSL.
- Paired with a colleague to decouple the risk data streaming into a new GrpcServer component (C# WebApi/SQL)
- Extended the WPF UI communications layer to discover the new Linux servers based on a user whitelist, facilitating a staged release. 
Implemented external test to find root cause and fix efficiently to overcome the challenge of ticking UI data streams (C#, WPF, Consul)
- Extended a transformer that code generates Java classes, OLAP DSL table definitions (1,000+ risk value table shape, joins/filters, projections, aggregation) from the FX system (GoLang)
- Worked with domain experts to configure trade loading, spot ladder, 'On demand risk runs' (alternative code path) and various core risk reports (FX Spot/Forward and the Spot Ladder report) for post-migration testing. Reported issues for further development fixes.
- Refactored RiskServer components to support Nancy IOC (C# Backend, Nancy)
- Conducted root cause analysis on GrpcServer hang-ups during shutdown using memory dumps and VS Parallel Task view

_Automated Regressions_

[Objective:](#) Extend the regression system built with a GoLang runner that triggers regression workers (Scala/Java) on OpenShift/Kubernetes to perform diffs between risk sets in two environments to support new FX rec runs. The regression run results are stored in Postgres and visualized in Kotlin Ktor Web UI.

- Address the challenge of regressing large data sets (3 million data rows) when regressing single currency ladder reports by implementing regression runners on Openshift/Kubernetes and tuning the openshift platform based on measured memory consumption (GoLang, Openshift)
- Resolved timeout issues with regression runs exceeding 6 hours by implementing a chunking strategy for reports (by sub-report types), enabling RegressionWorkers to process large runs reliably (Scala).