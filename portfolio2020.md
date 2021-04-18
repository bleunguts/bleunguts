**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)**
# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2013 – 2020._

# (Credit Suisse) Giraffe Core

_ **Period** __:_ May &#39;17 – Apr &#39;20

_ **Length** __:_ ~3 years

_ **Team Members** _ **:** 8 developers, 16 Business Analysts / Project Managers

_ **Technologies** _ **:** Java 8, Kotlin 1.3, Kotlin Coroutines, Kotlin Flow, JMS Apache Artemis, Javascript, Jetty, ArgoJSON, Multipart HTTP streaming, Java Service Wrappers, Netty TCP, Memcached, ElasticSearch, Grafana, Influx, Splunk

_ **Environments** _ **:** Linux/Windows

_ **Methodology** _ **:** Micro services, Scrum, Pair Programming, Feature teams, TDD, BDD

_ **Consultancy Experience:** _ Software engineering, Data Analysis &amp; Business Intelligence, Release Management, Feature management

_ **Description** _ **:**

Working with the Giraffe Core team, Giraffe risk management system is the firm&#39;s strategic unification of trading and risk management. The Credit Suisse global franchise Global Markets, Equities, Fixed Income and Prime Brokerage runs off the Giraffe platform worldwide producing accurate data for trading and risk aggregation feeds for capital regulatory requirements

Awarded the &quot;Risk Management House of the Year 2015 Award&quot; largely contributed to extremely small and fast product test and automated release cycle, well-engineered agile design effort, achieving efficient business requirements response and the risk-related requirements of regulators.

Among the eco-system of micro-services (80+) which constituents the giraffe platform, GIRAFFE core is the orchestrating development team that is the face to trading and regulator&#39;s feature requirements.

As a Giraffe Core developer the responsibilities included coordinating with BAs and Quant team in implementing valuation of PVs &amp; risk for portfolio management, building risk scenarios to meet risk-related regulatory &amp; trading analysis needs, P&amp;L attribution using both revaluation and RBPNL methodologies, asset pricing dependency trees and associated market data sourcing frequently coordinating with market data micro-service teams, price testing against 3rd party benchmark prices for regulators, trader EOD signoff calculation and overnight batch triggering for various CS business lines for risk feeds.

Performed portfolio PnL pricing discrepancy investigation often led to development work contributing to deeper understanding with the price driver dependency tree model for ETFs, stocks, futures, baskets.

Evaluated complex performance and capacity investigations arising from the calculation capacity required for the system to maintain scalable from increased trading volumes, book migrations off other risk systems, new reports requiring capacity. There were several farms the giraffe core MQ farm, the compute grid quant farm and the monte-carlo farm for more complex exotic calcs.

_ **Projects** _ **:**

_Giraffe Core (Risk Development)_

- Delivered new risk types feature requests involving sourcing market data, constructing quant dictionary, risk UI change to support the new risk type, feeding to overnight risk report
- Delivered additional risk reports included implementing new risk bump scenario, implement scheduling for the risk report and feeding to reporting micro-service cluster
- Implemented per book level Time Scenario bumping, this included sourcing market data for a specified date (e.g. T+1) and designing the intraday UI elements for display. Coordinated with BA team to decide regulatory reporting schedule subsequently implementing the relevant batch triggers. The challenge was that Traders had issues with running T+1 scenarios before public holidays which was overcome by implementing for regional calendars for quant calculations to take account thereby mitigating pricing discrepancy during holidays.
- Implemented SA-CCR risk to capture the new standard for counterparty credit risk exposure, market data sourcing of supervisory delta and volatility for the quant lib calculation
- Implemented Last Fixings Price Driver calculation in giraffe by supplying fixing resource data to the quant library which required development of sourcing fixings and modifications to the pricing dependency tree traversal to support this.
- Coordinated with the quant team to migrate spot proxy pricing for quant library migration programme, Spot Proxy uses another asset&#39;s spot price as the proxy for calculation which required market data sourcing. The system benefited as the capacity was migrated off the finite giraffe MQ farm onto the elastic compute grid (quant calcs).
- Coordinated with the quant team by providing analysis of the ETF pricing algorithm in the code base for the quant library migration programme. Contributed to deeper understanding of the ETF pricing algorithm the internal dividend calculation for the index and tracking index.
- Resolved Delta pricing discrepancy issue for PRIME brokerage which upon my investigation was caused by pricing Indexes over indexes. Resolved by ensuring the index of index was supplying decomposed risk bringing in the fuller set of resources required for the Pnl Attribution quant routine to price properly. Acquired deeper understanding of decomposed vs non-decomposed pricing for indexes over indexes.
- Coordinated with the quant team to migrate the Pnl Attribution with particular challenges that attribution can work with non-decomposed vs decomposed prices (e.g. decomposed risks on index with a basket of underlyings will contain price constituents as opposed to the former an aggregate index price)
- Implement live pricing permissions that allow certain traders to see live reuters prices. Made enhancement within the asset pricing dependency tree algorithm that traverses the price dependency tree for all system price types spot, future, index prices, FX rates.
- Developed Risk Factors generation quant operation to support regulatory Risk Based PnL Reports as it is required for the interim input to the routine (i.e. T+1 risks). Developed chunking strategy that partitions book of trades so that it can efficiently distribute over the MQ farm.
- Implemented logic for certain business lines (PRIME) where by missing prices default to zero (a very small number) with a fall-back to sourcing prices for previous version via the market data service for calculations to complete for intraday calcs.
- Implemented Start of Day Risk Factors feeding to CS firm-wide regulatory risk store. Implemented ThetaProjection to project T-1 risks to T SOD to address the SOD risk requirement.
- Implemented support for Commodities Index and Spot Bumping for Full Revaluation (VaR) reports
- Resolved long standing anomaly that originates from an issue with the Apache Artemis cluster management whereby messages non-deterministically drops due to server crashes albeit having brokers set up with message redistribution activated

