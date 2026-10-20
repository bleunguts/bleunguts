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

Alma is CIBC’s strategic real-time interest rate swaps pricing platform for the electronic fixed income (e-FI) business. **AlmaMarks** consumes live market data from Bloomberg B-PIPE and trader quotes over Solace, and exposes API endpoints for traders to mark the instruments on the curve in Excel (Python Stack) that feeds the curve build. **AlmaPricer** builds the CAD O/N curve and a three-curve USD setup (O/N curve, Fed Curve and Basis Curve) with the bank’s C++ analytics library. It streams indicative swap rates across trader-configured sources for curve instruments 1D to 50Y and prices client RFQs, publishing PV, swap rates and first order risk to Bloomberg, and KDB.

Alma went live in late Q3 2025 and replaced the legacy pricer in phases, running in parallel until final cutover in mid-2026. Integrating Alma into the bank’s strategic .NET PLATFORM framework captured reusable components and enhanced battle-tested robustness as it built from the same bank’s strategic risk platform. Key engineering challenges included handling high frequency curve recalibration (input rates updating 10+ times per second against a Bloomberg theoretical cap of four updates per second) while Alma must reprice on every tick yet publish within external system limitations. Additionally running dual pricers in production required complete end-to-end visibility across market data feeds, curve builds, and publishing execution prices, driving the construction of a observability estate (Elastic dashboards, KDB dashboards and Grafana).

