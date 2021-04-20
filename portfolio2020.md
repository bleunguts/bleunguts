**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)**
# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2013 – 2020._

# (Credit Suisse) Giraffe Core

_ **Period** __:_ May &#39;17 – Apr &#39;20

_ **Length** __:_ ~3 years

_ **Team Members** _ **:** 8 developers, 16 Business Analysts / Project Managers

_ **Technologies** _ **:** Java 8, Kotlin 1.3, Kotlin Coroutines, Kotlin Flow, JMS Apache Artemis, Jetty, Multipart HTTP streaming , Java Service Wrappers, ArgoJSON, Netty TCP, Memcached, ElasticSearch, Javascript, Performance Metrics and Trade Execution flow capturing with Grafana /Influx/Splunk

_ **Environments** _ **:** Linux/Windows

_ **Methodology** _ **:** Agile, Micro Services, Scrum of Scrum, Pair Programming, Feature teams, TDD, BDD

_ **Consultancy Experience:** _ Software engineering, Analyst Developer, Complex Data Analysis &amp; Business Intelligence of valuations, Feature management Release Management

_ **Description** _ **:** Giraffe risk management system is the firm&#39;s strategic unification of trading and risk management. The Credit Suisse global franchise Global Markets, Equities, Fixed Income and Prime Brokerage runs off the Giraffe platform worldwide producing accurate data for trading and risk aggregation feeds servicing capital regulatory requirements and business requests from Trading

Awarded the &quot;Risk Management House of the Year 2015 Award&quot; largely contributed to extremely small and fast product test and automated release cycle, well-engineered agile design effort, achieving efficient business requirements response and the risk-related requirements of regulators.

Among the eco-system of the many micro-services (80+) which constituents the giraffe platform, GIRAFFE core is the orchestrating development team that is the first-line face to trading and regulator&#39;s requirements.

As a Giraffe Core developer the responsibilities included coordinating with BAs and Quant team in implementing valuation of PVs &amp; risk for portfolio management, building risk scenarios to meet risk-related regulatory &amp; trading analysis needs, P&amp;L attribution using both revaluation and RBPNL methodologies, asset pricing dependency trees and the associated market data sourcing, price testing against 3rd party benchmark prices to satisfy product control regulatory requirements, trader EOD signoff calculation and overnight batch risk feeding.

Conducted portfolio PnL pricing discrepancy investigations and the associated enhancements or fixes which obtaining deeper understanding on the price driver dependency tree model for ETFs, stocks, futures, baskets.

Compute capacity was the notoriously complex space which sprung from performance concerns from trading desks and satisfying the SLAs for the overnight delivery of risk. Conducted in-depth performance related compute capacity investigations for the system looking at the non-deterministic patterns which could originate from and not limited to increased trading volumes, capacity requirements from book migrations, newly introduced reports to name a few. The valuation flow was complex in nature as it spanned across multiple services (core, market source, data services, grid) but in addition the internal farming landscapes in Giraffe; the MQ farm, the compute grid quant farm and the monte-carlo farm (structured exotic calcs). In terms of delivery, post-investigation performance enhancement were discussed and items of work raised, and another significant piece of work was designed a suite of performance dashboards top-down to assist the isolation of performance-related problem areas.

_ **Projects** _ **:**

_Giraffe Core (Risk Development)_

- Implemented new risk types involving sourcing market data, funnelling the correct data on the quant dictionary, handling quant risk results, Risk UI change for trading to value against the new risk type, feeding the risk in the relevant overnight risk report
- Implemented additional risk reports included implementing new risk bump scenario, implement scheduling for the risk report and feeding to report results to the data services cluster
- Implemented book level Time Scenario bumping, this included sourcing market data for a specified date (e.g. T+1) and designing the intraday UI elements for display. Coordinated with BA team to decide regulatory reporting schedule and implemented the relevant batch triggers.

This gave trading the ability to run T+1 scenario before public holidays as the feature that was implemented now supplies regional calendars for the quant lib to take account during holidays which resulted in reduced pricing discrepancies.

