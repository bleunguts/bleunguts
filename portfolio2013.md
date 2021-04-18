**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** 
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
