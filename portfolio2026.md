**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2026-2025](https://bleunguts.github.io/bleunguts/portfolio2026)** | **[2023-2021](https://bleunguts.github.io/bleunguts/portfolio2023)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)** 

# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2025 – 2026._

# (CIBC) Swaps Pricing

_ **Period** __:_ May ’25 – May ’26

_ **Length** __:_ 1 year

_ **Team Members** __:_ 2 Quant Devs, 1 Quant Product Lead, 3 Desk Devs, 1 Quant Trader, 1 Desk Dev Lead, 2 Broadway Devs, 2 Platform Devs

_ **Technologies** __:_ C#, .NET 9, ASP.NET Core, nUnit, C++ Analytics Interop, Pricing Object Graph, Solace MQ, SolCache, Bloomberg B-PIPE, SQL, MongoDB, Elastic/Kibana, Grafana, KDB+/q (RDB, IDB, HDB), Excel/xlOil, Python, JavaScript/HTML

_ **Environments** __:_ Windows, Linux containers

_ **Methodology** __:_ Direct Trading Desk interactions, Agile, Micro Services, TDD

_ **Consultancy Experience:** _ Analyst Developer, Quant Developer, IR Swaps Pricing, Yield Curve Construction, e-Trading RFQ

_ **Description** __:_ 

Alma is CIBC’s strategic real-time interest rate swaps pricing platform for the electronic fixed income (e-FI) business. Alma Marks consumes live market data from Bloomberg B-PIPE and trader quotes over Solace, and exposes API endpoints for traders to mark the instruments on the curve in Excel (Python Stack) that feeds the curve build. Alma Pricer builds the CAD O/N curve and a three-curve USD setup (O/N curve, Fed Curve and Basis Curve) with the bank’s C++ analytics library. It streams indicative swap rates across trader-configured sources for curve instruments 1D to 50Y and prices client RFQs, publishing PV, swap rates and first order risk to Bloomberg, and KDB.

Alma went live in late Q3 2025 and replaced the legacy pricer in phases, running in parallel until final cutover in mid-2026. Integrating Alma into the bank’s strategic .NET Platform framework captured reusable components and enhanced battle-tested robustness as it built from the same bank’s strategic risk platform. Key engineering challenges included handling high frequency curve recalibration (input rates updating 10+ times per second against a Bloomberg theoretical cap of four updates per second) while Alma must reprice on every tick yet publish within external system limitations. Additionally running dual pricers in production required complete end-to-end visibility across market data feeds, curve builds, and publishing execution prices, driving the construction of an observability estate (Elastic dashboards, KDB dashboards and Grafana).

[Responsibilities:](#)
Responsibilities spanned technical and business analysis for yield curve building and swap pricing alongside the quant lead and trading desk, translating requirements into structured JIRA stories. Core engineering focused on C# pricing service development, interop integration with the native C++ quant layer, Swagger diagnostic endpoints, and building telemetry dashboards across OpenTelemetry, KDB, and Grafana. Managed promotion across DEV, SIT, UAT, and PROD environments, including weekend release validations and post-release support, driving complete end-to-end delivery of each assigned capability.

[Involvement:](#)
I joined alongside the outgoing quant developer and, after an intensive handover (USD curve specification, CAD bond-to-yield calculations, FOMC meeting dates, monthly bond future rolls, configurable calculators on the calc graph), took over development of Alma. I worked on the curve build and object-graph lifecycle, the core CIBC platform migration, RFQ and portfolio pricing, building new calculators, and curve configuration in a data-event-subscribable MongoDB platform layer. Additionally, I delivered benchmark bond and cheapest-to-deliver rolling in Alma Marks to safeguard pricing accuracy, while building the monitoring estate across KDB/Grafana and Elastic.

[Skills Required:](#)
* **Functional Quant Knowledge:** Yield curve construction (OIS discounting, O/N curve, Fed Curve and Basis Curve multi-curve, central-bank meeting-date jumps, futures convexity adjustments, bond-yield-plus-spread marking for the CAD long end), swap conventions (IMM dates, day counts, fixings, stubs), bond futures and cheapest-to-deliver mechanics, and RFQ workflows.
* **Technical breadth:** Strong C#/.NET background with the ability to debug into native C++ analytics, the capacity to learn new tooling quickly (KDB+/q, Solace, Grafana), self-drive and ownership, and proactive communication across the desk, quants, desk developers, platform, market-data and KDB teams.

_ **Projects** __:_

### PLATFORM Integration

[Delivery Summary:](#)
* **Problem & Context:** Alma required migration onto Platform — the bank’s high-throughput service framework that drives the battle-tested strategic risk system — to leverage standardized request routing and high-frequency Solace messaging. 
* **Architecture & Solution:** Extracted core pricing domain logic into standalone assemblies, refactoring Alma Marks and Alma Pricer to run independently outside Platform during the transition. Configured TeamCity CI/CD pipelines and wired request interfaces to route snap and streaming swap queries across the Platform -> Alma -> Quant Interop -> Solace stack. 
* **Pricing & Business Value:** Delivered the first production release of real-time CAD OIS swap streaming (ON to 30Y) to downstream Fixed Income Trading systems that integrated with Bloomberg. 
* **Key Techniques:** C#/.NET 9 microservice decoupling, Solace PubSub+ multi-VPN connection handling, ASP.NET Core diagnostic Swagger endpoints, and Platform routing-rule optimization. 

[Delivery Journal:](#)
- Refactored the swap pricing domain logic into a deployable assembly, enabling the pricer to be hosted inside the Platform container. (C#, .NET) [May 30]
- Refactored Alma Marks and the Alma Swap Pricer to run standalone outside Platform, and performed curve build smoke-test via Excel UI and solace-utils before merging and promoting through environments, minimizing disruption to existing production and staging BAU activities. (C#, Excel UI, solace-utils) [Jun 20, Jul 4]
- Created the Platform Alma Pricer repository and TeamCity build, establishing end-to-end DevOps automation. (Platform, TeamCity) [Jun 20]
- Wired the request interfaces to Platform and conducted local end-to-end snap swap testing, diagnosing and resolving integration issues across the Platform → Alma → Quant → Solace stack. (C#, Platform, Solace) [Jul 4]
- Promoted services to DEV and resolved infrastructure issues across request routing tables, Elastic logging configuration, web gateways and TeamCity build issues. [Jul 4]
- Implemented Solace e-FICC VPN cutover alongside the MarketFlow team, troubleshooting connection recovery edge cases, producing a reproducible test case for reconnection issues, and coordinating the upgraded VPN/MarketFlow schema rollout across DEV, SIT, UAT, and PROD. (C#, Solace PubSub+) [Jun 13, Jul 4, Jul 11]
- Integrated the Alma Pricer into Platform alongside the platform team across DEV, SIT and UAT, conducting release testing for the initial July 2025 production go-live. [Jul 11]
- Developed ASP.NET Core Swagger endpoints exposing active stream statuses and the latest swap pricing results for real-time stream inspection. (ASP.NET Core, Swagger) [Aug 8]
- Configured Platform Settings and Rules within to setup routing for CAD instances and USD multi instances. (MongoDB, Nucleus) [Jul 25, Aug 8]
- Contributed to architecture designs utilizing Platform's routing-rules model to drive the CAD and USD partitions routing. [Jul 11]

---

### Streaming Curve Build

[Delivery Summary:](#)
* **Problem & Context:** Yield curves recalibrate on every market rate tick (10+ updates/second), driving substantial intraday compute loads during volatility. Alma was required to maintain full pricing consistency across high-frequency updates while publishing within external system caps (Bloomberg theoretical cap of 4 updates/sec). 
* **Architecture & Solution:** Wrapped the Quant Interop YieldCurve builds in C# to support the real-time intraday use case. Standardized full cold bootstraps for morning start-ups and new instruments requiring a rebuild, paired with fast Object Graph updates for incremental single tick movements. Designed and stabilized the stateful T -> T+1 daily reboot lifecycle – resolving a critical bug where stale valuation dates persisted – to flush old states, purge expired object graphs and initialize fresh business-date curve builds. 
* **Pricing & Business Value:** Real-time curve construction across CAD, USD, USD FED, USD Basis setups. Modeled explicit Central Bank meeting-date jumps ensuring accurate curve shape and jump sizes during monetary policy announcements events. 
* **Key Techniques:** C# to native C++ Quant interop, Object Graph lifecycle caching, Visual Studio mixed-mode managed/native debugging, and nUnit state-reproduction tests. 

[Delivery Journal:](#)
- Built a functional prototype of the USD curve specification during onboarding, triaging pricing discrepancies on early-maturity nodes with the trading desk. (C#, Excel Py) [May 30, Jun 13]
- Identified and fixed a wrong Object Graph instantiation defect causing swap prices to resolve to zero. (C#, Quant Interop) [Jun 13]
- Triaged and resolved a bug where AlmaPricer failed to publish 35Y/40Y long-end swap points due to unhandled null mid-price inputs within the pricing pipeline. [Jun 13–20]
- Reinstated forward curve publishing mechanisms from the pricer to aid debugging and visual UI verification. [Jul 4]
- Enhanced Quant call logging, fast-curve utilization tracking, and curve rebuild quote triggers metrics within the pricing engine and exposed to Elastic Dashboards. [Jul 11]
- Resolved an object graph state inconsistency issue occurring when alternating full curve rebuilds with fast OG updates, validating fixes via C# nUnit reproducible tests. (C#, Quant Interop, nUnit) [Jul 18]
- Improved Exotica service test coverage for expired futures during fast curve updates. (nUnit) [Jul 18]
- Investigated and raised for design discussion a race condition between market-data subscription pumps and quote-processing message pumps stabilizing subscription event updates. [Jul 18, Jul 25]
- Triaged the automated T → T+1 nightly restart issue causing curves to build with stale T-1 prices. The restart purges the previous day’s Object Graph (OG), rebuilds a fresh OG for the new business date, performs a FULL curve rebuild, then switches to fast updates. Captured defect in a small C# reproduction test. (C#, Exotica) [Jul 25]
- Extended yield curve building logic to incorporate the Quant CentralBankMeetingDates function, building the meeting-date jumps ObjectGraph table. (C#, Quant Interop) [Nov 14]
- Re-enabled futures convexity adjustments that had been omitted from the yield curve build to fix the pricing regression test failure that I built. [Nov 14]
- Resolved intermittent test failures by pinning the exact valuation timestamp for the Quant Interop test suite. (C#, Quant Interop, nUnit) [Nov 14]
- Authored Quant Service validation tests verifying implied overnight rates across central bank meeting dates to validate jump magnitudes. (C#, Quant Interop, nUnit) [Nov 21]
- Deployed configuration patches removing legacy MeetingDateInterpolation once explicit meeting-date jumps were active in production. [Nov 21]
- Upgraded AlmaPricer to utilize Quant Interop Library’s new GetValuationResult return type to retrieve OG values. [Aug 29]

---

### Market Data & Connectivity

[Delivery Summary:](#)
* **Problem & Context:** Official market quotes for long-end or illiquid swap tenors can become stale or sparse during the trading day, threatening PnL calculation and RFQ quoting accuracy. 
* **Architecture & Solution:** Built a modular pipeline (PartitionRunner -> price stream -> calculation graph) that mirrors the desk's marking spreadsheets. Implemented new custom calculators, including SwapRateFromBondYieldAndSpread, allowing traders to derive swap rates dynamically from underlying bond yields and spreads. 
* **Pricing & Business Value:** Enabled traders to manually mark curves intraday, maintaining continuous, reliable pricing across sparse tenors and safeguarding live RFQ spreads. 
* **Key Techniques:** Event-driven calculator pipelines, automated calculation-graph integration testing, and nUnit pipeline verification. 

[Delivery Journal:](#)
- Integrated the new Solace e-FICC VPN into Alma with the market-data team, triaging breaking platform issues lacking dual VPN support, while investigating Solace connection recovery edge cases with MarketFlow teams and successfully created a reproducible test for the reconnection problem. (Solace PubSub+) [Jun 13 – Aug 15]
- Configured direct Bloomberg B-PIPE ticker subscriptions to debug live curve input behaviour with the desk, isolating B-PIPE/MarketData API session drops in lower environments. BPIPE tools were used to coordinate production BBG subscription lists. (MarketData API, Bloomberg) [Jun 20 – Aug 22]
- Diagnosed and fixed MarketData API price streams entering terminated states during SIT/UAT release testing, filtering invalid Bloomberg CBBT mid-values that caused output invalidations, and implementing SolCache service-restart self-healing recovery routines. (SolCache, MarketData API) [Jul 11 – Sep 26]

---

### Alma Marks Calculators

[Delivery Summary:](#)
* **Problem & Context:** Traders required custom calculation routines to derive curve marks from disparate raw market inputs, particularly when official benchmark quotes were unavailable or sparse.
* **Architecture & Solution:** Built a modular, event-driven calculation engine (Runner -> price streams -> calculation graph) mirroring front-office marking sheets. Implemented specialized calculators like SwapRateFromBondYieldAndSpread and maintained commonly used BondPriceToYield calculator. 
* **Pricing & Business Value:** Empowered traders to manually mark curves intraday with custom spread offsets, maintaining accurate PnL and continuous RFQ quoting across illiquid curve tenors. 
* **Key Techniques:** Directed acyclic graph (DAG) calculation execution, custom C# calculator pipelines, and automated nUnit pipeline verification tests.

[Delivery Journal:](#)
- Developed unit and integration test suites covering the Runner → price stream → calculation graph pipeline, self-documenting how curve configurations drive regional partitions, calculation paths and published metrics. (C#, nUnit) [May 23]
- Participated in CAD and USD marking spreadsheet design reviews with the head Quant Trader and desk developers to analyse front-office Excel Python workflows and how it interacts with the Alma C# Server, while expanding nUnit test coverage to self-document calculator configurations to guide desk developers. (C#, nUnit) [Jul 25]
- Implemented and delivered the SwapRateFromBondYieldAndSpread calculator to derive swap rates from government bond yields and spreads – while maintaining core calculators like BondPriceToYield and providing ongoing operational diagnostics for calculation graph execution support issues. (C#) [Aug 15, Aug 29]
- Supported trading desk developers in configuring USD curve setups and Excel integration debugging, successfully releasing Alma Marks USD to the US rates desk traders that enabled them to mark interest rate curves live. (Excel Py) [May 23, Jun 20, Sep 12]

---

### RFQ Pricing

[Delivery Summary:](#)
* **Problem & Context:** Following the release of indicative swaps on Broadway, the desk needed to scale eTrading to handle live client Requests for Quote (RFQs) – averaging ~50 trades per day across outrights, curves, butterflies and package swaps.
* **Architecture & Solution:** Extended AlmaPricer to support comprehensive swap variants (weekly/monthly tenors, IMM rolls, forward-starting, stub periods). Built a dedicated Quant GroupedSwapPriceTask package pricer with sequential and parallel execution flavors to handle packaged swaps. 
* **Pricing & Business Value:** Automated RFQs to drastically reduce manual trader quoting.
* **Key Techniques:** Object Graph with fixings, single swap & package swap calculations (PV/DV01), BenchmarkDotNet comparisons of sequential and parallel executions, and Python End-to-End External tests.

[Delivery Journal:](#)
- **Broadway Integration:** Integrated with the Broadway RFQ platform via joint testing sessions with the Broadway RFQ engineering team, validating Indicative Quote Adapters in SIT/UAT environments and triaging unsupported streaming request shapes. (C#, Broadway) [Jul 25 – Aug 15]
- Released production support for weekly/monthly tenors, IMM rolls, and stub periods; extended AlmaPricer to price swaps that have already started by injecting historical fixings into the Object Graph backed by diagnostic endpoints and nUnit service tests. [Sep 12, Sep 19, Oct 31]
- Developed Python end-to-end test suite invoking Alma C# debug REST APIs to validate swap request JSON pricing results; conducted live RFQ product testing by comparing AlmaPricer outputs directly against trader spreadsheets. (Python) [Sep 26]
- Implemented GroupedSwapPriceTask to handle package swaps (up to 50 swaps) for PV and DV01, developing both sequential and parallel execution variants; benchmarked performance using BenchmarkDotNet and selected the single-threaded sequential approach for optimal performance, retaining the parallel test variant to support future scalability. (C#, BenchmarkDotNet) [Oct 31, Nov 7, Nov 14]
- Implemented Object Graph cleanup routines and tied them to streaming start/stop lifecycles to prevent memory leaks; enhanced RFQ exception handling to publish human-readable messages back to Broadway and log errors to Elastic. [Aug 15, Oct 3, Oct 31]

---

### Curve Configuration

[Delivery Summary:](#)
* **Problem & Context:** Curve definitions were previously locked inside static files, meaning any tweak to curve instruments required full software deployments and release ceremonies.
* **Architecture & Solution:** Moved curve configurations out of static files and into the bank's MongoDB reference data store. Defined curve-config schemas and built C# readers in AlmaPricer to fetch live curve definitions dynamically from REST/Swagger endpoints, alongside runtime management tools for traders.
* **Pricing & Business Value:** Enabled non-disruptive, runtime curve template modifications (including USD multi-curve O/N curve, Fed Curve, and Basis Curve setups) without application downtime.
* **Key Techniques:** OData MongoDB API datastore, C# REST API schema design.

[Delivery Journal:](#)
- Participated in platform team’s OData MongoDB API store adoption as the firm’s strategic repo for yield curve definitions. [May 23]
- Authored the yield curve schema and entity specifications (curve-config) for storing curve templates, publishing the standardized JSON schemas across lower environments. (MongoDB, OData API) [Aug 1 – Dec 5]
- Developed C# curve configuration reader modules in AlmaPricer to fetch runtime curve definitions from REST endpoints and created Swagger management tools allowing authorized users to inspect active in-memory configurations and publish live CurveConfig updates. (C#) [Dec 5]
- Extended curve configuration readers to handle complex multi-curve structures, successfully parsing O/N curve, Fed Curve and Basis Curve setups for multi-curve builds (including instrument definitions like CASH, futures, and OIS Swaps controllable via the UI). [Mar 13]

---

### Bond Roll Epic

[Delivery Summary:]
* **Problem & Context:** Manual updates of benchmark government bonds and expiring bond futures introduced operational risk, calculation errors, and stale curve marks during contract rollover periods. Alma Marks yield curve configuration is configured by traders such that the long end of the curve is anchored by OTR benchmark government bonds.
* **Architecture & Solution:** Architected an automated instrument rolling engine in Alma Marks that detects benchmark bond contract rollover dates (from strategic SQL-based market data stores), updates near/far contracts within the Alma Pricing Engine, and invokes conversion-factor calculations from Quant Interop. On each update, the internal observable pricing graph updates with new bonds, the calculation graph retriggers, and Bloomberg market data is resubscribed, resulting in a seamless real-time pricing update.
* **Pricing & Business Value:** Automated the benchmark On-The-Run (OTR) Government of Canada (GoC) bonds and cheapest-to-deliver (CTD) roll for Canadian bond futures, eliminating manual operational risk and ensuring accurate pricing inputs.
* **Key Techniques:** C#, SQL database, Bloomberg B-PIPE re-subscription tracking, and dynamic curve config manipulation.

[Delivery Journal:](#)
- Produced the development roadmap for automatic instrument rolling, enabling dynamic curve configuration updates, and held initial collaboration chats with Platform developers about architectural reusage of the new BenchmarkBondRollService. [Dec 5]
- Resolved defects in US government bond roll logic, adding nUnit integration tests and source-tracking logging to identify which partition was updating the bond. (C#, nUnit) [Feb 27]
- Extended test coverage and verified the Government of Canada (GoC) OTR benchmark bond rolls in production environments. [Mar 6]
- Conducted technology evaluation for re-using the strategic scheduler API for scheduling bond rolls against time schedules rather than writing a greenfield scheduler. [Mar 13]
- Manually executed production interest rate future IMM contract rolls forward in the curve configuration ahead of contract expiry for the desk to maintain accurate pricing. [Mar 20]
- Added LastUpdatedReason metadata tags to Bloomberg B-PIPE subscription updates to monitor bond roll event triggers. (C#, B-PIPE) [Mar 20]
- Implemented MarketServices REST data API to source BenchmarkBonds within Alma, and established test data in marketdb for feature testing. (C#, SQL) [Mar 20, Mar 27]
- Delivered the automated cheapest-to-deliver (CTD) roll for bond futures: calculating conversion factors via quant analytics functions, sourcing CTD candidate bonds from SQL tables and dynamically rolling near/far contract definitions. (C#, Exotica, SQL) [Mar 27, Apr 3, Apr–May]

---

### Production Monitoring I & Debugging Pricing Graphs

[Delivery Summary:](#)
* **Problem & Context:** Running strategic and legacy pricers in parallel required real-time visibility across market data feeds, curve builds, and execution prices, while debugging pricing anomalies required delving into native Quant C++ analytics without causing pricing outages. 
* **Architecture & Solution:** Built AlmaMonitor (Javascript/HTML portal), configured VS mixed-mode managed/native debugging, and implemented ASP.NET Core Swagger endpoints that provide pricing replayability from a serialized ObjectGraph file. 
* **Pricing & Business Value:** Mitigated intraday trading outages efficiently. Provided traffic-light status indicators (microservices pipeline) and stale stream alerts for front-office support.  
* **Key Techniques:** Object Graph Serialization, OpenTelemetry / Elastic Integration, ASP.NET Core Swagger endpoints, C#/C++ mixed-mode debugging.

[Delivery Journal:](#)
- **Mixed-Mode Managed/Native Debugging & Local Replay:** Established local Alma C# server and Excel Python stack debugging environments validating end-to-end ticks via SolPy-Publish, configuring Visual Studio mixed-mode debugging to step seamlessly from C# code into native C++ analytics. (C#, F#, C++, CMake, MSBuild) [May 16 – May 23]
- **Object Graph Diagnostics & Swagger Replay Endpoints:** Developed Swagger API endpoints exposing internal Object Graph states, input quote sets, and calculated outputs; extended endpoints to return fully serialized Object Graph JSON payloads for offline pricing replayability. (ASP.NET Core, Swagger) [Aug 29–31]
- Built a curve-reset endpoint that reboots the internal ObjectGraph and streaming MKD resubscription used during intraday curve config changes and testing repeatable scenarios. (ASP.NET Core) [Jul 18]
- Instrumented Quant service interop calls with execution timers to log calculation latency for the elastic pricing latency dashboard. [Jul 25]
- **Elastic Telemetry Optimization & Outage Prevention:** Instrumented Quant service interop calls with execution timers, upgraded Metrics Exporters to the latest Platform OpenTelemetry standards, and developed Elastic Estate Dashboards to monitor and prevent Elastic server overloads during volatile trading windows. [Jul 25 – Oct 17]
- **MarketFlow Stream Health & Alerting Interception:** Implemented automated MarketFlow health tests and dashboard panels tracking bond feeds, meeting-date swaps, and request counts; intercepted production red-alerts for stale tickers before curve builds degraded. [Nov 28 – Mar 27]
- Developed AlmaMonitor (v1), a unified JavaScript/HTML dashboard with a Python application layer where we deployed smoke-testing scripts to monitor microservice pipeline health. (JavaScript, HTML, Python) [Sep 19 – Oct 31]
- Led the platform upgrade to .NET 9, resolved Platform startup failures, validated native Quant Analytics library upgrades, and executed weekend production releases using solace-utils. (.NET 9) [Jul 2025 – May 26]

---

### Production Monitoring II – KDB+/Grafana Dashboards

*KDB captures every market-data tick and every price Alma publishes. Building Grafana dashboards on it gave the desk and support a view of curve inputs, published prices, and RFQ flow across intraday and historical ranges. I learned KDB+/q from scratch for this story.*

[Delivery Summary:](#)
* **Problem & Context:** Front-office traders and support teams lacked real-time and historical visibility into quote tick rates, curve recalibration inputs, time of day changes, and cross-environment pricing discrepancies.
* **Architecture & Solution:** Self-taught KDB+/q to build a real-time and historical telemetry estate. Developed dynamic time bucket aggregation queries across RDB, IDB, and HDB databases, rendering interactive Grafana dashboards with traffic-light status indicators.
* **Pricing & Business Value:** Delivered instant front-office visibility into streaming curve health, caught stale market data feeds, and enabled automated PROD vs. UAT price regression analysis prior to production cutovers.
* **Key Techniques:** KDB+/q time-series queries (as-of joins, dynamic bucket aggregation), Grafana dashboard engineering, and automated RAG status alerts.

[Delivery Journal:](#)
- **Foundation and Initial Query Designs:** Participated in KDB primer sessions (anonymous functions, type casting, cross db table joins, and Grafana KDB plugin integration) using QStudio and IDE plugins; designed initial queries and Grafana charts tracking raw market quote updates that trigger yield curve builds, organizing 100+ queries into version-controlled folders (`uat_checks`, `price_regressions`, `curve_monitoring`). (KDB+/q, QStudio) [Aug 29, Sep 12, Feb 13, Feb 20, Nov 21, Nov 28]
- **High Performance Unions & Dynamic Time-Bucketing:** Developed big data union queries spanning Real-Time (RDB), Intraday (IDB), and Historical (HDB) KDB databases, converting Grafana’s Unix-timestamp into native q time types; extended market-data q functions with bucketed aggregation accepting Grafana intervals to automatically scale bucket widths over wide time ranges (enabling smooth 2-week tick database queries), backed by a latency test suite tuning production bucket thresholds and converting yield curve ingredient charts to use aggregated intraday history. (KDB+/q, Grafana) [Oct 31 – Feb 20]
- **RAG Overview Dashboard:** Implemented KDB RAG status checks and consolidated overview pages showing real-time traffic-light indicators for AlmaMarks, AlmaPricer, and MarketFlow 5-minute activity; built last-update marks panels shading streams red, amber, or green based on inactivity thresholds and smoke test panels flagging insufficient market data points or blank result sets. [Feb 20, Mar 6, Mar 13, Mar 20]
- **RFQ Analytics Dashboards:** Provided a visual view of client RFQ activity, designing comprehensive RFQ dashboards tracking volume by client, transaction type (single swap, curve, butterfly, and package), PV, DV01, and risks. [Mar 13, Mar 20]
- Built yield curve visual chart plotting real-time published swap rates with a T-1h overlay as requested by the trading desk. [Feb 20, Feb 27]
- **Designed Benchmark Price Comparison Dashboard:** Implemented KDB as-of joins matching Bloomberg generic (BGN) prices against Alma indicative rates across multi-day windows for key tickers. (KDB+/q) [Mar 27]
- Developed automated PROD vs. UAT price regression dashboards to intercept pre-cutover pricing deviations, refining dashboard price tables to flag `NULL` values arising from unparsable Solace messages in KDB feed handlers. [Mar 6 – Mar 20]
- Enhanced MarketFlow dashboard to surface commonly occurring SolCache connectivity errors and inactive streams directly, greatly reducing remediation effort. [Mar 20]
- Prototyped a forward switch swap chart for the desk in KDB leveraging Q by porting the clunkier Excel version and presented all dashboards to the team. [Feb 27]