- Implemented SA-CCR risk to capture the new standard for counterparty credit risk exposure, implemented the market data sourcing of supervisory delta and volatility for the quant lib calculation
- Implemented Last Fixings Price Driver calculation in giraffe by implementing fixing sourcing to the quant library and adding the business logic to the pricing dependency tree traversal algorithm.
- Coordinated with the quant team to migrate spot proxy pricing as part of the &#39;quant library migration programme&#39;, Spot Proxy uses another asset&#39;s spot price as the proxy for calculation which required market data sourcing. This migration exercise benefited the platform as now the calc capacity was effectively transferred from the &#39;finite&#39; and &#39;static&#39; giraffe MQ farm onto the &#39;elastic&#39; compute grid which performs quant calcs.
- Coordinated with the quant team by providing analysis of the ETF pricing algorithm in the code base for the &#39;quant library migration programme&#39;. Contributed to deeper understanding of the ETF pricing algorithm the internal dividend calculation for the index and tracking index and the sourcing of the supporting dividend tables and reference index market data.
- Resolved Delta pricing discrepancy issue for the PRIME brokerage business line that upon investigation was caused from assets which were indexes over indexes. Resolved by correcting the ensuring the underlying index was supplying dependent market data based on full risk decomposition as the fuller set of market data provided the Pnl Attribution quant operation the proper price. Acquired deeper understanding of decomposed vs non-decomposed risk pricing for indexes over indexes.
- Coordinated with the quant team to migrate the Pnl Attribution operation with particular challenges that attribution can work with decomposed (as opposed to the aggregate index price from non-decomposition) so that all the underlying price constitutions were taken in account when performing attribution.
- Implement live pricing permissions that allow certain traders that have permission to see live Reuters prices. Enhanced the asset pricing dependency tree algorithm that traverses the price dependency tree for all system price types&#39; spot, future, index prices, FX rates to support the permission code.
- Developed Risk Factors generation quant operation to support regulatory Risk Based PnL Reports as the interim input for T+1 risk. Paired with a colleague and devised a chunking strategy that partitions book of trades with the goal of efficient distributing of the operation against the MQ farm.
- Implemented logic for certain business lines (PRIME) where by missing prices default to zero (a very small number) with a fall-back to sourcing previous available price from the market data service to complete intraday calcs which were throwing errors due to zero prices.
- Implemented Start of Day Risk Factors feeding to CS firm-wide regulatory risk store. Implemented ThetaProjection to project T-1 risks to T SOD to address the SOD risk requirement from trading.
- Implemented support for Commodities Index and Spot Bumping for Full Revaluation (VaR) reports.
- Resolved long standing anomaly that originates from an issue with the Apache Artemis cluster whereby messages non-deterministically goes missing due to the self-restart of server crashes causing peculiar behaviour. It was complex to solve as the obvious options for MQ brokers to set up message redistribution have always been turned on.

_Giraffe Emu (Compute Grid Submitter)_

- Spearheaded the design of a Greenfield micro-service that receives quant valuation requests via MQ and processes it on the compute grid. This included elastic compute grid session management and processing the huge volumes of execution results received from the compute grid. (Kotlin 1.3, Kotlin CoRoutines, Kotlin Flows, Apache Artemis MQ, IBM Symphony 7)
- Implemented and delivered end-to-end working compute grid submitter in Kotlin from inception. Implemented clustered session closing feature which gave the ability for the platform to purge selected compute workloads.

# (Credit Suisse) Giraffe Yeti

_ **Period** __:_ Sep &#39;13 - May &#39;17

_ **Length** __:_ ~4 years

_ **Team Members** _ **:**

