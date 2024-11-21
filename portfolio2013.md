**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2023-2021](https://bleunguts.github.io/bleunguts/portfolio2023)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)** 
# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2008 – 2013._

# Lloyds

_ **Period** __:_ Feb '13 - Sep '13

_ **Length** __:_ 7 months

_ **Team Members** _ **:** 3

_ **Technologies** _ **:** WPF, C# .NET 4.5, PRISM, MVVM, WPFToolkit, NUnit, WCF SOAP WebServices

_ **Environments** _ **:** Windows

_ **Methodology** _ **:** Agile

_ **Description** _ **:** Developed the WPF GUI for Lloyds Banking Group’s core ecommerce FX system. This system was responsible for mark-up structuring and pricing model configuration, with the WPF GUI interfacing via WCF Web Services with the Java SOAP web server.

_ **Projects** _ **:**

- Implemented features related to Dodd Frank regulations, enhancing the FX model pricing configuration module for traders 
- Collaborated with the trading desk to develop a custom WPF control that presented traders with a hybrid dropdown and checkbox control with instructional tooltips to help them select different pricing configurations.

# Credit Agricole

_ **Period** __:_ Feb '12 – Feb '13

_ **Length** __:_ 1 year

_ **Team Members** _ **:** 10+

_ **Technologies** _ **:** C#, Winforms, Infragistics Windows Controls, low-latency, .NET remoting, ECN FIX protocol, TypeMock, ANTS Performance Profiler, Reactive Extensions (RX)

_ **Environments** _ **:** Windows

_ **Methodology** _ **:** Agile

_ **Description** _ **:** In house eCommerce FX low-latency real-time pricing and trading execution platform. The GUI subscribed to RMDS Reuters price ticks, calculates and publishes sales prices to external clients through ECN FIX channels (360T, FXALL,RTFX) and to CA traders via RFQ or auto-trading configuration screens.

_ **Projects** _ **:**

- Developed enhancements for FX Spot, FX Forwards, FX Swaps, Options (Vanilla Sales & Structured FX)
- Implemented spread calculation based on traders' sales' spread, building forward points to price the corresponding asset classes (Forwards, Swaps, Options)
- Streaming new RICS from RMDS to generate live price tick input feed into the eCommerce platform, Implemented conflation of dropped price ticks improving overall system resilience.
- Support new QuickFix protocol ECN (360T, FXALL) for publishing prices to external downstream market interbank platforms
- Developed Cash Deal Request for Quote(RFQ) GUI screen, allowing traders to add their spreads in the FX pricing module
- Implemented price and trader spreads stream aggregation using a push-based SOA design pattern, extending the existing price/spread tick pub-sub pattern.
- Conducted Root cause Analysis for trading losses, investigating price and order execution logs. Isolated offending code related to latency and system latency tolerance limits, used Redgate Performance Profiler to analyze performance degradation trends in code resulting to the trading loss impact. Presented and resolved performance designs in the price subscription and trade execution pipeline.

# Trafigura

_ **Period** __:_ Apr '11 – Jan '12

_ **Length** __:_ 9 months

_ **Team Members** _ **:** 30 +

_ **Technologies** _ **:** C#/VB.NET, VS 2008/2010, WinForms, WiX, MSBuild, VB6, Teamcity, NCoverage, SQL Server, NUnit, VB 6, SAP Business Objects

_ **Environments** _ **:** Windows

_ **Methodology** _ **:** Agile

_ **Description** _ **:** Served as the lead developer for Trafigura’s Oil & Metals legacy enterprise platform, supporting one of the world’s largest end-to-end crude oil supply chains.  My role focused on reliability and performance in a high-stakes environment by enhancing code quality, devising development best practices, and coordinating sensitive production releases whereby operational efficiency directly impacts $70billion commodities under management.  Supervised and mentored 10+ developers driving critical improvements to code quality and development standards tailored to the high impact oil desks.

_ **Consultancy Experience** _: Our consultancy team orchestrated critical overhauls to mitigate risks by re-engineering release management processes and developing innovative tools to streamline production and system uptime.  I spearheaded initiatives to optimize middle-office trade capture and risk management, leveraging domain-specific expertise in crude oil logistics, futures pricing, and supply chain dynamics.

This successful engagement earned BJSS exclusivity with Trafigura, significantly expanding consultancy involvement within the company and solidifying our reputation for delivering high-impact transformative results. 

_ **Projects** _ **:**

- Developed middle office solutions for Trade Capture and Derivatives trading covering Oil & Natural Gas Futures , Options and Swaps.
- Enhanced the Oils Options module with Black-Scholes model calibration parameters, improving valuation precision for crude oil derivatives.
- Led complex release operations, coordinating efforts across seven teams to ensure smooth deployment and mitigate risks in a volatile production environment.

# UBS

_ **Period** __:_ Mar '10 – Oct '10

_ **Length** __:_ 7 months

_ **Team Members** _ **:** 5 (1 PM, 3 offshore developers)

_ **Technologies** _ **:** C# 3.5 .NET, .NET XML Web Services, VC++8, SVN SQL Server 2005, NUnit, WiX C++ Extensions, Wise for Windows MSI

_ **Environments** _ **:** Windows

_ **Methodology** _ **:** Agile, Cruise Control

_ **Description** _ **:** Acted as the C#/C++ Architect, leading the development of self-service products and deployment tools for UBS's Distributed Storage System group

Helped shape the engineering roadmap work which required revisions to the architecture to give the deployment tools used by UBS staff a plug-and-play feature architecture.

The core product was ADT Studio used by traders in Fixed income (FIRC), FX (FXCCT) and Equities to browse and install UBS in-house software.

_ **Projects** _ **:**

- C# feature development for ADT Studio packaging tool with a C++ gateway
- Conceptualized and Designed Plugin SDK for bank app owners to write their own plugins that they can drop into ADT Studio enabling their new apps to be downloaded by traders
- Refactored code with dependency inversion principle so that the primary SDK interfaces can be offered to consumers of the Plugin SDK
- Development of folder/file security to adhere to UBS security policy standards
- Development of authentication and authorization via Active Directory groups
- Technology assessment BITS (Background Information Transfer Service) a WIN32 COM API for downloading and uploading files via http inbuilt into win32 kernel
- Technology assessment and roadmap planning for a pluggable architecture to allow the business to add componentized features in a pluggable enable/disable fashion

# International Gaming Technology (IGT)

_ **Period** __:_ Jan '09 – Jan '10

_ **Length** __:_ 1 year

_ **Team Members** _ **:** 4 (1 scrum master, 3 developers)

_ **Technologies** _ **:** C# 3.5.NET, LINQ, Remoting, WCF, MS UnitTest, MoQ, Windsor IoC, VC++ 7, SQL Server 2005, Game Machine Protocol Development, WPF

_ **Environments** _ **:** Windows

_ **Methodology** _ **:** Scrum plugin for TFS, TFS Team Explorer, TDD

_ **Description** _ **:** IGT specializes in the design, manufacturing, distribution and sales of FOBT slot gaming terminals. Engaged in the greenfield development of a new CVT gaming system for FOBT betting terminals, managing communications between the C# server and C++ transport layer. (C# server, C++ transport layer, .NET 3.5)

_ **Projects** _ **:**

- Developed an orchestrating system for distributing game packages to hardware game terminals. (C#, gaming protocol SSAS)
- Developed communications layer to the BetServer (C++) that produces betting outcome calculations from a random seed.
- Implemented features on the Ticket in and Ticket out bet terminal management module (C#)
- Developed estate wide reporting module of gaming terminal PnL.

# Goldman Sachs

_ **Period** __:_ Feb '08 – Nov '08

_ **Length** __:_ 10 months

_ **Team Members** _ **:** 100+ strategists (5 teams in Core; Core QA, Core Install, Core Devs, Core Dbs, Quant Core Devs)

_ **Technologies** _ **:** Slang SecDb, Secdb inbuilt routines, quant routines, markup-language, dynamic table market data generation API, UI toolkit API

Low level diagnosis; VC++ 6 / 8, Java 1.4/1.6, Shell Scripting, CVS

Pricing models tests algorithms, quantitative routines, automated regression testing Infrastructure development, Slang technology tools, issue tracking tools, performance analysis tools development

_ **Environments** _ **:** Windows / RHEL4 Linux / Solaris

_ **Methodology** _ **:** Open Source, Code Approvals

_ **Description** _ **:** As a Core QA strategist, my role required leadership and initiative to identify and resolve issues within the platform in the fast-paced, complex, mission-critical environment of the core SecDb programming platform. SecDb distributes financial calculation units worldwide via its in-house compute grid, covering equities, commodities, fixed income, IRP, and emerging markets across New York, London, Tokyo, Hong Kong, and Bangalore.

*Collaborative Problem-Solving:* Worked closely with core developers, quants, installers, and desk strategists to manage the bi-weekly SecDb releases.

*Production Issue Resolution:* Captured and resolved production issues reported by desks or identified through code inspection. This involved programming Slang scripts to navigate the extensive, open-source ecosystem deployed globally within the investment bank.

*Code Inspection and Analysis:* Regularly inspected code to identify design flaws, assess their impact, and determine potential risks. Focused on scalability and performance issues, particularly during volatile trading periods.

*Communication and Collaboration:* Effectively managed contradictory assumptions between developers, using judgment and team collaboration skills to ensure successful global releases, directly impacting Goldman Sachs' bottom line.

My work involved identifying areas requiring QA focus and promptly resolving issues to maintain the platform's integrity and performance. This proactive approach ensured the reliability and efficiency of SecDb releases, which are crucial to the firm's operations.

_ **Achievements** _ **:**

- Major strength is in root-cause analysis of problem, proposing solutions to core developers. My breadth of knowledge in programming languages allowed me to be effective in identifying root cause (C++, Java, .NET).
- Balance of prioritization, liaising with skilled team members, making right judgments is a day-to-day aspect and plays a crucial part to the tight bi-weekly release schedule
- Improved the core software release success rate from 5% to 100% through diligent process optimization and effective team management. This achievement was recognized by the Core team, leading to my sole responsibility for signing off SecDb releases. Upper management commended me for significantly enhancing the quality of global SecDb releases.
- Collaborated with global team members to resolve numerous defects and code flaws, reducing real-time trading downtime and mitigating system risk for corporate applications.
- Successfully drove QA process for upgrading VC6 to VC8(.NET) across all applications and compute hosts globally. Overcome challenges from the failed 2006 VC8 release by leveraging expertise in VC++ migrations to .NET and addressing memory/performance issues. Goldman Sachs now universally employs for pricing and financial applications.
- Acquired extensive experience with financial pricing applications.
- Pioneered the establishment of the Core QA presence in LDN. As the initial member, identified role requirements and optimized the use of time-zone differences between LDN and NY, leading to the expansion of the LDN team to two members.
- Conceptualized and implemented workflow enhancements in our QA Dashboard (Slang). This initiative involved identifying and addressing workflow inefficiencies, implementing improvements, and effectively communicating these changes.

_ **Projects** _ **:**

- RAMS (Regression Analysis) distributed over 1 billion calculation units (in-house grid) to verify pricing sensitive changes and discrepancies between release versions
- Price regression analysis tests pricing variations across SecDb assets including equities, commodities, fixed income and IRP.
- Day-to-day PreProd differences analysis, analysis of test results including pricing model tests, pricing variation results, SecDb Core technology test results.

As it is infeasible to achieve test coverage for every aspect of system, pioneered an idea to use code inspection to identify design flaws and collaborated with core devs to resolve issues reducing production defect rate dramatically.

- Conceptualize, implement and refine test algorithms systems, based on inspection of application code, known defects and very limited functional requirements.
- Heavy design + development of workflow tools, Designing & implementing tools for the QA infrastructure are a day-to-necessity at GS.
- Implemented speed / memory diagnosis tool that helps identify where in application discrepancy exists
- Tracking desks reports on software release issues via email or phone or reasoning from communications. As the nature of production defects are critical and often hold financial impact this was a crucial part of my role.
- Tracking issues that have been reported / found through testing / deduced from inspection to resolution. This required performing root cause analysis, finding offending developers, working with desks / traders ensuring their applications are in safe position in a highly complex and critical financial environment.
- Root cause analysis of price discrepancies and working with developers to resolve the issue.
- Worked with feature switches to back out problematic features during release
- Worked with development of code quality cyclomatic analysis to provide statistics for slang/Secdb code