_Giraffe Emu (Compute Grid Submitter)_

- Spearheaded the design of a greenfield microservice that receives quant valuation requests via MQ and processes it on the compute grid. This included session management of an elastic grid and processing the huge volumes of execution results from the grid. (Kotlin 1.3, Kotlin CoRoutines, Kotlin Flows, Apache Artemis MQ
- Implemented and delivered end-to-end working compute grid submitter in Kotlin from inception. The business value add was the feature to select and purge particular workloads by implementing a clustered session management model in Emu that purges Grid sessions

# (Credit Suisse) Giraffe Yeti

_ **Period** __:_ Sep &#39;13 - May &#39;17

_ **Length** __:_ ~4 years

_ **Team Members** _ **:**

_ **Technologies** _ **:** C#, ASP.NET Web API 2, COM Interop with native, Managed vs Unmanaged Memory analysis, Autofac DI, Quartz, KnockoutJS, SignalR, JQuery, Twitter Bootstrap, Typescript, WPF, NinJect, Owin, Nancy, Jquery, Knockout .JS, Telegraf/InfluxDB/Grafana Metrics, Oracle Coherence Cache, ActiveMQ, IBM Symphony 5.0/7.0 Compute Grid, Splunk Enterprise Dashboard design, Splunk Enterprise Monitoring &amp; Alerts Design, Google Proto Buffers, WinDbg Crash Dump analysis, Redgate Memory/Peformance profiler, Nagios, SVN, Git, Teamcity, Octopus Deploy, MongoDB

_ **Environments** _ **:** Windows /Linux HA Proxy Load balancers

_ **Methodology** _ **:** Scrum/Agile, Pair Programming, Micro-services, TDD, Compute Grid collaboration

_ **Consultancy Experience** _: Software engineering, Business Intelligence, Grid Computing Collaboration

_ **Description** _ **:**

As the lead developer of EDIT Valuation services, I covered all aspects of the valuation service which included developing new risks by calling quant core libraries on the compute grid from business analysis with end users to end-delivery to production. The Yeti service included packaging the quant lib execution on the CS compute grid using IBM Symphony 7.0 acquired expert knowledge of Grid Resource Allocation/Scheduling Optimization and compute unit maximisation analysis.

Yeti is the sole micro-service which interacts directly with the CS compute grid which manages 1,500 heavy duty servers, with 20,000 compute units of capacity in EMEA, US, APAC. It also manages the GPU NVIDIA computes and the bridge to elastic &#39;rented capacity&#39; of Azure.

_ **Projects** _ **:**

_GiraffeRT (Giraffe Real-Time Risk Development)_

- Implemented new risks and supporting various asset classes for the real-time business including support for Options, VIX, ETFs, Bonds, Exotics.
- Implemented attribution and scenario analysis to evaluate risk changes due to market movements
- Support Exotics risk valuations that run complex Monte Carlo simulations off the Compute Grid
- Designed greenfield new iteration of trade discovery on the compute grid, building a dependency tree of trade related resources and leveraging compute grid elasticity to maximise efficiency and adhere to ever-changing compute capacity requirements
- Implemented library to do Google Protobufs Serialization of PV of risk results
- Implemented enterprise circuit breaker of MQ to resolve production issue that resulted in server crashing and consequent loss of risk results
- Assessing and implementing caching technologies to support volumes using HTTP caching, Oracle Coherence local/remote caching, Grid Computing Caching technologies
- \*\* Integration with market data service for grid quant calcs
- \*\* Develop MarketData and risk config passing to quant libraries
- \*\* Interfacing with downstream position management, valuation model parameters configuration

_Yeti (Compute Grid Submitter)_

- Development of valuation system utilizing grid technologies and bank&#39;s analytics libraries serviced by exposed REST API
- Core programming of the IBM Symphony Grid API to launch worker calculations on the compute grid
- Implemented trade valuation monitoring tools and analysis with WebApi, HTML
- Implemented trade valuation performance profiling and reporting analysis via Splunk Enterprise
- Implemented capacity analysis data mining capabilities that extracts from compute grid performance metrics to produce periodic business capacity reports
- Grid computing scheduling policies, resource allocation, workload monitoring, task priority and pre-emption
- Implementing priority of workload whereby acquired deep knowledge of grid scheduling policies and the internal algorithm of pre-emption of tasks based on priority, selective reclaim of compute resources. This would be exposed via the API to end users so they can prioritize there workloads over 22,000 compute capacity world-wide
- Implemented quant execution metrics pipeline using Splunk Enterprise logging and designed dashboard visualization so that the firm wide 22K compute units can be visualized to identify bottlenecks and potential areas for maximisation
- Partook as an SME in Azure and GPU programme rollout
- Performance analysis on compute grid slot ratios, successfully delivered achieving 3 times compute capacity cutting TCO costs by 1/3

_Walrus (Desk Asset &amp;Model configuration provider)_

- Involved in architectural investigation and implementation of a greenfield configuration system which houses desk pricing parameters, pricing model data, instrument configuration, model parameters using WebAPI, MongoDB
- Drove the concept development and implementation of the Data Access Layer using MongoDB, successfully deployed cross-regional replication design, schema definition and release migration systems

As the lead developer of EDIT Valuation services, I covered all aspects of valuation services which include Grid Resource Allocation/Scheduling Optimization and building financial models with quant core libraries and business analysis with end users.
