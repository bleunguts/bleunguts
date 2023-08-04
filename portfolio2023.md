**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2023-2021](https://bleunguts.github.io/bleunguts/portfolio2023)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)** 
# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2021 – 2023._

# (Credit Suisse) Counterparty Credit Risk CVA desk

_ **Period** __:_ May '22 – Apr '23

_ **Length** __:_ 1 year

_ **Team Members** _ **:** 8 Analyst Developers, 1 Project Manager

_ **Technologies** _ **:** C#, ASP.NET Core, SQL Server, SSRS, Redgate SQL Compare/ Generator

React 7, Jest, Enzyme shallow Test, Hooks, Router, States, Pagination, Bootstrap, AG Grid (Group & Pivot, Server-Side chunking), mobx, Typescript, Node JS, SSRS

In-house MQ, ChannelConsole, ChannelWorkbench, Primo Workflows, Primo Winforms-, JANE Quant Analytics, MonteCarlo Valuations

_ **Environments** _ **:** Windows

_ **Methodology** _ **:** Agile, Micro Services, TDD, BDD

_ **Consultancy Experience:** _ Analyst Developer, Credit Valuation Adjustments, FRTB CVA, Basel III

_ **Description** _ **:**

Describe XVA and primo CVA desk

Describe FRTB project

We are responsible for the end-to-end delivery of numbers not only just implementation, including close communications with quants

_ **Projects** _ **:**

_FRTB Capital Breakdown epic_

FRTB CVA has a bespoke differs that it doesnt care about risk tenors as it aggregates at trade level, it will source risks from accounting. IIt runs capital calc at the end of the workflow and sourced hedge map, hedge allocation, hedge classification, cpty data from reference data in the workflow. It comes up with huge capital number that traders hedge against that capital calc

- Capital Breakdown UI screen which breaks down capital by corporate divisions
- Cap breakdown screen showing gross capital
- Investigated inconsistent capital numbers and worked with quants to resolve, debugged locally the COM calculator by spiking a test harness.

_FRTB Capital Calculator Hedges Verification epic_

- Implemented the Hedge Verification MI screen which showed Capital Calc hedges
- validates whether hedges run in a batch - hedge routing rules and hedge trades in the batch are correct
- Had to re-run calc workflows risk data for sa calc, imm SA-CCR is used for BA calc
- Had to investigate calc workflow batches and analytics quant calls to ensure risk data as sourced properly, market environment that is built is built properly Risk Inputs, Deltas sources from RS (Results Service)

_Exclusion by book control epic_

Implemented Exclusion by book control used by global market risk team to run impact analysis

- changes to primo trade loading workflow to filter out books, required wiring from TRADES interface into controls microservice and saved to database
- full UI changes to allow books to be exclusion
- Modified netting set -\> trades in a batch screen to show book field
- backend changes to save exclusion rule
- Acquired deep understanding of book sourcing, enriching netting set data with TRADES api

_IMM EE Curve epic_

Initial Margin mandates cpty post collateral against bilateral OTC derivs.

Initial Margin Model invokes CRMD EE Profile in JSON format with EE Values per IMM netting agreement. Draw 100 year curve of exposure 50 horizon dates

- Added hyper link BA-CVA drill down screen of netting set when user clicks EE Profile to bring up this new modal shows table of EE Curve
- React table design and batch comparison
- backend changes of sourcing IMM risk data from Primo EPE service

_React AG-GRID risk summary epic_

Spearhead UI innovation to use AG-GRID leveraging on the benefits of group & pivot, server-side chunking of huge capital data sets advanced excel exports, we enabled the core FRTB CVA risk results summary page giving trading the ability to pivot on netting set enhancing their managerial reporting efficiencies. We made capital reporting possible because it house 10,000,000 records

  - Fixed CSS checkboxes
  - designed custom risk selector cell templates which can be applied as a column template to new columns
  - designed custom counterparty cell template which shows 'Not Found' when downstream systems did not contain counterparty meta data
  - designed custom error cell template which can be applied as a column template to new columns to inherit a way to popup a detailed error modal with detailed stack information of the error message
  - designed money cell risk scaling template which can be applied
  - designed comparison column templates, baseline/selected/delta which allowed traders to compare two batches
  - react grid look and feel changes
  - designed overlay for loading screen
  - debugging UI cells in React using Cell tags

_Features_

  - Implemented Hedge Allocation feature by adding validation to prevent same hedge and counterparty to be duplicated, validate total hedges per cpty allocate to 100% allocated per counterparty before publication for the quant SA-CVA calcs. (React, C# backend changes)
- Implemented Risk Selection Modal that allows users to select risk CVA, SA-CCR, IMM EAD risk from different batches and follows the workflow to re-run capital calc based on those selected risk. Shows pending state in capital run, and after kicking off a run the state management changes to run. Had to investigate how risks are sourced based on RiskReport and how the valuation workflow calcs those risks

- Implemented quant calc exception popup that sources exceptions from backend
- Fixed issue with applied controls returning wrong numbers for comparison folder
- Fixed issue with missing reference data deleting entity screen
- Fixed issue with csv export by migrating to ag-grid
- Fixed defect with Controls validation of controls
- Extended batch comparison screens so that risk values show column filter
- Added dotnet metrics to the RiskService to identify issues with high memory use, analysed with dotnet tools visualization
- Enhanced Publishing reference data to file share so it can be sourced via the analytics

# (Credit Suisse) Giraffe Real Time Intraday Risk

_ **Period** __:_ Sep '21 - Mar '22

_ **Length** __:_ 6 month

_ **Team Members** _ **:** 5 developers, 6 Business Analysts / Project Managers

_ **Technologies** _ **:** C#, WPF, .NET 4.7.2, Redis Cache 6.0, Nancy IoC, .NET sockets, Google ProtoBuf, Windows Service, SQL 18

Java/C# real-time OLAP relational algebra library, Scala, Scala Futures, GoLang, Kotlin, Postgres, Linux, Openshift, Kubernetes, GIT feature branches, Shell scripting.

_ **Environments** _ **:** Windows /Linux / Linux OpenShift/Kubernetes

_ **Methodology** _ **:** Scrum/Agile, Pair Programming, Micro-services, Legacy code patterns

_ **Consultancy Experience** _: Systems integration risk system rationalisation, Real-time ticking table transformations, solving business delivery issues due to incomplete testing and lengthy releases

_ **Description** _ **:** GRT is recognised as the banks unifying intraday platform (Equities and Rates) boasting simplicity, regularly automated and tested business deliveries and the gold standard of best utilization of the bank's real-time OLAP relational algebra library which processes huge streams of financial data in real-time per day to be presented to trading as a WPF UI.

Phase 1 of the risk rationalization programme involved conceptualizing and migration the raptor, the FX Spot & Forwards & Options as well as Spot Ladders, real-time P&L and spot and forwards prices publishing into the wider strategic GRT's ecosystem.

This was a precedent challenge migrating Raptor which utilizes a different quant analytic stack (functional domain knowledge required, coupled with quant analytics libs) into GRT (looser coupled, tech first, quant second stack) whilst ensuring continual functioning FX desks (30 traders Zurich alone, 90+ users globally) which presented a different challenge of handling 3 million trades per day, and also different sourcing of risk number (direct Grpc tunnels, Redis, via RiskServer) depending on the velocity of trading.

We were responsible for analysing and lifting the risk server, the orchestrating component that streams risk results into the real-time OLAP relational platform hosted on 40+ windows hosts into GRT's OLAP platform 80+ linux hosts in a staged, no-downtime in order to keep the business features online. This involved porting table shapes, projections, filters, pivots into the GRT shell (Java/Scala/GoLang), extending the GRT WPF UI service discovery comms layer to hook into these new backend services (WPF/ C#) and modifications to the RiskServer employ Google ProtoBuf / GRPC connectivity to the Redis cache.

To conclude the delivery of Phase 1, we implemented a risk results regression system that allowed us to validate risk numbers from windows to linux (leveraging some of GRT's regression techniques) to predominantly address historical FX desk concerns of incomplete testing and lengthy release processes. (GoLang, Java/Scala, Openshift/Kubernetes)

_ **Projects** _ **:**

_Risk Server migration_

The purpose is to migrate the main risk engine (Risk Server, C# webapi) that served results to UI via RiskAggregation lib via direct Grpc, Redis that also provided users real-time risk results streaming with on-the-fly slicing and dicing (filter,pivots,agg implemented with the in-house DSL)

- Implement changes to RiskServer to decouple the risk streaming module into its own GrpcServer component (C# WebApi)
- Extended GrpcServer discovery to work with WebU by implementing consul discovery layer into server
- Refactored and added IoC containerization in Nancy for RiskServer components
- Extended transformer that code generates the RiskAggregation lib DSL table definitions (1,000+ risk value table shape, joins/filters, projections, aggregation) from FX system to GRT. (GoLang)
- Extended the WPF UI comms layer to discover the new linux servers based on a user whitelist to facilitate a staged release (C#, WPF)
- Worked with domain experts to learn how to run risk reports (FX Spot/Forward and the Spot Ladder report) to figure out to validate risk numbers as a post migration test. Setup Ladder, PLExplain report to test changes which required understanding and configuring Trade Loading, Model Parameter setups and making sure valuationDependences were published correctly by the TradeCoordinator
- Supported issues with migration with WPF GUI UI ticking data streams, implemented an external test to isolate the root cause, fix the issue and build it into the release pipeline.
- Worked with domain experts on 'On demand risk report runs'
- Root cause analysis on GrpcServer hanging on shutdown using memory dumps and VS Parallel Task view. Developed a test rig to reproduce and resolve the issue to do with too many open tcp connections causing a sync lock issue.
- Investigated and fix OLAP library JDBC connection issue (RiskAggregation lib, Java Linux)

_Automated Regressions_

Regression consisted of GoLang runner which triggers Regression Workers that operate on OpenShift/Kubernetes to perform diffs between risk results for the old system compared with the new system

- Extended the regression system to handle windows risk aggregation servers vs linux risk aggregation servers
- Implemented enhancement to Regression Workers to handle Grpc connectivity between RiskSources
- Resolved challenge when regressing single currency ladder reports (3 million data set like helped setup regressions onto openshift platform and scaled the RegressionWorker processes up with careful tuning of memory to solve this issue
- Resolved challenge where regression runs timed out after 6 hours, implemented chunking strategy of reports so that RegressionWorkers can process the load in chunks broken down by sub report types