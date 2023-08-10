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

Enhanced features developed that improved future development effort:



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


# (Credit Suisse) Giraffe Real Time Intraday Risk 

**_Period:_** Sep ’21 - Mar ‘22

**_Length:_** 6 month 

**_Team Members<span style="text-decoration:underline;">:</span>_**  5 developers, 6 Business Analysts / Project Managers

**_Technologies<span style="text-decoration:underline;">:</span>_** C#, WPF, .NET 4.7.2, Redis Cache 6.0, Nancy IoC, .NET sockets, Google ProtoBuf, Windows Service, SQL 18 

Java/C# real-time OLAP relational algebra library, Scala, Scala Futures, GoLang, Kotlin, Postgres, Linux, Openshift, Kubernetes, GIT feature branches, Shell scripting.

**_Environments<span style="text-decoration:underline;">:</span>_** Windows /Linux / Linux OpenShift/Kubernetes

**_Methodology<span style="text-decoration:underline;">:</span>_** Scrum/Agile, Pair Programming, Micro-services, Legacy code patterns 

**_Consultancy Experience_**: Systems integration risk system rationalisation, Real-time ticking table transformations, solving business delivery issues due to incomplete testing and lengthy releases 

**_Description<span style="text-decoration:underline;">: </span>_**GRT is recognised as the banks unifying intraday platform (Equities and Rates) boasting simplicity, regularly automated and tested business deliveries and the gold standard of best utilization of the bank’s real-time OLAP relational algebra library which processes huge streams of financial data in real-time per day to be presented to trading as a WPF UI.

Phase 1 of the risk rationalization programme involved conceptualizing and migration the raptor, the FX Spot & Forwards & Options as well as Spot Ladders, real-time P&L and spot and forwards prices publishing into the wider strategic GRT’s ecosystem.  

This was a precedent challenge migrating Raptor which utilizes a different quant analytic stack (functional domain knowledge required, coupled with quant analytics libs) into GRT (looser coupled, tech first, quant second stack) whilst ensuring continual functioning FX desks (30 traders Zurich alone, 90+ users globally) which presented a different challenge of handling 3 million trades per day, and also different sourcing of risk number (direct Grpc tunnels, Redis, via RiskServer) depending on the velocity of trading. 

We were responsible for analysing and lifting the risk server, the orchestrating component that streams risk results into the real-time OLAP relational platform hosted on 40+ windows hosts into GRT’s OLAP platform 80+ linux hosts in a staged, no-downtime in order to keep the business features online.  This involved porting table shapes, projections, filters, pivots into the GRT shell (Java/Scala/GoLang), extending the GRT WPF UI service discovery comms layer to hook into these new backend services (WPF/ C#) and modifications to the RiskServer employ Google ProtoBuf / GRPC connectivity to the Redis cache.   

To conclude the delivery of Phase 1, we implemented a risk results regression system that allowed us to validate risk numbers from windows to linux (leveraging some of GRT’s regression techniques) to predominantly address historical FX desk concerns of incomplete testing and lengthy release processes.  (GoLang, Java/Scala, Openshift/Kubernetes)

**_Projects<span style="text-decoration:underline;">:</span>_**

**_Risk Server migration_**

The purpose is to migrate the main risk engine (Risk Server, C# webapi) that served results to UI via RiskAggregation lib via direct Grpc, Redis that also provided users real-time risk results streaming with on-the-fly slicing and dicing (filter,pivots,agg implemented with the in-house DSL)



* Implement changes to RiskServer to decouple the risk streaming module into its own GrpcServer component (C# WebApi)
* Extended GrpcServer discovery to work with WebU by implementing consul discovery layer into server
* Refactored and added IoC containerization in Nancy for RiskServer components
* Extended transformer that code generates the RiskAggregation lib DSL table definitions (1,000+ risk value table shape, joins/filters, projections, aggregation) from FX system to GRT. (GoLang)
* Extended the WPF UI comms layer to discover the new linux servers based on a user whitelist to facilitate a staged release (C#, WPF)
* Worked with domain experts to learn how to run risk reports (FX Spot/Forward and the Spot Ladder report) to figure out to validate risk numbers as a post migration test. Setup Ladder, PLExplain report to test changes which required understanding and configuring Trade Loading, Model Parameter setups and making sure valuationDependences were published correctly by the TradeCoordinator
* Supported issues with migration with WPF GUI UI ticking data streams, implemented an external test to isolate the root cause, fix the issue and build it into the release pipeline.
* Worked with domain experts on 'On demand risk report runs' 
* Root cause analysis on GrpcServer hanging on shutdown using memory dumps and VS Parallel Task view.  Developed a test rig to reproduce and resolve the issue to do with too many open tcp connections causing a sync lock issue.
* Investigated and fix OLAP library JDBC connection issue (RiskAggregation lib, Java Linux)

**_Automated Regressions 	_**

Regression consisted of GoLang runner which triggers Regression Workers that operate on OpenShift/Kubernetes to perform diffs between risk results for  the old system compared with the new system



* Extended the regression system to handle windows risk aggregation servers vs linux risk aggregation servers
* Implemented enhancement to Regression Workers to handle Grpc connectivity between RiskSources
* Resolved challenge when regressing single currency ladder reports (3 million data set like helped setup regressions onto openshift platform and scaled the RegressionWorker processes up with careful tuning of memory to solve this issue
* Resolved challenge where regression runs timed out after 6 hours, implemented chunking strategy of reports so that RegressionWorkers can process the load in chunks broken down by sub report types