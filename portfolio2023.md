**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2023-2021](https://bleunguts.github.io/bleunguts/portfolio2023)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)** 
# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2021 – 2023._

# (Credit Suisse) Counterparty Credit Risk CVA desk

_ **Period** __:_ May '22 – Apr '23

_ **Length** __:_ 1 year

_ **Team Members** _ **:** 8 Analyst Developers, 1 Project Manager

_ **Technologies** _ **:** C#, ASP.NET Core, Dapper DAO, SpecFlow, SQL Server, SSRS, Redgate SQL

React 7, Jest, Enzyme, Hooks, State management, Pagination, mobx, AG Grid (Group & Pivot, Server-Side chunking), Typescript, Bootstrap, Node JS

In-house .NET business tasks and workflow MessageBus, Primo Server, JANE Quant Analytics, MonteCarlo Valuations

_ **Environments** _ **:** Windows

_ **Methodology** _ **:** User Story-Driven Development, Agile, Micro Services, BDD, TDD

_ **Consultancy Experience:** _ Analyst Developer, Credit Valuation Adjustments, FRTB CVA, Basel III

_ **Description** _ **:**

FRTB CVA technology team works with the bank's distributed risk system including sophisticated risk analysis and reporting functionality, market and trade data interfaces, services to integrate risk analytics engine with the FRTB application layer to comply with the Basel III Regulatory CVA risk requirements.

Main goal of FRTB CVA programme is to capture risk drivers of CVA risk to better align capital standards with accounting practices. The role demanded end-to-end ownership of stories, from technical business analysis incl. breaking down into manageable sub-stories and tickets, full stack development of the React UI, ASP.NET Web API, DB changes, changes to calc workflow and quant analytics layer, triggering valuation batch workflows with carefully configured pricing parameters, manual UI acceptance testing and automated unit tests/BDD Specflow acceptance tests. We were responsible for the cohesive end-to-end full stack delivery of each user story. I must stand behind my delivery and the risk results produced to be ready to answer any questions that arrive from the desk and project management.

Involved with FRTB capital requirements calculation; SA-CVA, BA-CVA calculation methodologies, sourcing of model inputs including risk sensitivities, credit hedges for SA-CVA, Expected Exposure and maturities for BA-CVA, counterparty reference data UI screens (Hedge allocations, Counterparty regions and credit quality), and the rule based 'controls' engine that classifies raw trade populations to the correct calculation methodology.

The role demanded a risk functional background, self-drive, strong sense of ownership, proactive enthusiasm and broad ranging technical abilities working closely with quant analysts, market data, primo infrastructure and project management teams.

_ **Projects** _ **:**

_FRTB Capital Requirements Breakdown story_

Computation of capital requirements is one of the main drivers of FRTB CVA; the trading desk is required to hedge against the huge capital numbers produced in compliance with Basel III. This story required producing portfolio level capital requirements for SA-CVA, BA-CVA for the bank's netting agreements. Ongoing responsibility of this story involved root cause analysis on capital number discrepancies and working with various team members and quants to take to resolution.

- Extended the batch workflow to source hedge allocation reference data and funnelled to the capital calculator (Backend C#, SQL stored procs, Batch workflow XAML)

- Implemented Capital Breakdown UI screen, capital breakdown by legal entity and capital request (Gross Capital, Hedges applied, and Net Capital). (React UI, Backend C#)
- Investigated issue due to incorrect sourcing of hedge risks because the backend sourcing of Accounting CVA trade-level hedges did not account for the fact that FRTB CVA specific calcs aggregate tenors at a yearly level. Fixed backend server to implement correct grouping of risk hedges to be supplied to the capital calc
- Investigating valuation batch workflow pricing parameters to be used to debug quant capital calculator (via COM interop) producing incorrect capital. Fixed by working with team members to fix the pricing model parameters in the pricing configuration store

_FRTB Capital Calculator Hedge Risk verification story_

_This feature exposes key inputs to the capital calculator__for a capital batch_

- Implemented the Hedge Verification MI screen that exposed credit spread hedges, credit quality per netting set (key model inputs to the capital calculator). (React, Backend C#)
- Involved understanding and execution of capital calc workflows for testing, analysing valuation snapshot cache service for correct calc input parameters for the COM interop quant capital calculator
- Implemented the sourcing of published reference data (credit quality, region) in the backend and conducted thorough user acceptance testing simulating trader usage of the UI to assign and publish credit quality, region to cpty for the valuation batch and the analytics to process (Backend C#, SQL)

_Exclusion by book routing rule story_

Implemented Exclusion by book control which allowed the business to run capital calcs with certain trading books routed to BA or excluded totally to capture diffs in capital numbers for business impact analysis.

- Implemented Book Exclusion UI screen to allow users to route trading books to BA-CVA or excluded (React)
- Enhanced trade loading sub-workflow by extending TRADES interface to support books and added a new control to route selected books to the assigned valuation methodology. Gained experience through thorough user acceptance testing; setting up book sourcing, netting set enrichment with the TRADES interface (Backend C#, Analytics workflow, SQL)
- Enhanced netting set trade drill down screen to expose book column for the business to verify the calc methodology post routing

_IMM EE Curve story_

Implemented EE curve sourcing (a key input to the BA-CVA calc)

- Implemented a popup dialog that displays EE curve data up to fifty future horizon dates. Overcame user design challenges faced due to high volume of curve data by discussing with team resulting in a single curve per netting set design, driven by modifying the netting set-\>drill into screen. (React UI, Backend C#)
- Extended backend changes and batch workflow to source EE curves from the in-house EPE REST service
- Implemented batch comparison that compare EE curves between batch runs

_React AG-GRID risk summary story_

Spearheaded UI innovation to leverage the features of commercial AG-GRID group & pivot, advanced excel exports, server-side chunking to address the real technical challenge of huge capital data sets (10 million record set). We piloted the innovation by converting FRTB CVA risk results summary page with success and not only were we able to build out the capital requirements screen efficiently, it gave the desk ability to address advanced reporting needs with AG-GRID group and pivots. (React 7 tables, AG-GRID)

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
- Commended for having proactive drive, tenacity and working with internal and external team members (as knowledge was scattered) for the successful set up of the risk system ecosystem to run on a local PC. (Launching the following: cluster of calc workers, in-house kubernetics service discovery/management service, valuation snapshot server, results server, risk and trades SQL DBs, and analytics pricing/system configs in order to achieve successful FRTB CVA valuation batch execution. Delivered confluence documentation and acted as go to support for local env runs as per necessary.

# (Credit Suisse) Giraffe Real Time Intraday Risk

_ **Period** __:_ Sep '21 - Mar '22

_ **Length** __:_ 6 month

_ **Team Members** _ **:** 5 developers, 6 Business Analysts / Project Managers

_ **Technologies** _ **:** C#, WPF, .NET 4.7.2, Redis Cache 6.0, Nancy IoC, .NET sockets, Google ProtoBuf, Windows Service, SQL 18, Consul

Java/C# real-time OLAP relational algebra library, GoLang, Kotlin, Scala, Postgres, Linux, Openshift, Kubernetes, GIT feature branches, Shell scripting

_ **Environments** _ **:** Windows / Linux / OpenShift/Kubernetes for Linux

_ **Methodology** _ **:** Scrum/Agile, Pair Programming, Micro-services, Legacy code patterns

_ **Consultancy Experience** _: Risk system rationalisation & system integrations, Ticking OLAP relational table transformations, incomplete testing and lengthy releases

_ **Description** _ **:** GRT is recognised as the banks unifying intraday platform for Equities and Rates; boasting simplicity, regular, consistent and automated tested releases, the gold standard of best utilization of the CS ticking OLAP relational algebra platform that is responsible for processing huge streams of financial data sets in real-time.

This programme involved migrating CS's FX intraday system that also publishes real-time P&L for spot/forwards/spot ladder but for the FX market into the wider and larger GRT ecosystem.

Deemed as an unprecedented challenge by senior members, the FX system used a different banks quant stack, FX (C#/Java/Windows) being more tightly coupled to the quant (.NET interface) thus requiring Risk functional expertise with the strategic GRT (Java/Golang/C#/Linux) which is loosely coupled to quant stack via (JSON to C#). Also, the difference in the velocity of trading in FX and the huge volumes (3 million trades per day) posed a significant technical challenge, additionally the assumed no-downtime phased releases to ensure operational stability for the FX desks world-wide (30 traders Zurich alone, 90+ users globally).

The scope for Phase 1 required lifting the real-time risk results aggregation engine, the cluster of real time CS OLAP services from the FX windows platform (40+ Windows servers) and build it into the GRT Linux shell (80+ linux hosts). This involved development work in porting table shapes, projections, filters, pivots into the GRT shell (Java/Scala/GoLang), extending the GRT WPF UI service discovery comms layer to hook into these new backend services (WPF/ C#) and modifications to the FX RiskServer to support the transport piping to redis cache in Linux and the direct transport pipe from RiskServer to the new Linux OLAP services (C#/Google ProtoBuf GRPC/Java).

In addition we implemented a regression system validates risk numbers cross environments, i.e. Windows vs Linux excelling development effort by cherry picking GRT regression components/ patterns (GoLang, Java/Scala, Openshift/Kubernetes).

_ **Projects** _ **:**

_Risk Server migration_

The purpose is to migrate the main risk engine (Risk Server, C# WebApi) that serves risk results to the WPF UI through the CS OLAP services cluster via its various connectors (Grpc connector to RiskServer/Db and Redis). Included migrating and porting sourcing/pivots/groupings/aggregations table definitions which are written in CS OLAP DSL.

- Paired with colleague to decouple the risk data streaming into a new GrpcServer component (C# WebApi/SQL)
- Extended the WPF UI communications layer to discover the new Linux servers based on a user whitelist to facilitate a staged release, Implemented external test to find root cause and fix efficiently to overcome the challenge of ticking UI data streams (C#, WPF, Consul)
- Extended transformer that code generates Java classes, OLAP DSL table definitions (1,000+ risk value table shape, joins/filters, projections, aggregation) from the FX system (GoLang)
- Worked with the team domain experts to configure trade loading, spot ladder, 'On demand risk runs' (separate code path) and various core risk reports (FX Spot/Forward and the Spot Ladder report) for post migration testing. Reported surfaced issues with team for further development fixes.
- Refactored RiskServer components to support Nancy IOC (C# Backend, Nancy)
- Root cause analysis on GrpcServer hanging on shutdown using memory dumps and VS Parallel Task view

_Automated Regressions_

The regression system was built with a GoLang runner that triggers regression workers (Scala/Java) on OpenShift/Kubernetes to perform diffs between risk sets in two environments. The regression run results are stored in Postgres and visualized in Kotlin Ktor Web UI.

- Implemented enhancement to Regression Workers to handle Grpc connectivity between RiskSources (In-house OLAP DSL)
- Resolved challenge with huge volumes (3 million data set) when regressing single currency ladder reports by implement regression runners in Openshift/Kubernetes. Configured new workers on the openshift platform and tuned memory consumption to get these heavy regression runs to work (GoLang, Openshift)
- Resolved challenge where regression runs timed out after 6 hours, implemented chunking strategy of reports so that RegressionWorkers can process the load in chunks broken down by sub report types. (Scala)