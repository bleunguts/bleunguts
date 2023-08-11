**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2023-2021](https://bleunguts.github.io/bleunguts/portfolio2023)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)** 
# PORTFOLIO

_This section outlines the projects I have been involved in during the period 2021 – 2023._


# (Credit Suisse) Counterparty Credit Risk CVA desk 

**_Period:_** May ’22 – Apr ‘23

**_Length:_** 1 year

**_Team Members<span style="text-decoration:underline;">:</span>_**  8 Analyst Developers, 1 Project Manager

**_Technologies<span style="text-decoration:underline;">:</span>_**  C#, ASP.NET Core, Dapper DAO, SpecFlow, SQL Server, SSRS, Redgate SQL 

React 7, Jest, Enzyme, Hooks, Router, State management, Pagination, mobx, AG Grid (Group & Pivot, Server-Side chunking), Typescript, Bootstrap, Node JS

In-house .NET business tasks and workflow MessageBus, Primo Server, JANE Quant Analytics, MonteCarlo Valuations

**_Environments<span style="text-decoration:underline;">:</span>_** Windows

**_Methodology<span style="text-decoration:underline;">:</span>_** User Story-Driven Development, Agile, Micro Services, BDD, TDD

**_Consultancy Experience: _**Analyst Developer, Credit Valuation Adjustments, FRTB CVA, Basel III

**_Description<span style="text-decoration:underline;">: </span>_** FRTB CVA technology team works with the bank’s distributed risk system including sophisticated risk analysis and reporting functionality, market and trade data interfaces, services to integrate risk analytics engine with the FRTB application layer to comply with Basel III Regulatory CVA risk requirements.

Main goal of FRTB CVA programme is to capture risk drivers of CVA risk to better align capital standards with accounting practices.  The role demanded end-to-end ownership of stories, from technical business analysis incl. breaking down into manageable sub-stories and tickets, to the full stack development of the React UI, ASP.NET Web server, DB changes, extending quant analytics libraries layer to support new calcs, configuring pricing parameters and triggering valuation batch workflows, manual UI verification to completion with automated unit tests/BDD Specflow acceptance tests. We were responsible for the cohesive end-to-end full stack delivery of each user story.  I must stand behind my delivery and the produced risk results to be ready to answer any questions that arrive from the desk and project management.

Involved with FRTB capital requirements calculation and the necessary SA-CVA, BA-CVA CVA calculation methodologies (Basel III), sourcing of model inputs which included risk sensitivities, credit hedges for SA-CVA, Expected Exposure and maturities for BA-CVA, building out counterparty reference data UI screens (Hedge allocations, Counterparty regions and credit quality), and the rule based ‘controls’ engine that classified raw trade populations to their corresponding calculation methodology.

The role demanded a risk functional background, self-drive, a strong sense of ownership, proactive enthusiasm and broad ranging technical abilities working closely with quant analysts, market data, primo infrastructure and project management..  

**_Projects<span style="text-decoration:underline;">:</span>_**

**_FRTB Capital Requirements Breakdown story_**

Computation of capital requirements is one of the main drivers of FRTB CVA, the trading desk is required to hedge against the huge resultant capital numbers produced in conjunction with Basel III.  This story required producing portfolio level capital requirements for SA-CVA, BA-CVA for the bank’s netting agreements.  Ongoing responsibility of this story involved root cause analysis on capital number discrepancies.
* Extended the batch workflow to source hedge allocation reference data to be funnelled into the capital calculator (Backend C#, SQL stored procs, Batch workflow XAML)
* Implemented Capital Breakdown UI screen which breaks down capital by legal entity and capital request, Gross Capital, Hedges applied, Net Capital (React UI, Backend C#)
* Investigated issue due to incorrect sourcing of hedge risks because the backend logic for sourcing trade-level risk hedges from Accounting CVA did not take into account that in FRTB CVA tenors should be aggregated at yearly level. Fixed backend server to implement correct grouping of risk hedges to be supplied to the capital calc
* Resolved issues with incorrect pricing parameters issue, which required a combination of investigating valuation batch workflow parameters and debugging quant calculators (via COM interop) with supplied parameters.   Discussed with team and fixed by changing pricing model parameters in the pricing configuration store

**_FRTB Capital Calculator Hedge Risk verification story_**

This feature exposes hedge risk trades, credit quality reference data per netting set for a capital calc batch, key inputs to the capital calculator.
* Implemented the Hedge Verification MI screen that exposed credit spread hedges, credit quality per netting set (key model inputs to the capital calculator).  (React, Backend C#)
* Involved understanding and execution of capital calc workflows for testing, analysing valuation snapshot cache service for correct calc input parameters for the COM interop capital calculator quant libs 
* Implemented backend logic to source published reference data (credit quality, region) and developed deeper understand of business workflow from  inputting credit quality into UI and the sequence of components it gets passed through to be correctly executed in the  valuation batch (Backend C#, SQL)

**_Exclusion by book routing rule story_**

Implemented Exclusion by book control used by the business to run impact analysis, e.g. running capital calcs with certain trading books routed to BA or excluded totally to capture diffs in capital numbers.
* Implemented Book Exclusion UI screen to allow users to route trading books to BA-CVA or excluded  (React)
* Enhanced trade loading sub-workflow by extending TRADES interface to support books and adding a new control to route selected books to correct valuation methodology (Backend C#, Analytics workflow, SQL)
* Enhanced netting set trade drill down screen to expose book column
* Gained understanding and experience in setting up book sourcing, netting set enrichment with the TRADES interface to perform user acceptance testing on changes

**_IMM EE Curve story_**

Implemented EE curve sourcing which is a key input to the BA-CVA calc.
* Implemented a popup screen that displays EE curve data up to fifty future horizon dates.    User design challenges faced due to high volume of curve data, discussed with team and implemented a single curve per netting set design which can be launched via the netting set->drill into screen.  (React UI, Backend C#)
* Implemented batch comparison that compare  EE curves between batch runs 
* Extended backend changes and batch workflow to source EE curves from the in-house EPE service

**_React AG-GRID risk summary story_**

Spearhead UI innovation to leverage the features of commercial AG-GRID group & pivot, advanced excel exports, server-side chunking which addressed a real issue of huge capital requirements data sets (10 million record set).  We piloted the innovation by converting FRTB CVA risk results summary page with success and not only were we able to build out the capital requirements screen efficiently, it gave the desk ability to address advanced reporting needs with AG-GRID group and pivots. (React 7 tables, AG-GRID)
* look and feel changes using ag-grid styles, loading overlay screens using both AG-GRID client side, server-side chunking data models
* designed comparison column templates, baseline/selected/delta which allowed traders to compare data between two batches
* designed custom risk selector cell templates that allowed users to select risk values for different batches
* designed custom counterparty cell template, applies UI styling, and 'Not Found' when no counterparty meta data is found
* designed money cell risk scaling template, number scaling, and RWA scaling can be applied
* designed custom error cell template, applies UI styling, and a clickable link to a popup screen which sourced detailed exception stack information from the back-end.

**_Other features_**
* Implemented Hedge Allocation validation that validated that the counterparty is 100% hedged before user can publish the data for the SA-CVA calculators to consume. (React, C# backend)
* Implemented Risk Selection Modal that allows users to select risk results from a selection of batch runs as inputs for capital batch runs.
* Implemented calc exception drill-in screen that sources detailed exception stack-trace from backend (React, Backend C#)
* Fixed issue with applied controls returning incorrect comparison values (React)
* Enhanced batch comparison screens so that risk values shows column filter (React 7 tables)
* Enhanced RiskService WebApi with dotnet metrics to identify issues with server crashes due to high memory use (Backend C#, dotnet tools visualization)
* Commended for having proactive drive, tenacity and working with internal and external team members (knowledge was scattered) for the successful set up of the risk system ecosystem to run on a local PC.  (Launching the following: cluster of calc workers, in-house kubernetics service discovery/management service, valuation snapshot server, results server, risk and trades SQL DBs, and analytics pricing/system configs in order to achieve successful FRTB CVA valuation batch execution.  Delivered confluence documentation and go to support for other team members.


# (Credit Suisse) Giraffe Real Time Intraday Risk 

**_Period:_** Sep ’21 - Mar ‘22

**_Length:_** 6 month 

**_Team Members<span style="text-decoration:underline;">:</span>_**  5 developers, 6 Business Analysts / Project Managers

**_Technologies<span style="text-decoration:underline;">:</span>_** C#, WPF, .NET 4.7.2, Redis Cache 6.0, Nancy IoC, .NET sockets, Google ProtoBuf, Windows Service, SQL 18, Consul 

Java/C# real-time OLAP relational algebra library, GoLang, Kotlin, Scala, Postgres, Linux, Openshift, Kubernetes, GIT feature branches, Shell scripting

**_Environments<span style="text-decoration:underline;">:</span>_** Windows / Linux / OpenShift/Kubernetes for Linux

**_Methodology<span style="text-decoration:underline;">:</span>_** Scrum/Agile, Pair Programming, Micro-services, Legacy code patterns 

**_Consultancy Experience_**: Risk system rationalisation & system integrations, Real-time OLAP relational table transformations, incomplete testing and lengthy releases 

**_Description<span style="text-decoration:underline;">: </span>_**GRT is recognised as the banks unifying intraday platform for Equities and Rates; boasting simplicity, regular, consistent and automated tested releases, the gold standard of best utilization of the CS real-time OLAP relational algebra platform which is responsible for processing huge streams of financial data sets in real-time every day.

This programme involved migrating CS’s FX intraday system, publishes real-time P&L for spot/forwards/spot ladder but for the FX market into the GRT ecosystem. 

Deemed as an unprecedented challenge of the decade as the FX system and GRT used a different quant stacks, the FX (C#) being more tightly coupled to the quant (C# interface) which requiring Risk functional knowledge whereby the strategic GRT (Java) was loosely coupled to quant stack (JSON to C#). The difference in volumes (3 million trades per day) and velocity of trading in the FX system and the no-downtime requirement from FX desks (30 traders Zurich alone, 90+ users globally) also posed as a significant technical challenge.  

The scope for Phase 1 required lifting the real-time risk results aggregation engine, the cluster of RT OLAP report services from the FX windows platform (40+ Windows servers) and builds it out into the GRT Linux shell (80+ linux hosts).   This involved development work in porting table shapes, projections, filters, pivots into the GRT shell (Java/Scala/GoLang), extending the GRT WPF UI service discovery comms layer to hook into these new backend services (WPF/ C#) and modifications to the FX RiskServer to not only support the new transport pipes to the redis cache, but also changes to the RiskServer to connect to the new Linux servers (C#/Google ProtoBuf GRPC/Java).   

In addition we implemented a regression system validates risk numbers cross environments, i.e. Windows vs Linux excelling development effort by cherry picking GRT regression components/ patterns (GoLang, Java/Scala, Openshift/Kubernetes).

**_Projects<span style="text-decoration:underline;">:</span>_**

**_Risk Server migration_**

The purpose is to migrate the main risk engine (Risk Server, C# WebApi) that served results to the WPF UI through the in-house OLAP library service cluster via its various connectors (Grpc connector to RiskServer/Db and Redis).  Migrated OLAP library service in-house DSL which is responsible for sourcing and feeding ticking slicing and dicing library, pivots/groups/aggregations needed to be ported. 
* Paired with colleague to decouple the risk data streaming into a new GrpcServer component (C# WebApi/SQL)
* Extended the WPF UI communications layer to discover the new Linux servers based on a user whitelist to facilitate a staged release (C#, WPF, Consul)
* Extended transformer that code generates Java classes, OLAP DSL table definitions (1,000+ risk value table shape, joins/filters, projections, aggregation) from the FX system to GRT. (GoLang)
* Worked with domain experts to run risk reports (FX Spot/Forward and the Spot Ladder report) for initial testing in post migration. Gained understanding in Spot Ladder, configuring the Trade Loading setups
* Worked with domain experts on 'On demand risk report runs’ which engages a separate non real-time code path.
* Supported issues with migration with WPF GUI UI ticking data streams, implemented an external test to isolate the root cause, fix issues efficiently
* Refactored RiskServer components to support Nancy IOC
* Root cause analysis on GrpcServer hanging on shutdown using memory dumps and VS Parallel Task view. 

**_Automated Regressions 	_**

The regression system was built with a GoLang runner that triggers regression workers (Scala/Java) on OpenShift/Kubernetes. Diffs are performed on risk results between environments and results stored in Postgres to be displayed in the Kotlin UI .
* Setting up and executing regression runs between environments
* Implemented enhancement to Regression Workers to handle Grpc connectivity between RiskSources (In-house OLAP DSL)
* Resolved challenge with huge volumes (3 million data set) when regressing single currency ladder reports by implement regression runners in Openshift/Kubernetes.  Configured new workers on the openshift platform and tuned memory consumption to get these heavy regression runs to work  (GoLang, Openshift)
* Resolved challenge where regression runs timed out after 6 hours, implemented chunking strategy of reports so that RegressionWorkers can process the load in chunks broken down by sub report types.  (Scala)