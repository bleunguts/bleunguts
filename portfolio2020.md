**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2023-2021](https://bleunguts.github.io/bleunguts/portfolio2023)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)** 
# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2013 – 2020._

# (Credit Suisse) Giraffe Core

_ **Period** __:_ May '17 – Apr '20

_ **Length** __:_ ~3 years

_ **Team Members** _ **:** 8 developers, 16 Business Analysts / Project Managers

_ **Technologies** _ **:** Java 8, Kotlin 1.3, Kotlin Coroutines, Kotlin Flow, JMS Apache Artemis, Jetty, Multipart HTTP streaming , Java Service Wrappers, ArgoJSON, Netty TCP, Memcached, ElasticSearch, Javascript, Performance Metrics and Trade Execution flow capturing with Grafana /Influx/Splunk

_ **Environments** _ **:** Linux/Windows

_ **Methodology** _ **:** Agile, Micro Services, Scrum of Scrum, Pair Programming, Feature teams, TDD, BDD

_ **Consultancy Experience:** _ Software engineering, Analyst Developer, Complex Data Analysis & Business Intelligence of valuations, Feature management Release Management

_ **Description** _ **:** Giraffe is Credit Suisse's risk management system, unifying trading and risk management across Global Markets, Equities, Fixed Income, and Prime Brokerage. It ensures accurate data for trading and risk aggregation, meeting regulatory requirements and business demands. The system was instrumental in Credit Suisse winning the "Risk Management House of the Year 2015 Award," largely due to its agile design, efficient response to business needs, and fast product testing and automated release cycle.

[https://www.risk.net/awards/2435442/risk-management-house-year-credit-suisse](https://www.risk.net/awards/2435442/risk-management-house-year-credit-suisse)

Among the eco-system of the many micro-services (60+) which constituents the giraffe platform, GIRAFFE core is the orchestrating development team that is the first-line face to trading and regulator's requirements.

As a Giraffe Core developer, I coordinated with BAs and the Quant team to implement valuation of PVs & risk for portfolio management, building risk scenarios to meet risk-related regulatory & trading analysis needs, P&L attribution using both revaluation and RBPNL methodologies, asset pricing dependency trees and the associated market data sourcing, price testing against third party benchmark prices to satisfy product control regulatory requirements, trader EOD signoff calculation and overnight batch risk feeding.

I was regularly involved in resolving portfolio PnL pricing discrepancies, starting initial investigation with trading, proposing solutions, discussing with the wider team and implementing enhancements and fixes. This process deepened my understanding of the price driver dependency tree model for assets like ETFs, stocks, futures, baskets.

Compute capacity was a notoriously complex area due to performance concerns from trading desks and the need to meet SLAs for the overnight risk delivery. I conducted in-depth compute capacity investigations, examining non-deterministic patterns caused by factors such as increased trading volumes, capacity requirements from book migrations and newly introduced reports. The valuation flow, spanning multiple service-oriented clusters (core, market source, data services, grid) and internal calculation farming landscapes (MQ farm, compute grid quant farm, and Monte Carlo farm for structured exotic calculations), added to the complexity. 

Post-investigation, I discussed performance enhancements and raised work items. Another significant task was designing a suite of performance dashboards from top-down to help isolate performance-related issues.

_ **Projects** _ **:**

_Giraffe Core (Risk Development)_

- Implemented new risk types by sourcing market data, funnelling the correct data shape into the quant dictionary and handling quant risk results. Enhanced the Risk UI for trading to value against the new risk types and fed the risks to the relevant overnight risk reports.
- Implemented additional risk reports including new risk bump scenario and the scheduling code that ensure risk reports results were fed to the data services cluster within scheduling requirements.
- Implemented book level Time Scenario bumping, sourcing market data for a specified date (e.g. T+1) and designing UI elements for the intraday GUI. Coordinated with BAs to set regulatory reporting schedules and implemented batch triggers. This allowed trading to run T+1 scenario before public holidays by supplying regional calendars to the quant routines resulting in more accurate pricing.
- Implemented SA-CCR risk to capture the new standard for counterparty credit risk exposure, sourcing supervisory delta and volatility data from market data service to be supplied to the quant library calculation.
- Implemented Last Fixings Price Driver calculation in giraffe by implementing fixing sourcing to the quant library and adding the business logic to the pricing dependency tree traversal algorithm.
- Coordinated with the quant team to migrate spot proxy pricing as part of the 'quant library migration programme', Spot Proxy uses another asset's spot price as the proxy for calculation which required market data sourcing. This migration slashed the platform's capacity utilization by moving the calculation logic from the 'finite' and 'static' giraffe MQ farm (inline) onto the 'elastic' compute grid (grid quant execution).
- Coordinated with the quant team by providing analysis of the ETF pricing algorithm for the 'quant library migration programme'. Led to a deeper understanding of theinternal dividend calculation for the index and tracking index and the sourcing of the supporting dividend tables and reference index market data in ETF pricing.
- Successfully conducted RCA for the PRIME brokerage business whom had issue of Delta pricing discrepancy for EquityIndexes over Indexes. Resolved by correcting the issue whereby the underlying index was supplying dependent market data based on full risk decomposition, as the fuller set of market data provided the Pnl Attribution quant operation the proper price.  Gained deep understanding of decomposed vs non-decomposed risk pricing for indexes over indexes.
- Coordinated with the quant team to migrate the Pnl Attribution operation faced particular challenges that attribution can work with decomposed (as opposed to the aggregate index price from non-decomposition) so that all the underlying price constitutions were taken in account when performing attribution.
- Implement live pricing permissions for selected traders that are permissioned to see live Reuters prices. Enhanced the asset pricing dependency tree algorithm that traverses the price dependency tree for all system price types' spot, future, index prices, FX rates to support the permission code.
- Developed Risk Factors generation quant operation to support regulatory Risk Based PnL Reports as the interim input for T+1 risk. Paired with a colleague and devised a chunking strategy that partitions book of trades with the goal of efficient distributing of the operation against the MQ farm.
- Implemented logic for certain business lines (PRIME) where by missing prices default to zero (a very small number) with a fall-back to sourcing previous available price from the market data service to complete intraday calcs which were throwing errors due to zero prices.
- Implemented Start of Day Risk Factors feeding to firm-wide regulatory risk store. 
 Implemented ThetaProjection to project T-1 risks to T SOD to address the SOD risk requirement from trading.
- Implemented support for Commodities Index and Spot Bumping for Full Revaluation (VaR) reports.
- Resolved a long standing anomaly with the Apache Artemis cluster that caused  non-deterministic message loss.  This edge case happened during automatic self-restart after server crashes. It was complex to solve as the obvious options for MQ brokers to set up message redistribution have always been turned on.  Led the investigation with chief SMEs and brought the issue to a resolution reducing the out-of-support calls for server crashes significantly.

_Giraffe Emu (Compute Grid Submitter)_

- Spearheaded the design of a Greenfield micro-service that receives quant valuation requests via MQ and processes it on the compute grid. This included elastic compute grid session management and processing the huge volumes of execution results received from the compute grid. (Kotlin 1.3, Kotlin CoRoutines, Kotlin Flows, Apache Artemis MQ, IBM Symphony 7)
- Implemented and delivered end-to-end compute grid submitter from inception, including a clustered session closing feature to purge selected compute workloads.

# (Credit Suisse) Giraffe Yeti

_ **Period** __:_ Sep '13 - May '17

_ **Length** __:_ ~4 years

_ **Team Members** _ **:**

_ **Technologies** _ **:** C#, ASP.NET Web API 2, COM Interop with native/managed quant libs, Managed vs Unmanaged Memory analysis, Autofac DI, Quartz, KnockoutJS, SignalR, JQuery, Twitter Bootstrap, Typescript, WPF, NinJect, Owin, Nancy, Jquery, Knockout .JS, Telegraf/InfluxDB/Grafana Metrics, Oracle Coherence Cache,CacheCow.NET, ActiveMQ, IBM Spectrum Symphony 5/7 Grid, Splunk Enterprise Dashboard design, Splunk Enterprise Monitoring & Alerts Design, Google Proto Buffers, WinDbg Crash Dump analysis, Redgate Memory/Peformance profiler, Nagios, SVN, Git, Teamcity, Octopus Deploy, MongoDB

_ **Environments** _ **:** Windows /Linux HA Proxy Load balancers

_ **Methodology** _ **:** Scrum/Agile, Pair Programming, Micro-services, TDD

_ **Consultancy Experience** _: Software engineering, Business Intelligence, Grid Computing Collaboration

_ **Description** _ **:** As the lead developer of EDIT Valuation services, I covered all aspects of the valuation service development which included developing new risks for Giraffe RealTime (a separate Real-time risk team).

The Yeti service packages the quant core libraries and invoking the execution on the compute grid via the Symphony 7.0 API.

The Yeti service orchestrated the CS compute grid, managing 1,500 servers and 20,000 compute units across EMEA, US, and APAC, as well as the GPU NVIDIA compute farms and Azure's elastic 'rented capacity'.

Gained SME status for Cloud computing in Credit Suisse in areas such as Compute Grid Resource Allocation/Scheduling Optimization and compute unit maximisation analysis within the Investment Bank franchise and participated as SME in Azure and GPU program rollouts.

Throughout my tenure, I demonstrated expertise in grid computing, performance optimization, and effective collaboration with cross-functional teams, significantly enhancing the capabilities and efficiency of Credit Suisse's valuation services.

_ **Projects** _ **:**

###### GiraffeRT (Giraffe Real-Time Risk Development)

- Implemented new risks and supporting various asset classes for the real-time business including Options, VIX, ETFs, Bonds, Exotics.
- Implemented attribution and scenario analysis to evaluate risk changes due to market movements
- Support Exotics risk valuations running complex Monte Carlo simulations on the Compute Grid
- Drove the implementation of a new trade discovery that iteratively performs trade discovery on the compute grid to build a dependency tree of trade related resources. It leverages compute grid elasticity to maximise efficiency and adhere to the ever-changing compute capacity requirements
- Enhaced Google Protobufs Serialization to process PV and risk results
- Implemented enterprise circuit breaker of MQ to resolve production issue that caysed server crashes and loss of risk results
- Assessing and implementing caching technologies to support high volumes of market data and trade position data sourcing. (Oracle Coherence local/remote caching, HTTP caching using CacheCow, Grid Computing Caching technologies)


###### Yeti (Compute Grid Submitter)

- Development of valuation system using grid technologies and bank's analytics libraries serviced by a REST API (ASP.NET WebApi, IBM Spectrum Symphony 7)
- Core programming of the IBM Symphony Grid API to launch worker calculations on the compute grid
- Implementing workload priority, gaining deep knowledge of grid scheduling policies, task pre-emption algorithms based on priority and selective reclaim of compute resources. This would be exposed via the API to end users so they can prioritize huge workloads to get an idea
- Designed dashboards to visualize the valuation compute on the grid such that the firm-wide 22,000 compute units can be visualized and monitored and reviewed for bottlenecks to maximise compute usage. Performance metrics were an integral part of periodic business capacity reporting as an attempt to manage the volatility of valuation volumes due to BAU or could be impact of certain design decisions. (Splunk Enterprise Dashboards and Alerts)
- Performance analysis on compute grid slot ratios, successfully delivered achieving 3 times compute capacity cutting TCO costs by 1/3
- Participated as an SME in the Azure and GPU program rollout.

###### Walrus (Desk Asset Configuration provider)

- Contributed to the architectural design of a greenfield configuration system for desk pricing parameters, pricing model data, and instrument configuration using ASP.NET WebAPI and MongoDB.
- Led the implementation of the Data Access Layer with MongoDB, including cross-regional replication design and schema definition to meet HA and resilience requirements.
