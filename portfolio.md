**[HOME](https://bleunguts.github.io/bleunguts)**   
# CV Portfolio
This portfolio consists of three sub sections spanning from 2003 to present (sub-sections: 2003-2007, 2008-2014, 2014-2020)

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

# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2008 – 2013._

# Credit Agricole

**Period** _:_ Feb &#39;12 – Feb &#39;13

**Length** _:_ 1 year

**Team Members:** 10+

**Technologies:** C#, Winforms, Infragistics Windows Controls, low-latency development, .NET remoting, ECN FIX protocol, TypeMock, ANTS Performance Profiler, Reactive Extensions (RX)

**Environments:** Windows

**Methodology:** Agile, Design Patterns for price/spread tick subscription model

**Description:** Foreign Exchange eCommerce in-house system low-latency real-time pricing and trading execution platform. The Winform GUI system subscribes to RMDS Reuters price ticks and calculates and publishes sales prices to external clients through ECN FIX channels (360T, FXALL,RTFX) and for internal traders via a Request For Quote (RFQ) or auto-trading config screens.

**Projects:**

- Developing enhancements and support for new products for the following asset classes FX Spot, FX Forwards, FX Swaps, Options (Vanilla Sales &amp; Structured FX)
- Included spread calculation based on traders and sales spread building forward points for corresponding derivative products (Forwards, Swaps, Options)
- Streaming new RICS from RMDS to generate live price ticks as input to the eCommerce system, implemented resilence due to dropped price ticks via conflation
- Support new QuickFix protocol ECN (360T, FXALL) for publishing prices to external downstream market interbank platforms
- Cash Deal Request for Quote(RFQ) GUI development screen for in-house traders to add their spreads before executing trades
- Implemented price and trader spreads stream aggregation push-based SOA design
- Root cause Analysis for trading losses which involved investigating price and order execution issues via log file inspection related to latency (system latency tolerance limit). Identified business critical doing code performance analysis using Redgate Performance Profiler &amp; performance counters. Presented and resolved performance designs to the price subscription and trade execution pipeline.

# Lloyds

**Period** _:_ Feb &#39;13 - Sep &#39;13

**Length** _:_ 7 months

**Team Members:** 3

**Technologies:** WPF, C# .NET 4.5, PRISM, MVVM, WPFToolkit, NUnit, WCF Soap Webservices

**Environments:** Windows

**Methodology:** Agile

**Description:** WPF GUI development for LBG&#39;s core ecommerce FX system responsible for markup structuring and model pricing configuration store. WCF GUI client interfacing via WCF Web services to a Java Soap webservice.

**Projects:**

- Implemented features related to Dodd Frank regulations by developing enhancements to the model pricing configuration used by trading to collaborate their FX pricing models
- Speaking directly with the trading desk to source requirements for a WPF custom control which presented traders with a hybrid dropdown and check box control with tool tips to help them select different pricing configurations

# Trafigura

**Period** _:_ Apr &#39;11 – Jan &#39;12

**Length** _:_ 9 months

**Team Members:** 30 +

**Technologies:** C#/VB.NET, VS 2008 &amp; VS 2010, WPF, WiX, MSBuild, VB6, Teamcity, Sql Server, NUnit, NCoverage, Visual Basic 6, SAP Business Objects

**Environments:** Windows

**Methodology:** Agile

**Description:** Lead developer (BJSS) for Trafigura&#39;s integral Oil &amp; Metals legacy enterprise platform. Supervision and mentoring 10+ team members in the implementation &amp; delivery of development effort.

**Consultancy Experience** :

One of the major things our consultancy team came in to solve was the sensitivity of the releasing to the production and the impact of defects.

I drove innovations to enhance code quality, code analytics, devising global development standards, team hiring and building for the trade capture and derivatives trading system

Achieved client recognition and awarded exclusivity multiplying our consultancy headcount more than ten fold

**Projects:**

- Front office/Middle office development for Trafigura&#39;s integral platform in Trade Capture, Derivatives trading (primarily Oil &amp; NATGAS Futures/Options/Swaps)
- Implemented additional BS model calibration parameters in the Oils Options module
- Release management activities which include coordinating with up to seven teams to bring release artefacts into a global &amp; volatile production environment

-

# UBS

**Period** _:_ Mar &#39;10 – Oct &#39;10

**Length** _:_ 7 months

**Team Members:** 5 (1 PM, 3 offshore devs)

**Technologies:** C# 3.5 .NET, .NET XML Web Services, VC++8, SVN SQL Server 2005, NUnit, WiX C++ Extensions, Wise for Windows MSI

**Environments:** Windows

**Methodology:** Agile, Cruise Control, Trac

**Description:**

I acted as the C#/C++ Architect which was responsible for leading development of the self-service products and deployment tools for the &#39;Distributed Storage System group&#39; at UBS.

Helped shape the engineering/roadmap work which required revisions to the architecture to give the deployment tools used by UBS staff a pluggable feature architecture .

The core product was ADT Studio deployment tool for traders working in Fixed income (FIRC), FX (FXCCT) and Equities

**Projects:**

- C# feature development for ADT Studio packaging tool with a C++ gateway
- Development of folder/file security to adhere to UBS security policy standards
- Development of authentication and authorization via Active Directory groups
- Technology assessment BITS (Background Information Transfer Service) a WIN32 COM API for downloading and uploading files via http inbuilt into win32 kernel
- Technology assessment and roadmap planning for a pluggable architecture to allow the business to add componentized features in a pluggable enable/disable fashion

# International Gaming Technology (IGT)

**Period** _:_ Jan &#39;09 – Jan &#39;10

**Length** _:_ 1 year

**Team Members:** 4 (1 scrum master, 3 devs)

**Technologies:** C# 3.5.NET, LINQ, Remoting, WCF, MS UnitTest, MoQ, Windsor IoC, VC++ 7, SQL Server 2005, Game Machine Protocol Development, WPF

**Environments:** Windows

**Methodology:** Scrum plugin for TFS, TFS Team Explorer, TDD

**Description:**

IGT has been the leading company specializing in design, manufacturing, distribution and sales of computerized gaming equipment. Greenfield development of a new CVT gaming system which manages an enterprise of FOBT betting terminals (C# server, C++ transport layer, .NET 3.5)

**Projects:**

- Develop orchestrating system that distributes game packages to hardware game terminals. (C#, gaming protocol SSAS)
- Develop communications to BetServer C++ that receives a random seed for betting outcome calculations
- Implementing features on the Ticket in and Ticket out bet terminal management module (C#)
- Estate wide reporting module of gaming terminal PnL.

# Goldman Sachs

**Period** _:_ Feb &#39;08 – Nov &#39;08

**Length** _:_ 10 months

**Team Members:** 200+ strategists (5 x teams Core QA, Core Install, Core Devs, Core Dbs, Quant Core Devs)

**Technologies:** Slang SecDb, secdb inbuilt routines, quant routines, markup-language,

dynamic table market data generation API, UI toolkit API

Low level diagnosis; VC++ 6 / 8, Java 1.4/1.6, Shell Scripting, CVS

pricing models tests algorithms, quantitative routines, automated regression testing Infrastructure development, slang technology tools, issue tracking tools, performance analysis tools development

**Environments:** Windows / RHEL4 Linux / Solaris

**Methodology:** Agile

**Description:**

As a Goldman&#39;s core strategies QA member we are given a sole focus, teams to communicate with leadership and initiative we identify areas within the environment that require a QA focus and take to resolution. This strategies model is imperative in such a fast-paced, critical investment banking context.

As part of Core QA team we deal with complex Quality Assurance techniques, such as code inspection of design flaws / possible future defects, handling implied assumptions from developer to developer, building a timely distributed regression testing daily infrastructure for global testing, analysis of cyclomatic complexity of code, and ultimately, low level API test crafting for complex code entry points.

Scalability and performance issues identification through code inspection, engineering techniques are also a crucial instrument as we are dealing with highly transactional, mission critical pricing/trading systems world wide.

Working as part of the core strategies team focusing in quality assurance in bi-weekly releases Slang / SecDb (Goldman Sachs financial programming platform). As a QA Operations Strategist, my role involves working closely with a world-class team of core developers, core quant team, core install team, desk strategists / traders focusing on high quality releases that are distributed to all financial units world-wide (equities, commodities, fixed income, IRP, new markets in NY, LDN, TKO, HK, BGL).

Working in a dynamic, high-paced &amp; with highly complex financial/API-level applications, judgment &amp; team collaboration skills are imperative as global releases have a direct impact on the bottom line of Goldman Sachs.

**Acheivements:**

- Major strength is in root-cause analysis of problem, suggesting solution to developer. My breadth of knowledge in programming languages allows me to effectively identify root cause (C++, Java, .NET).
- Balance of prioritization, liaising with skilled team members, making right judgments is a day-to-day aspect and plays a crucial part to the tight bi-weekly release schedule
- Successfully conceptualized + implementing workflow enhancements into our existing QA Dashboard system (Slang). This required reacting responsively &amp; accurately to introducing changes in current procedures usually via designing eWorkflow enhancements, taking defects to resolution in a timely matter.
- Contributed in improving core software release success rate from 5% to 100% (through diligent process optimization &amp; team command), thereafter was assigned responsible for signing off global releases of Slang / SecDb. Commended by upper management for improving the quality of global releases dramatically!
- Working with team to bring resolution countless defects &amp; flaws in code preventing down-time in real-time trading systems effectively saving costs
- Implemented / revised performance impact of releases which plays particular importance when introducing new OS platforms. Successfully drove QA process for VC6 to VC8 (.NET) upgrade for all applications/computers world-wide. With my experience of VC++ migrations to .NET and understanding of memory / speed potential issues. In 2006 core has failed to release VC8 because of the complexity of a global upgrade from legacy VC6 to VC8. With my knowledge &amp; strategic planning, Goldman Sachs world-wide now utilizes VC8 for all its pricing/financial applications.
- Have experience with dealing with financial pricing applications,
- Have crafted the Core QA presence in LDN – I started off as the sole member in LDN needing to determine, the requirements of the role, how to best utilize the differences in time-zones between LDN + NY. Successfully conceptualized + implementing workflow enhancements into our existing QA Dashboard system (Slang). This required reacting responsively &amp; accurately to introducing changes in current procedures usually via designing eWorkflow enhancements using Slang &amp; SecDb. My contribution has allowed LDN team to grow reaching 2 members now.
- Improved core software release success rate from 5% to 100% (through diligent process optimization &amp; team command), thereafter was assigned responsible for signing off global software releases.
- Implemented / revised performance impact of releases which plays particular importance when introducing new OS platforms. Successfully drove QA process for VC6 to VC8 (.NET) upgrade for all applications/computers world-wide. With my experience of VC++ migrations to .NET and understanding of memory / speed potential issues, Goldman Sachs world-wide now utilizes VC8 for all its pricing/financial applications.

**Projects:**

- RAMS (Regression Analysis) distributed calcs running on EventD (in-house grid built on C++ CORBA)
- Price regression analysis on all SecDb assets (equities, commodities, fixed income, IRP)
- Day-to-day PreProd differences analysis, analysis of test results including pricing model tests, pricing variation results, SecDb Core technology test results. As it is infeasible for tests to always cover every aspect of system, inspection of code to identify flaws in design plays a very important role in preventing defects from hitting production.
- Conceptualize, implement and refine test algorithms for our cutting-edge proprietary systems, based on inspection of application code, known defects and very limited functional requirements.
- Critique &amp; offer analysis/solutions to C++ models / quant routines that are pricing incorrectly
- Heavy design + development of workflow tools, Designing &amp; implementing tools for the QA infrastructure are a day-to-necessity at GS.
- Implemented speed / memory diagnosis tool that helps identify where in application discrepancy exists
- Tracking desks reports on software release issues, these come in any form email / phone / reasoning. Nature of production defects are critical and have a direct financial impact.
- Tracking issues that have been reported / found through testing / deduced from inspection to resolution. This requires performing root cause analysis, finding offending developers, working with desks / traders ensuring their applications are in safe position in a highly complex financial environment
- Root cause analysis of price discrepencies and working with developers to resolve the issue.
- Worked with Backout Variables to back out problematic features during release
- Worked with development of code quality cyclomatic analysis to provide statistics for slang/secdb code
- Analysis &amp; delivery of programming solution to critical production defects
- Code inspection and Design/implementation of faciliting tools in Slang
- Monitoring issues desks reports on software release issues. Software release defects are critical when they are released in production environments as they can have a direct financial impact.
  - Tracking issues that have been reported / found through testing / deduced from evidence to resolution. This requires performing root cause analysis, finding developers responsible, working with desks / traders ensuring their applications are in safe position + working with developers to resolve desks problems.
  - Major strength is in root-cause analysis of problem, suggesting solution to developer. My breadth of knowledge in programming languages allows me to effectively identify root cause (C++, Java, .NET).
- Monitoring regression test results for different stages of releases.
  - Analysis of test results including Pricing model tests, Pricing variation results, SecDb core technology test results
  - Conceptualize, implement and refine test algorithms for our cutting-edge proprietary systems, based on inspection of application code, known defects and very limited functional requirements.
  - Suggest reasons models or quant routines are pricing incorrectly
- Heavy design + development of workflow tools, Designing &amp; implementing tools for the QA infrastructure is a day-to-day activity at GS.
  - Implemented speed / memory diagnosis tool that helps identify where in application discrepancy exists
  - Implemented changes to our eWorkflow system to allow for improvement in process workflows
- Balance of prioritization, delegation to more skilled members, managing the tight bi-weekly schedule is crucial to day-to-day work in my role.

# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2004 – 2007._

# Siemens

_ **Period** __:_ Jul &#39;05 – Jul &#39;07

_ **Length** __:_ 2 years

_ **Team Members:** _ _12+_

_ **Technologies:** _ C#, Composite UI Application Block, WinForms, .NET Remoting, MSMQ, NUnit

C++ 6.0 &amp; 7.0, MFC , COM,, C++ Cryptography, ATL/STL containers, ODBC, Crystal Reports, SQL Server 2005/2008 TSQL/UDF/View/StoredProc/, XML.

Smart card &amp; DVR windows driver APIs, hardware/firmware interfacing via RPC

_ **Environments:** _ Windows XP/Vista

_ **Tools:** _ CVS, PR Tracker, Wise for Windows Installer, Windows Vista Certification

_ **Methodology:** _ Custom Process Engineering (as it involved both Software and Hardware coordinated delivery)

_ **Description:** _

Sipass has been installed in 1300 sites worldwide over 55 countries world-wide. Sipass has secured 2000 doors in Huawei HQ, 784 doors in Beijing Television Center and 744 doors in Wohnpark Alt Erlaa in Austria.

_ **Acheivements:** _

- Smart Card Hardware API development expertise
- Major innovation of our product which is the research &amp; development of a component to support smart card access control on personal office rooms cylinders. This is one of the two core selling points for our next release which the project manager assigned to me to take care of.
- Managed the suite of Digital Video Recording (DVR API) division of SiPass using C++ / COM interfacing with 3rd party developments. The video surveillance division involved programmable image capturing sequencing based on trigger-able events such as tripping of alarms. I had to developing enhancements using C++ COM to according to 3rd party vendor requests. (C++, ATL, STL, COM)

- Achieved appraisal for my succinct analysis skills delivering solutions to critical hard to solve live bugs which had a global impact.
- Successfully resolving 50+ show-stopping site problems mitigating delivering effective solutions with zero-risk. Each time I deliver a solution to a problem, I will identify if that mistake pattern exists elsewhere in the large-scale system effectively improving the quality of the system by delivering complete solutions. C++, C# .NET, COM, .NET Remoting, SQL Server, Wise, Memory Leaks

- With my drive to take ownership &amp; proven ability to deliver zero-risk solutions the project manager gave me more show-stopping site problems to solve, more enhancements to develop and more development areas to look after. After acknowledging my ability to manage time effectively with concurrent tasks &amp; my leadership qualities I was assigned team lead for 1-3 engineers so that I can transit out and concentrate on other critical design areas, I held responsibility of the outcome of the leading tasks.
- Resolved issue to do with OLE Server Busy error which was difficult to reproduce and for many years the anomaly was left unsolved. I isolated the issue to be a performance issue in the C++ RPC connectivity to the server. Resolved &amp; delivered with assistance from engineers that had experience with building this antique module. (C++, MFC)
- Designed &amp; implemented 20+ system enhancements which were smaller requirements requested by product line (C# .NET, COM+ MFC, .NET Message Queue, Crystal Reports, C++)

- Received notoriety in my attention to quality, was assigned responsible for quality assurance of requirements, design &amp; API manuals from other engineers.
- Strategised to develop &amp; employ automation tool to cut down costs for the problematic localization process. SiPass is translated into 12+ languages and €1.5 million is spent in localization alone. In recognition to my initiative &amp; sense of ownership I became the SME and supervised 2-3 engineers to develop automated solution using C#, scripting, C++ API interfacing and was highly appraised for cutting the cost of effort by 40+%. (C# .NET, Scripting, C++ RC-WinTrans API)
- Packaging and setup for our security product using Wise For Windows Installer
- Windows Vista compatibility technical optimization tickets in adherence to Microsoft Windows Vista standards

_ **Projects** __:_

_SiPass Enterprise_

- Designed, implemented from inception the alarm module for the new SiPass Enterprise system. The alarms alerting module in C# which will provide a system wide ability to trigger, acknowledge, report on alarms. This would need to be integrated with SiPass as well. (C# .NET, WinForms .NET, Composite UI Application Block, NUnit .NET, COM+ Message Queue, XML)
- Designed, implemented licence generation mechanism with a custom hashing algorithm for SiPass Enterprise (C++.NET, NUnit .NET, C++ COM Unit Test, ASP.NET Unit Test). Managed the licensing division of SiPass Enterprise.

_Sipass Hardware Mechanics_

- Designed &amp; implemented module that supports pre-released smart card readers (2 developments; GemPlus, OmniKey) using C++ API interfacing. (C++, OO Design, API interfacing). Managed the smart card division of SiPass from thereon.
- Designed &amp; implemented a module that introduced turnstile door types to the system. Required conceptualisation of the turnstile operation. (C++, MFC, COM, SQL Server, XML)
- Lead the suite of Digital Video Recording division of SiPass using C++ / COM interfacing to 3rd parties for them to develop device drivers. This included developing enhancements using C++ COM to maintain the video stream between the hardware to SiPass. (C++, ATL, STL, COM)
- Designed &amp; developed an innovative key marketable component which was to implement a smart-card digital locking cylinder (HID&#39;s new R&amp;D invention) to create a wireless unlocking effect for end-users. This invention was designed I supervised 1 engineer with this project and the framework that I designed was to be used as a basis for future client-server developments. (C#, .NET, Design Patterns, .NET Remoting, SQL Server)

_SiPass Integrated_

- Designed &amp; implemented enhancement where visitors entered the building on particular dates (C++, MFC)
- Designed &amp; implemented enhancement where users can scroll through a large database of cardholders with high performance &amp; concurrency considerations. (C++, MFC, SQL Server UDFs)
- Designed &amp; implemented mechanism for system-wide fetching of database credential information. (C++, COM, C++ .NET, C# .NET, C++ Cryptology, Wise for Windows Installer). This was difficult because it will be used for all future projects that needed to access the database.
- Designed &amp; implemented mechanism for system-wide fetching of system sensitive database credential information. (C++, COM, C++ .NET, C# .NET, C++ Cryptology, Wise for Windows Installer)
- Integrated an external legacy access control system into SiPass by designing a migration tool and developing integration features into SiPass. (C++, COM, MFC, ODBC)
- Strategized an automation tool to cut down costs for the problematic localization process. SiPass is translated into 12+ languages and €1.5 million is spent in localization alone. I took initiative &amp; identified possible ways to increase productivity by using programming techniques. Assigned lead of 2 - 3 engineers to develop an automated solution using C#, scripting, C++ API interfacing (C# .NET, Scripting, C++ RC-WinTrans API). Received high appraisal for cutting the cost of effort by 40+%.
- Resolved issue with where user sessions were not identified properly and caused reporting of logged in users incorrectly, C++, COM
- Designed &amp; implemented 20+ system enhancements, C++, C# .NET, COM+ MFC, .NET Message Queue, Crystal Reports
- Designed &amp; implemented VC++7 module to detect which SQLServer versions are available on the domain &amp; implementing into Wise for Windows Installer. (VC++7, Wise for Windows Installer)
- Detected &amp; resolved C++ quality of code criteria to pass Windows Vista Certification
- Integrated a complete access control system into SiPass by designing a migration tool and developing integration features into SiPass. (C++, COM, MFC, ODBC)

# AMAT

_ **Period** __:_ Jun &#39;04 - Jul &#39;05

_ **Length** __:_ 1 year 1 month

_ **Team Members** __:_ 8 Consultants ( 3 developers, 2 testers, 3 project managers)

_ **Technologies** __: C# .NET, ASP .NET, .NET Nuke, .NET NEO, Java 1.4 applets, Lotus Notes 7 LotusScript/FormulaScript OLE, VB6, VBA, HTML/CSS, JavaScript/VBScript, SQL Server_

_ **Environments** __:_ Windows 2000 Server and XP / Linux CVS

_ **Tools:** _ CVS, Bugzilla

_ **Methodology** __:_ TDD, BDD, Story based development, Feature Based Development

_ **Description:** _

AMAT is a software consulting start-up specialising in developing software solutions for the mortgage industry.

The core product is called MortgageFirst which provides a Client Relationship Management (_CRM_), and _workflow for_ mortgage associates to drive their enterprise process.

_ **Consultancy Experience:** _

As a boutique software consultancy house, I was actively involved in the full SDLC from inception to delivery:

- On site software sales for new client acquisition promoting value add to their day-to-day operations
- Direct client request support for the product over the telephone or onsite
- The major components I have been assigned to manage are the document automation component, commissions distribution component, data migration from existing databases
- Customer facing role involving requirements gathering, business analysis of mortgage workflow, commissioning rule and loan structuring nuances for new clients
- Post software development I was responsible for user training for the finished product presenting to 10+ mortgage consultants
- Windows server administration for deployed software maintenance
- Linux server system administration that hosts source control (CVS) and data backup
- Internal IT Administrator which includes checking internal infrastructure, maintaining the CVS repository &amp; providing the team with software tools &amp; suggestions that may improve the running of the business

_ **Projects** __:_

_OptusWorld_

Is a Data capture and Reporting enginedeveloped with .NET Nuke (ASP.NET framework) and .NET NEO for the backend DAO layer. Scoped and developed an easily maintainable web application for Optus marketing campaigns.

Mystery shoppers unconsciously survey an Optus store to tell the service and later report on their feedback to the system. The system will deliver reports based on certain criteria to the head marketing team to analyse the service proficiency of Optus stores.

(.NET 1.1, .NET 2.0, C#, ASP.NET, .NET Nuke, NEO, SQL Server, CSS, HTML, JavaScript, XML)

_Commissions C#.NET_

A system that facilitates funder&#39;s to upload their spreadsheets for commissions processing.

Developed rules based module to handle disparate specific business requirements for commissions&#39; reconciliation which were disparate for the many different clients

Developed a C# data extraction bridge from C# to Lotus Domino via COM interfacing

Developed new Lotus Domino ODBC data adaptor for the new C# commissions system

_MortgageFirst_

- Loan Processing workflow system allows financial consultants to keep track of the full lifecycle of loans till post-settlement
- CRM keeps details, associated personal documents, associated applications of clients in the document management system
- keeps details of brokers and introducers for commissioning purposes
- keeps details of banks for commissioning purposes
- provides &#39;Income Conversion&#39; calculator, &#39;Property Investment calculator&#39;, Cost estimate calculators
- developed mail merge facilities for bulk marketing campaigns
- Allowed brokers to create appointments and tasks which they can associate to related accountants etc.
- loan status tracking
- calendar that synthesises the appointments
- creating reports for employee performance tracking, introducer tracking, overall loan statuses, loan processing deficiencies
- creation of product matrix that compares different loan products
- creation of serviceability calculator .NET C#, ASP.NET
- loan amortisation calculation

_BP Motorist_

An online transaction processing (OTP) reporting engine that data captures product assessments input. The core purpose is for BP to conduct product assessment at an aggregate company level over the many disparate offices.

_ **Achievements:** _

- Domain expertise in Mortgage workflow
- Designed an agile requirements management system to manage projects on site and in the office
- Successfully communicated the benefits of configuration management (CVS)
- entire SDLC including business analysis through to training support for the mortgage business domain
- Successfully developed and migrated a medium-scale database for Acceptance Finance improving their day-to-day productivity dramatically whilst preserving two years of their business data
- Re-factored and improved the document generation modules / commissions module to a point which slashed development costs in adding addition features to this core module of the MortgageFirst database system

_ **Timeline** __:_

- Acceptance Finance (mortgage brokers)
- Austral (mortgage managers, do residential / investment / commercial loans and investment finance)
- The Capital Trust (mortgage brokers)
- Verix ( mortgage brokers)
- Aussie Mortgage Solutions (non-bank lender mortgage originator and mortgage manager)
- Prudent (mortgage brokers)
- Select (mortgage aggregators)

_mortgage manager_ - (mortgage banker) A company, individual or institution that originates mortgages. Mortgage bankers use their own funds, or funds borrowed from a warehouse lender, to fund mortgages. After a mortgage is originated, a mortgage banker might retain the mortgage in portfolio, or they might sell the mortgage to an investor.

_mortgage originator_ - an institution or individual that works with a borrower to complete a mortgage transaction. A mortgage originator can be either a mortgage broker or a mortgage banker, and is the original mortgage lender. Mortgage originators are part of the primary mortgage market.

# UTS

_ **Period** __:_ Jul &#39;03 - Jun &#39;04

_ **Length** __:_ ~1 year

_ **Team Members** _ **:** Independent (working with Programme Coordinator of Software Engineering)

_ **Technologies** _ **:** J2EE, ACE+TAO Corba, JacOrb, Jini, .NET, CVS, Intersystems Caché OODBMS

_ **Environments** _ **:** Linux/Windows

_ **Methodology** _ **:** IEEE Software Engineering Process, UML modelling, Rational Rose, Archstyler

_ **Description** _ **:**

This role was a unique role specially created by Postgraduate Software Engineering Coordinator Mr. Zenon Chaczko in recognition of my technical competence, entrepreneurship and ability to think for myself.

This placement was created for assistance in subject development for the Software Engineering Major core subjects (software architecture, software systems analysis and design, software systems middleware) at undergraduate / postgraduate level of the Software Engineering disciplines.

_ **Acheivements** _:

- Training &amp; co-supervision of undergraduate thesis project that deals with Web Site Development for the software education laboratory. WebML+, HTML, CSS
- Training &amp; support of postgraduate thesis project that deals with a network performance management system project using Sun Jini technology
- Full lifecycle development of a PDA class library, which provides students with a framework for software development using PDA&#39;s. (Java based embedded, Server-side Java, DBMS – Intersystems Cache)
- Ability to provide formal lectures / public technical speaking

_ **Projects** _ **:**

- Supervising students in software design for particular technologies throughout the , software development life cycle (J2EE, Corba, Jini, J2SE, Microsoft .NET.)
- Class lectures &amp; presentations for the following list of technologies

Java platform; J2EE, J2SE, Embedded Java

- Application Server support; BEA Weblogic 8.1, SunOne Application Server 6.0
- CVS on Unix
- Installation, configuration and assistance on using software development environments, languages, configuration management and modelling.
- Supervising in the application of software engineering process using CASE tools, Rational Suite, Archstyler.
- Supervising Intersystems Caché OODBMS development
- Presentations and tutorials on Java 2 EE technology (Autumn 2003)
- Design &amp; development of new software frameworks for potential projects
- Corba tutorials (May 2003)
- Installed, designed new mobile enterprise system that presents wireless connectivity to an enterprise control context (20 working days – in progress)
- Java &amp; .NET Mobile development for Personal Digital Assistance (PDAs)
- Bluetooth Wireless Radio Technology on Linux enterprise connectivity application
