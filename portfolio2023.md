**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2023-2021](https://bleunguts.github.io/bleunguts/portfolio2023)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)** 
# PORTFOLIO

_This section outlines the projects I have been involved in during the period 2021 – 2023._


# (Credit Suisse) Counterparty Credit Risk CVA desk 

**_Period:_** May ’22 – Apr ‘23

**_Length:_** 1 year

**_Team Members<span style="text-decoration:underline;">:</span>_**  8 Analyst Developers, 1 Project Manager

**_Technologies<span style="text-decoration:underline;">:</span>_**  C#, ASP.NET Core, Dapper DAO, SpecFlow, SQL Server, Redgate SQL 

React 7, Jest, Enzyme, Hooks, Router, States, Pagination, mobx, AG Grid (Group & Pivot, Server-Side chunking), Typescript, Bootstrap ,Node JS, SSRS 

In-house .NET business tasks and workflow MessageBus, Primo Server, JANE Quant Analytics, MonteCarlo Valuations

**_Environments<span style="text-decoration:underline;">:</span>_** Windows

**_Methodology<span style="text-decoration:underline;">:</span>_** Agile, Micro Services, TDD, BDD

**_Consultancy Experience: _**Analyst Developer, Credit Valuation Adjustments, FRTB CVA, Basel III

**_Description<span style="text-decoration:underline;">: </span>_**

FRTB CVA technology team works with the bank’s distributed risk system including sophisticated risk analysis and reporting functionality, market and trade data interfaces, services to integrate risk analytics engine with FRTB trading application layer to achieve Basel III Regulatory CVA requirements.

Main goal of FRTB CVA programme is to capture risk drivers of CVA risk to better align capital standards with accounting practices.  The role demanded end-to-end ownership of stories, from the technical business analysis and dividing business reqs into manageable tickets, full stack dev from the React UI, ASP.NET server-side, db changes, enhancing analytics layer to support new calcs, setting up pricing parameters and execution of valuation batch workflows, manual UI testing, sealing it off with automated unit tests/BDD Specflow acceptance tests. We were responsible for the cohesive end-to-end full stack delivery of each cohesive story.  I must stand behind my delivery and the produced risk results to be ready to answer any questions that arrive from the desk and senior management.

I was involved with the development of FRTB capital requirements calculation, the corresponding regulator CVA calculations of SA-CVA, BA-CVA (Basel III), the sourcing of model inputs, risk sensitivities, hedges for the SA-CVA methodology, Expected Exposure and maturities for the BA-CVA calc, associated counterparty reference data user input screens (Hedge allocations, Cpty regions and credit quality), and the rule based engine that classify trade populations to the relevant calculation methodology.

The role demanded risk functional background, self-drive, strong sense of ownership, proactive enthusiasm and broad ranging technical abilities to work closely with quant analysts, market data and the trading desk.  

**_Projects<span style="text-decoration:underline;">:</span>_**

**_FRTB Capital Requirements Breakdown story_**

Computation of capital requirements is one of the main drivers of FRTB CVA, trading is required by regulators to hedge against the huge capital numbers produced.  This story required producing portfolio level capital requirements for SA-CVA, BA-CVA and combined portfolio level of netting agreements.  Ongoing responsibility of this story involved RCA on the validity of capital numbers produced.



* Implemented enhancements to the batch workflow to source hedge allocation reference data as input to the capital calculator (Backend C#, SQL stored procs, Batch workflow XAML)
* Implemented Capital Breakdown UI screen which breaks down capital by legal entity and capital request level of Gross Capital, Hedges applied, Net Capital (React UI, Backend C#)
* Investigated and implemented fix included incorrectly sourcing hedge risks associated with the logic in the backend sourcing trade-level risk hedges from Accounting CVA not taking account the FRTB CVA requirements of aggregated tenors correctly. Implemented backend server fixes to implement correct grouping of risk hedges
* Investigated issues related to incorrect pricing parameters passed to the valuation batch and debugging techniques which involved evaluating numbers directly with the quant calculators (via COM interop).   Discussed with team and fixed by changing pricing model parameters the pricing configuration store 

**_FRTB Capital Calculator Hedge Risk verification story_**

This feature allowed the desk to verify hedge trade risks, credit quality per capital calc netting set valuation for a valuation batch.  It verifies hedging routing rules, counterparty mappings, and reference data were setup correctly in the UI or via the pricing parameters in the valuation engine.



* Implemented the Hedge Verification MI screen which displays credit spread hedges, credit quality per netting set (model inputs to capital calculator).  (React, Backend C#)
* Involved understanding and running capital calc workflows, analysing input parameters hedged risk sources, cpty reference data by navigating the valuation cache snapshot service and debugging the capital calculator quant libs (COM interop)
* Development challenges was the sourcing of credit quality which required understanding  business workflow of publishing reference data from UI and how it gets picked up by the batch analytics phase.  Implemented logic to source published reference data on the backend (Backend C#, SQL)

**_Exclusion by book routing rule story_**

Implemented Exclusion by book control used by global market risk team to run impact analysis, it allows trading books to be routed to BA / excluded in a batch to understanding capital implications.



* Implemented UI changes to allow users to route trading books to BA-CVA or excluded  (React)
* Enhanced trade loading sub-workflow to filter out books by wiring it from trades the TRADES interface into our controls micro-service (Backend C#, Analytics workflow, SQL)
* Enhanced netting set trade drill down screen to expose book column
* Acquired deeper understanding of book sourcing, netting set enrichment with the TRADES interface

**_IMM EE Curve story_**

Implemented EE curve sourcing, EE & maturities are a key input to the BA-CVA computation.



* Implemented popup that shows EE curve data up to fifty future horizon dates.    The volume of data required discussion of various UI designs to pull a single curve per netting set.  (React UI, Backend C#)
* Implemented batch comparison which allowed traders to compare EE curves between batch runs with different pricing settings
* Extended backend changes in sourcing IMM EE curves from the in-house EPE service with enhancements to the batch workflow

**_React AG-GRID risk summary story_**

Spearhead UI innovation to leverage OTS AG-GRID group & pivot, advanced excel exports, server-side chunking to address the huge volume of expected capital requirements data sets.  We piloted the innovation by converting FRTB CVA risk results summary page with success as it gave the desk ability to pivot data to support reporting needs.  This lay the foundation of capital requirements reporting with expected 10 million record sets. (React 7 tables, AG-GRID)



    * look and feel changes using ag-grid styles, loading overlay screens using both AG-GRID client side, server-side chunking data models
    * designed comparison column templates, baseline/selected/delta which allowed traders to compare two data between batches
    * designed custom risk selector cell templates that allowed users to select risk values for different batches
    * designed custom counterparty cell template, applies UI styling, and 'Not Found' when no counterparty meta data is found
    * designed money cell risk scaling template, number scaling, and RWA scaling can be applied
    * designed custom error cell template, applies UI styling, which shows a link to popup of exception stack details

**_Other features_**



    * Implemented Hedge Allocation validation that ensures hedges allocated per counterparty is 100% hedged before publication for the quant SA-CVA calcs to consume. (React, C# backend)
* Implemented Risk Selection Modal that allows users to select risk results from different batch runs to re-run capital batches scenarios.

    I conducted acceptance testing to verify low-level calcs was sourcing risk results correctly.

* Implemented calc error drill-in screen that sources detailed exception stacktrace from backend (React, Backend C#)
* Fixed issue with applied controls returning wrong numbers for comparison folder
* Fixed issue with missing reference data deleting entity screen (React, SQL)
* Enhanced batch comparison screens so that risk values shows column filter (React 7 tables)
* Enhanced RiskService with dotnet metrics to identify issues with server crashes due to high memory use (Backend C#, dotnet tools visualization)
* Commended for my proactive drive, tenacity and team collaboration (as the knowledge was dispersed around members of the team, and infra teams) for setting up the risk system to run locally.  This included setting up various configs, system, profile, pricing configs and running cluster of calc workers, valuation snapshot server, results server, SQL dbs, and analytics configs to run a batch and price properly.


# (Credit Suisse) Giraffe Real Time Intraday Risk 

**_Period:_** Sep ’21 - Mar ‘22

**_Length:_** 6 month 

**_Team Members<span style="text-decoration:underline;">:</span>_**  5 developers, 6 Business Analysts / Project Managers

**_Technologies<span style="text-decoration:underline;">:</span>_** C#, WPF, .NET 4.7.2, Redis Cache 6.0, Nancy IoC, .NET sockets, Google ProtoBuf, Windows Service, SQL 18 

Java/C# real-time OLAP relational algebra library, Scala, Scala Futures, GoLang, Kotlin, Postgres, Linux, Openshift, Kubernetes, GIT feature branches, Shell scripting.

**_Environments<span style="text-decoration:underline;">:</span>_** Windows /Linux / Linux OpenShift/Kubernetes

**_Methodology<span style="text-decoration:underline;">:</span>_** Scrum/Agile, Pair Programming, Micro-services, Legacy code patterns 

**_Consultancy Experience_**: Risk system rationalisation & System Integrations, Real-time OLAP relational table transformations, solving business delivery issues due to incomplete testing and lengthy releases 

**_Description<span style="text-decoration:underline;">: </span>_**GRT is recognised as the banks unifying intraday platform (for Equities and Rates) boasting simplicity, regular and tested (automated) business deliveries and also known as the gold standard of best utilization of the bank’s real-time OLAP relational algebra lib that processes streams huge financial data sets in real-time per day.

I was involved in ‘Phase 1’ of the risk rationalization programme; migration of the bank’s FX intraday system that also publishes real-time P&L for spot/forwards/spot ladder but for the FX market. 

The migration of FX into the wider GRT ecosystem, was a challenge as it utilized, different quant stack (a tighter coupling with Risk domain knowledge) into GRT (a looser coupled, tech first stack) whilst keeping FX desks worldwide running (30 traders Zurich alone, 90+ users globally).  The difference in volumes (3 million trades per day) and velocity of trading in the FX system also posed as a significant technical challenge.  

We decided to lift the risk server into GRT, the cluster of components that streams risk results into the real-time OLAP relational platform (hosted on 40+ Windows hosts) into GRT’s OLAP relation platform (80+ linux hosts) in a staged, no-downtime manner.  This involved development work in porting table shapes, projections, filters, pivots into the GRT shell (Java/Scala/GoLang), extending the GRT WPF UI service discovery comms layer to hook into these new backend services (WPF/ C#) and modifications to the FX RiskServer to support the transport pipe to the redis cache (Google ProtoBuf  GRPC).   

We addressed the business concerns of irregular, untested releases by implementing a regression system cherry picking GRT components/patterns that validates risk numbers cross environments, in this case Windows vs Linux (GoLang, Java/Scala, Openshift/Kubernetes).

**_Projects<span style="text-decoration:underline;">:</span>_**

**_Risk Server migration_**

The purpose is to migrate the main risk engine (Risk Server, C# WebApi) that served results to the WPF UI through the OLAP relation library to source ticking real-time _risk data_, with on-the-fly pivots, filters, agg ability via various connectors (Grpc connector to RiskServer/Db and Redis).  The on-the-fly slicing and dicing library required us to port the logic using the in-house DSL.



* Paired with colleague to decouple the risk streaming into its own GrpcServer component (C# WebApi/SQL)
* Extended GrpcServer discovery to work with the UI 
* Extended the WPF UI comms layer to discover the new Linux servers based on a user whitelist to facilitate a staged release (C#, WPF)
* Extended transformer that code generates the OLAP relational algebra DSL table definitions (1,000+ risk value table shape, joins/filters, projections, aggregation) from FX system to GRT. (GoLang)
* Worked with domain experts to run risk reports (FX Spot/Forward and the Spot Ladder report) for initial testing in post migration. Gained understanding in Spot Ladder, PLExplain reports, configuring the Trade Loading setups
* Worked with domain experts on 'On demand risk report runs'  which engages a separate code path as it is not a real-time report
* Supported issues with migration with WPF GUI UI ticking data streams, implemented an external test to isolate the root cause, fix issues efficiently
* Refactored RiskServer components to support Nancy IOC
* Root cause analysis on GrpcServer hanging on shutdown using memory dumps and VS Parallel Task view. 

**_Automated Regressions 	_**

The regression system was built with a GoLang runner that triggers regression workers on OpenShift/Kubernetes. Diffs are performed on risk results and flags attention.



* Setting up/instrumentation of regression runs between the old and new environments.
* Implemented enhancement to Regression Workers to handle Grpc connectivity between RiskSources (In-house OLAP DSL)
* Resolved challenge when regressing single currency ladder reports (3 million data sets) by scaling up on Openshift.  Configured new workers on the openshift platform and tuned memory consumption to get these heavy regression runs to work  (GoLang, Openshift)
* Resolved challenge where regression runs timed out after 6 hours, implemented chunking strategy of reports so that RegressionWorkers can process the load in chunks broken down by sub report types.  (Scala)