_ **Technologies** _ **:** C#, ASP.NET Web API 2, COM Interop with native/managed quant libs, Managed vs Unmanaged Memory analysis, Autofac DI, Quartz, KnockoutJS, SignalR, JQuery, Twitter Bootstrap, Typescript, WPF, NinJect, Owin, Nancy, Jquery, Knockout .JS, Telegraf/InfluxDB/Grafana Metrics, Oracle Coherence Cache,CacheCow.NET, ActiveMQ, IBM Symphony 5.0/7.0 Compute Grid, Splunk Enterprise Dashboard design, Splunk Enterprise Monitoring &amp; Alerts Design, Google Proto Buffers, WinDbg Crash Dump analysis, Redgate Memory/Peformance profiler, Nagios, SVN, Git, Teamcity, Octopus Deploy, MongoDB

_ **Environments** _ **:** Windows /Linux HA Proxy Load balancers

_ **Methodology** _ **:** Scrum/Agile, Pair Programming, Micro-services, TDD

_ **Consultancy Experience** _: Software engineering, Business Intelligence, Grid Computing Collaboration

_ **Description** _ **:** As the lead developer of EDIT Valuation services, I covered all aspects of the valuation service which included developing new risks for Giraffe RealTime (a separate Real-time risk team).

The implementation involved calling the quant core libraries and placing the execution on the compute grid via the Symphony API.

The Yeti service included packaging the quant lib execution on the CS compute grid using IBM Symphony 7.0 acquired expert knowledge of Grid Resource Allocation/Scheduling Optimization and compute unit maximisation analysis.

Yeti is the sole micro-service which interacts directly with the CS compute grid which manages 1,500 heavy duty servers, with 20,000 compute units of capacity in EMEA, US, APAC. It also manages the GPU NVIDIA computes and the bridge to elastic &#39;rented capacity&#39; of Azure.

_ **Projects** _ **:**

_GiraffeRT (Giraffe Real-Time Risk Development)_

- Implemented new risks and supporting various asset classes for the real-time business including support for Options, VIX, ETFs, Bonds, Exotics.
- Implemented attribution and scenario analysis to evaluate risk changes due to market movements
- Support Exotics risk valuations that run complex Monte Carlo simulations off the Compute Grid
- Designed a new trade discovery which iteratively performs trade discovery on the compute grid, building a dependency tree of trade related resources and leverages compute grid elasticity to maximise efficiency and adhere to ever-changing compute capacity requirements
- Implemented enhancements using Google Protobufs Serialization to process PV and risk results
- Implemented enterprise circuit breaker of MQ to resolve production issue that resulted in server crashing and consequent loss of risk results
- Assessing and implementing caching technologies to support high volumes of market data and trade position data sourcing using Oracle Coherence local/remote caching, HTTP caching (using CacheCow), Grid Computing Caching technologies.

_Yeti (Compute Grid Submitter)_

- Development of valuation system utilizing grid technologies and bank&#39;s analytics libraries serviced by exposed REST API (ASP.NET WebApi)
- Core programming of the IBM Symphony Grid API to launch worker calculations on the compute grid
- Implementing priority of workload whereby acquired deep knowledge of grid scheduling policies and the internal algorithm of pre-emption of tasks based on priority, selective reclaim of compute resources. This would be exposed via the API to end users so they can prioritize huge workloads to get an idea
- Designed dashboards to visualize the valuation compute on the grid such that the firm-wide 22,000 compute units can be visualized and monitored and reviewed for bottlenecks to maximise compute usage. Performance metrics were an integral part of periodic business capacity reporting as an attempt to manage the volatility of valuation volumes due to BAU or could be impact of certain design decisions. (Splunk Enterprise Dashboards and Alerts)
- Performance analysis on compute grid slot ratios, successfully delivered achieving 3 times compute capacity cutting TCO costs by 1/3
- Partook as an SME in Azure and GPU programme rollout

_Walrus (Desk Asset Configuration provider)_

- Involved in architectural design of a greenfield configuration system which houses desk pricing parameters, pricing model data, instrument configuration, model parameters using ASP.NET WebAPI, MongoDB
- Drove the implementation of the Data Access Layer using MongoDB, cross-regional replication design, schema definition to satisfy the HA and resilience non-functional requirements.