[Responsibilities:](#)
Responsibilities spanned technical and business analysis for yield curve building and swap pricing alongside the quant lead and trading desk, translating requirements into structured JIRA stories. Core engineering focused on C# pricing service development, interop integration with the native C++ quant layer, Swagger diagnostic endpoints, and building telemetry dashboards across OpenTelemetry, KDB, and Grafana. Managed promotion across DEV, SIT, UAT, and PROD environments, including weekend release validations and post-release support, driving complete end-to-end delivery of each assigned capability.

[Involvement:](#)
I joined alongside the outgoing quant developer and, after a short intensive handover (USD curve specification, CAD bond-to-yield calculations, FOMC meeting dates, monthly bond future rolls, configurable calculators on the calc graph), took over development of Alma. I worked on the curve build and object-graph lifecycle, the core CIBC platform migration, RFQ and portfolio pricing, building new calculators, and curve configuration in a data-event-subscribable MongoDB platform layer. Additionally, I delivered benchmark bond and cheapest-to-deliver rolling in AlmaMarks to safeguard pricing accuracy, while building the monitoring estate across KDB/Grafana and Elastic.

[Progression:](#)
* **Onboarding & Core Fixes (May–Jun '25):** Handled handover of CAD/USD curve specifications, resolved critical object-graph calculation bugs, and stabilized initial pricing routines.
* **Platform Architecture & Messaging (Jul–Sep '25):** Integrated Alma into the bank’s strategic PLATFORM framework, migrated the pricer to .NET 9, and enabled multi-VPN Solace streaming.
* **Multi-curve, RFQ Expansion & Bond Roll (Oct '25–Jan '26):** Implemented multi-curve setups, central bank meeting-date jumps, and portfolio PV/DV01 pricing. Took ownership of the automated Bond Roll epic: server-side C# keeping the long end of the curve accurate as government bond futures expire.
* **Estate-wide Monitoring & CTD Bond Roll (Feb–May '26):** Built tick-level KDB+/q and Grafana monitoring with traffic-light status across AlmaMarks, AlmaPricer and MarketDataAPI. It caught a bad production dependency the morning after a release. Delivered the CTD half of the Bond Roll epic: automated cheapest-to-deliver rolling of near and far bond futures, with conversion factors from the market database.

[Skills Required:](#)
* Quant: yield curve construction (OIS discounting, O/N curve, Fed Curve and Basis Curve multi-curve, central-bank meeting-date jumps, futures convexity adjustments, bond-yield-plus-spread marking for the CAD long end), swap conventions (IMM dates, stubs, day counts, fixings), bond futures and cheapest-to-deliver mechanics, RFQ workflows.
* Engineering: Strong C#/.NET with debugging down into native C++ analytics. Learned KDB+/q, Solace, Grafana on the job.
* Ownership: Handover was brief and nobody else on the team was familiar with the codebase, so I became sole engineering owner. As a contractor I worked it out from first principles: given a list of contacts, I built the system around them as sole engineering owner, from first analysis through to production support.
* Worked With: quant trader, desk developers, quant researchers, platform tech, market-data, kdb tick analytics team, production support

_ **Projects** __:_

### PLATFORM Integration

[Delivery Summary:](#)
* **Problem & Context:** Alma required migration onto PLATFORM —the bank’s high-throughput service framework that drives the battle-tested strategic risk system —to leverage standardized request routing and high-frequency Solace messaging.
* **Architecture & Solution:** Extracted core pricing domain logic into standalone assemblies, refactoring AlmaMarks and AlmaPricer to run independently outside PLATFORM during the transition. Configured TeamCity CI/CD pipelines and wired request interfaces to route snap and streaming swap queries across the PLATFORM -> Alma -> Quant Interop -> Solace stack.
* **Pricing & Business Value:** Delivered the first production release of real-time CAD OIS swap streaming (ON to 30Y) to downstream Fixed Income Trading systems that integrated with Bloomberg.
* **Key Techniques:** C#/.NET 9 microservice decoupling, Solace PubSub+ multi-VPN connection handling, ASP.NET Core diagnostic Swagger endpoints, and PLATFORM routing-rule optimization.

[Delivery Journal:](#)
- Refactored the swap pricing domain logic into a deployable assembly, enabling the pricer to be hosted inside the PLATFORM container. (C#, .NET)
- Refactored AlmaMarks and the AlmaPricer to run standalone outside PLATFORM, and performed curve build smoke-test via Excel UI and solace-utils before merging and promoting through environments, minimizing disruption to existing production and staging BAU activities. (C#, Excel UI, solace-utils)
- Created the PLATFORM AlmaPricer repository and TeamCity build, establishing end-to-end DevOps automation. (PLATFORM, TeamCity)
- Wired the request interfaces to PLATFORM and conducted local end-to-end snap swap testing, diagnosing and resolving integration issues across the PLATFORM → Alma → Quant→ Solace stack. (C#, PLATFORM, Solace)
- Promoted services to DEV and resolved infrastructure issues across request routing tables, Elastic logging configuration, web gateways and TeamCity build issues.
- Implemented Solace e-FICC VPN cutover alongside the MarketDataAPI team, troubleshooting connection recovery edge cases, producing a reproducible test case for reconnection issues, and coordinating the upgraded VPN/MarketDataAPI schema rollout across DEV, SIT, UAT, and PROD. (C#, Solace PubSub+)
- Integrated the AlmaPricer into PLATFORM alongside the platform team across DEV, SIT and UAT, conducting release testing for the initial July 2025 production go-live.
- Developed ASP.NET Core Swagger endpoints exposing active stream statuses and the latest swap pricing results for real-time stream inspection. (ASP.NET Core, Swagger)
- Configured PLATFORM Settings and Rules within to setup routing for CAD instances and USD multi instances (MongoDB, Nucleus)
- Contributed to architecture designs utilizing PLATFORMS routing-rules model to drive the CAD and USD partitions routing.

---

### Streaming Curve Build

[Delivery Summary:](#)
* **Problem & Context:** Yield curves recalibrate on every market rate tick (10+ updates/second), driving substantial intraday compute loads during volatility. Alma was required to maintain full pricing consistency across high-frequency updates while publishing within external system caps (Bloomberg theoretical cap of 4 updates/sec).
* **Architecture & Solution:** Wrapped the Quant Interop YieldCurve builds in C# to support the real-time intraday use case. Standardized full cold boostraps for morning start-ups and new instruments requiring a rebuild, paired with fast Object Graph updates for incremental single tick movements. Designed and stabilized the stateful T -> T+1 daily reboot lifeccle – resolving a critical bug where stale valuation dates persisted – to flush old states, purge expired object graphs and initialize fresh business-date curve builds.
* **Pricing & Business Value:** Real-time curve construction across CAD, USD, USD FED, USD Basis setups. Modelled explicit Central Bank meeting-date jumps ensuring accurate curve shape and jump sizes during monetary policy announcements events.
* **Key Techniques:** C# to native C++ Quant interop, Object Graph lifecycle caching, Visual Studio mixed-mode managed/native debugging, and nUnit state-reproduction tests.

[Delivery Journal:](#)
- Built a functional prototype of the USD curve specification during onboarding, triaging pricing discrepancies on early-maturity nodes with the trading desk. (C#, Excel Py)
- Identified and fixed a wrong Object Graph instantiation defect causing swap prices to resolve to zero. (C#, Quant Interop)
- Triaged and resolved a bug where AlmaPricer failed to 35Y/40Y long-end swap points due to unhandled null mid-price inputs within the pricing pipeline.
- Reinstated forward curve publishing mechanisms from the pricer to aid debugging and visual UI verification.
- Enhanced Quant call logging, fast-curve utilization tracking, and curve rebuild quote triggers metrics within the pricing engine and exposed to Elastic Dashboards
- Resolved an object graph state inconsistency issue occurring when alternating full curve rebuilds with fast OG updates, validating fixes via a C# nUnit reproducible tests. (C#, Quant Interop, nUnit)
- Improved Exotica service test coverage for expired futures during fast curve updates. (nUnit)
- Investigated and raised for design discussion a race condition between market-data subscription pumps and quote-processing message pump stabilizing subscription event updates.
- Triaged the automated T → T+1 nightly restart issue causing curves to build with stale T-1 prices. The restart purges the previous day’s Object Graph (OG), rebuilds fresh OG for the new business date, performs a FULL curve rebuilds, then switch to fast updates. Captured defect in a small C# reproduction test. (C#, Exotica)
- Extended yield curve building logic to incorporate the Quant CentralBankMeetingDates function, building the meeting-date jumps ObjectGraph table. (C#, Quant Interop)
- Re-enabled futures convexity adjustments that had been omitted from the yield curve build to fix the pricing regression test failure that I built.
- Resolved intermittent test failures by pinning the exact valuation timestamp for the Quant Interop test suite. (C#, Quant Interop, nUnit)
- Authored Quant Service validation tests verifying implied overnight rates across central bank meeting dates to validate jump magnitudes. (C#, Quant Interop, nUnit)
- Deployed configuration patches removing legacy MeetingDateInterpolation once explicit meeting-date jumps were active in production.
- Upgraded AlmaPricer to utilize Quant Interop Library’s new GetValuationResult return type to retrieve OG values.

---

### Market Data & Connectivity

[Delivery Summary:](#)
* **Problem & Context:** Official market quotes for long-end or illiquid swap tenors can become stale or sparse during the trading day, threatening PnL calculation and RFQ quoting accuracy.
* **Architecture & Solution:** Built a modular pipeline (PartitionRunner -> price stream -> calculation graph) that mirrors the desk's marking spreadsheets. Implemented new custom calculators, including SwapRateFromBondYieldAndSpread, allowing traders to derive swap rates dynamically from underlying bond yields and spreads.
* **Pricing & Business Value:** Enabled traders to manually mark curves intraday, maintaining continuous, reliable pricing across sparse tenors and safeguarding live RFQ spreads.
* **Key Techniques:** Event-driven calculator pipelines, automated calculation-graph integration testing, and nUnit pipeline verification.

[Delivery Journal:](#)
- Integrated the new Solace e-FICC VPN into Alma with the market-data team, triaging breaking platform issues lacking dual VPN support, while investigating Solace connection recovery edge cases with MarketDataAPI teams and successfully created a reproducible test for reconnection problem. (Solace PubSub+)
- Configured direct Bloomberg B-PIPE ticker subscriptions to debug live curve input behaviour with the desk, isolating B-PIPE/MarketData API session drops in lower environments. The BPIPE tools were used to coordinate production BBG subscription lists (MarketData API, Bloomberg)
- Diagnosed and fixed MarketData API price streams entering terminated states during SIT/UAT release testing, filtering invalid Bloomberg CBBT mid-values that caused output invalidations, and implementing SolCache service-restart self-healing recovery routines. (SolCache, MarketData API)

---

### AlmaMarks Calculators

[Delivery Summary:](#)
* **Problem & Context:** Traders required custom calculation routines to derive curve marks from disparate raw market inputs, particularly when official benchmark quotes were unavailable or sparse.
* **Architecture & Solution:** Built a modular, event-driven calculation engine (Runner -> price streams -> calculation graph) mirroring front-office marking sheets. Implemented specialized calculators like SwapRateFromBondYieldAndSpread and maintained commonly used BondPriceToYield calculator.
* **Pricing & Business Value:** Empowered traders to manually mark curves intraday with custom spread offsets, maintaining accurate PnL and continuous RFQ quoting across illiquid curve tenors.
* **Key Techniques:** Directed acyclic graph (DAG) calculation execution, custom C# calculator pipelines, and automated nUnit pipeline verification tests.

[Delivery Journal:](#)
- Developed unit and integration test suites covering the Runner → price stream → calculation graph pipeline, self-documenting how curve configurations drive regional partitions, calculation paths and published metrics. (C#, nUnit)
- Participated in CAD and USD marking spreadsheet design reviews with the head Quant Trader and desk developers to analyse front-end Excel Python workflows and how it interacts with the Alma C# Server, while expanding nUnit test coverage to self-document calculator configurations to guide desk developers on calculator configurations. (C#, nUnit)
- Implemented and delivered the SwapRateFromBondYieldAndSpread calculator to derive swap rates from government bond yields and spreads – while maintaining core calculators like BondPriceToYield and providing ongoing operational diagnostics for calculation graph execution support issues. (C#)
- Supported trading desk developers in configuring USD curve setups and Excel integration debugging, successfully releasing AlmaMarks USD to the US rates desk traders that enabled them to mark interest rate curve live. (Excel Py)

---

### RFQ Pricing

[Delivery Summary:](#)
* **Problem & Context:** Following the release of indicative swaps on Broadway, the desk needed to scale eTrading to handle live client Requests for Quote (RFQs) – averaging ~50 trades per day across outrights, curves, butterflies and package swaps.
* **Architecture & Solution:** Extended AlmaPricer to support comprehensive swap variants (weekly/monthly tenors, IMM rolls, forward-starting, stub periods. Built a dedicated Quant GroupedSwapPriceTask package pricer with sequential and parallel execution flavours to handle packaged swaps.
* **Pricing & Business Value:** Automated RFQs drastically reduces manual trader quoting.
* **Key Techniques:** Object Graph with fixings, single swap & package swap calculations (PV/DV01), BenchmarkDotNet comparisons sequential and parallel executions and Python End-to-End External tests

[Delivery Journal:](#)
- Broadway Integration, integrated with the Broadway RFQ platform via joint testing sessions with the Broadway RFQ engineering team, validating indicative Quote Adapters in SIT/UAT environments and triaging unsupported streaming request shapes. (C#, Broadway)
- Validated Indicative Quote Adapter integration in SIT and UAT environments, and triaged unsupported streaming swap request shapes.
- Released production support for weekly/monthly tenors, IMM rolls, and stub periods; extended AlmaPricer to price swaps that have already started by injecting historical fixings into the ObjectGraph backed by diagnostic endpoints and nUnit service tests.
- Developed Python end-to-end test suite invoking Alma C# debug REST APIs to validate swap request JSONs pricing results; conducted live RFQ product testing by comparing AlmaPricer outputs directly against trader spreadsheets. (Python)
- Implemented GroupedSwapPriceTask to handle package swaps (up to 50 swaps) for PV and DV01, developing both sequential and parallel execution variants; benchmarked performance using BenchmarkDotNet and selected single-threaded sequential approach for optiomal performance, retaining he parallel test variant to support future scalability. (C#, BenchmarkDotNet)
- Implemented Object Graph cleanup routines and tied to streaming start/stop lifecycles to prevent memory leaks; enhanced RFQ exception handling to publish human-readable messages back to Broadway and logging errors to Elastic.

---

### Curve Configuration

[Delivery Summary:](#)
* **Problem & Context:** Curve definitions were previously locked inside static files, meaning any tweak to curve instruments required full software deployments and release ceremonies.
* **Architecture & Solution:** Moved curve configurations out of static files and into the bank's MongoDB reference data store. Defined curve-config schemas and built C# readers in AlmaPricer to fetch live curve definitions dynamically from REST/Swagger endpoints, alongside runtime management tools for traders.
* **Pricing & Business Value:** Enabled non-disruptive, runtime curve template modifications (including USD multi-curve O/N curve, Fed Curve Basis Curve setups) without application downtime.
* **Key Techniques:** OData MongoDB API datastore, C# REST API schema design

[Delivery Journal:](#)
- Participated in platform team’s OData MongoDB API store adoption as the firm’s strategic repo for yield curve definitions.
- Authored the yield curve schema and entity specifications (curve-config) for storing curve templates, publishing the standardized JSON schemas across lower environments. (MongoDB, OData API)
- Developed C# curve configuration reader modules in AlmaPricer to fetch runtime curve definition from REST endpoints and created Swagger management tools allowing authorized users to inspect active in-memory configurations and publish live CurveConfig updates (C#)
- Extended curve configuration readers to handle complex multi-curve structures, successfully parsing O/N curve, Fed Curve and Basis Curve setups for multi curve builds (including instrument definitions like CASH, futures, OIS Swaps controllable via the UI.

---

### Bond Roll Epic

[Delivery Summary:](#)
AlmaMarks yield curve configuration is configured by traders such that the long end of the curve is anchored by OTR benchmark government bonds. As benchmarks are replaced and futures contracts approach expiry, the instrument set has to roll with them. Done by hand, that is operational risk and a source of stale marks. This epic automated the rolls in AlmaMarks and the main focus of the pricing accuracy and the final months of the engagement.
* **Problem & Context:** Manual updates of benchmark government bonds and expiring bond futures introduced operational risk, calculation errors, and stale curve marks during contract rollover periods.
* **Architecture & Solution:** Architected an automated instrument rolling engine in AlmaMarks that detects benchmark bond contract rollover dates (from the strategic SQL-based market data stores) and updates near/far contract within Alma Pricing Engine, and invokes conversion-factor calculations from Quant Interop. On each update the Alma Pricing Engine’s internal observable pricing graph updates with the new bonds, retriggers calculation graph, and BBG market data is resubscribed resulting in a seamless real-time pricing update
* **Pricing & Business Value:** Automated the benchmark On-The-Run (OTR) Government of Canada (GoC) bonds and cheapest-to-deliver (CTD) roll for Canadian bond futures, eliminating manual operational risk and ensuring accurate pricing inputs.
* **Key Techniques:** C#, SQL database, Bloomberg B-PIPE re-subscription tracking, and dynamic curve config manipulation.

[Delivery Journal:](#)
- Produced the development roadmap for automatic instrument rolling, enabling dynamic curve configuration updates, and held initial collaboration chats with PLATFORM developers about architectural reusage of the new BenchmarkBondRollService.
- Resolved defects in US government bond roll logic, adding nUnit integration tests and source-tracking logging to identify which partition was updating the bond. (C#, nUnit)
- Extended test coverage and verified the Government of Canada (GoC) OTR benchmark bond rolls in production environments.
- Conducted technology evaluation for re-using the strategic scheduler API for scheduling bond roll against time schedule rather than writing a greenfield scheduler.
- Manually executed production interest rate future IMM contract rolls forward in the curve configuration ahead of contract expiry for the desk to maintain accurate pricing.
- Added LastUpdatedReason metadata tags to Bloomberg B-PIPE subscription updates to monitor bond roll event triggers. (C#, B-PIPE)
- Implemented MarketServices REST data API to source BenchmarkBonds within Alma, and established test data in marketdb for feature testing. (C#, SQL)
- Delivered the automated cheapest-to-deliver (CTD) roll for bond futures: calculating conversion factors via quant analytics functions, sourcing CTD candidate bonds from SQL tables and dynamically rolling near / far contract definitions. (C#, Exotica, SQL)

---

### Production Monitoring I & Debugging Pricing Graphs

[Delivery Summary:](#)
* **Problem & Context:** Running strategic and legacy pricers in parallel required real-time visibility across market data feeds, curve builds, and execution prices, while debugging pricing anomalies required delving into native Quant C++ analytics without causing pricing outages.
* **Architecture & Solution:** Built AlmaMonitor (Javascript/HTML portal), configured VS mixed-mode managed/native debugging and implemented ASP.NET Core Swagger endpoints that provides pricing replayability from a serialized ObjectGraph file.
* **Pricing & Business Value:** Mitigated intraday trading outages efficiently. Provided traffic-light status indicators (microservices pipeline) and stale streams alerts for front-office support.
* **Key Techniques:** Object Graph Serialization, OpenTelemetry / Elastic Integration, ASP.NET Core Swagger endpoints, C#/C++ mixed-mode debugging

[Delivery Journal:](#)
- *Mixed-Mode Managed/Native Debugging & Local Replay*, established local Alma C# server and Excel Python stack debugging environments validating end-to-end ticks via SolPy-Publish, configuring Visual Studio mixed-mode debugging to step seamlessly from C# code into native C++ analytics. (C#, F#, C++, CMake, MSBuild)
- *Object Graph Diagnostics & Swagger Replay Endpoints*, developed Swagger API endpoints exposing internal Object Graph states, input quote sets, and calculated outputs; extended endpoints to return fully serialized Object Graph JSON payloads for offline pricing replayability. (ASP.NET Core Swagger )
- Built a curve-reset endpoint that reboots the internal ObjectGraph and streaming MKD resubscription used during intraday curve config changes and testing repeatable scenarios. (ASP.NET Core)
- Instrument Quant service interop calls with execution timers to log calculation latency for the elastic pricing latency dashboard.
- *Elastic Telemetry Optimization & Outage Prevention*, Instrument Quant service interop calls with execution timers and upgraded Metrics Exporters to latest PLATFORM OpenTelemetry standards, and developed Elastic Estate Dashboards to monitor and prevent Elastic server overloads during volatile trading windows.
- *MarketDataAPI Stream Health & Alerting Interception*, implemented automated MarketDataAPI health tests and dashboard panels tracking bond feeds, meeting-date swaps, and request counts; intercepted production red-alerts for stale tickers before curve builds degraded.
- *Developed AlmaMonitor (v1)*, a unified JavaScript/HTML dashboard with a Python application layer where we deployed smoke-testing scripts to monitor microservice pipeline health. (JavaScript, HTML, Python)
- Led the platform upgrade to .NET 9 resolved PLATFORM startup failures, validated native Quant Analytics library upgrades, and executed weekend production releases using solace-utils. (.NET 9)

---

### Production Monitoring II – KDB+/Grafana Dashboards

KDB captures every market-data tick and every price Alma publishes. Building Grafana dashboards on it gave the desk and support a view of curve inputs, published prices and RFQ flow across intraday and historical ranges. I learnt KDB+/q from scratch for this story.

[Delivery Summary:](#)
* **Problem & Context:** Front-office traders and support teams lacked real-time and historical visibility into quote tick rates, curve recalibration inputs, time of day changes, and cross environments pricing discrepancies.
* **Architecture & Solution:** Self-taught KDB+/q to build a real-time and historical telemetry estate. Developed dynamic time bucket aggregation queries across RDB, IDB, and HDB databases, rendering interactive Grafana dashboards with traffic-light status indicators.
* **Pricing & Business Value:** Delivered instant front-office visibility into streaming curve health, caught stale market data feeds and enabled automated PROD vs. UAT price regression analysis prior to production cutovers.
* **Key Techniques:** KDB+/q time-series queries (as-of joins, dynamic bucket aggregation), Grafana dashboard engineering, and automated RAG status alerts.

[Delivery Journal:](#)
- *Foundation and initial query designs*, participated in KDB primer sessions (anonymous functions, type casting, cross db table joins and Grafana KDB plugin integration) using QStudio, IDE plugins; designed initial queries and Grafana charts tracking raw market quote updates that trigger yield curve builds, and organized hundred+ queries into version-controlled folders (uat_checks, price_regressions, curve_monitoring). (KDB+/q, QStudio)
- *High Performance unions & Dynamic Time-Bucketing*, developed big data union queries spanning Real-Time (RDB), Intraday (IDB), and Historical (HDB) KDB databases, converting Grafana’s Unix-timestamp into native q time types; extended market-data q functions with bucketed aggregation accepting Grafana interval to automatically scale bucket widths over wide time ranges (enabling smooth 2-week tick database queries), backed by a latency test suite tuning production bucket thresholds and converting yield curve ingredient charts to use aggregated intraday history. (KDB+/q, Grafana)
- *RAG Overview Dashboard*, implemented KDB RAG status checks and consolidated overview pages showing real-time traffic-light indicators for AlmaMarks, AlmaPricer and MarketDataAPI five minutes activity; built last-updates marks panels shading streams red, amber, or green based on inactivity thresholds and smoke test panel that flags insufficient market data points or blank result sets.
- *RFQ Analytics Dashboards gave us a visual view of client RFQ activity*, designed comprehensive RFQ dashboards tracking volume by client, transaction type (single swap, curve, butterfly and package), PV, DV01 and risks.
- Built yield curve visual chart that plots real-time published swap rates with a T-1h overlay as requested by the trading desk.
- Designed Benchmark Price Comparison Dashboard by implementing KDB as-of join matching Bloomberg generic (BGN) prices against Alma indicative rates across multi-day window for key tickers. (KDB+/q)
- Developed automated PROD vs UAT price regression dashboard to intercept pre-cutover pricing deviations, with special visual indicator to flag unparsable Solace messages that KDB feed handlers failed to parse e.g. NULL values.
- Enhanced MarketDataAPI dashboard to surface commonly occurring SolCache connectivity errors and inactive streams directly greatly reducing remediation effort.
- Prototyped a forward switch swap chart for the desk in KDB leveraging Q by porting the clunkier excel version and presented all the dashboards to the team.
