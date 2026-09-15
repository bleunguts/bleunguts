**[HOME](https://bleunguts.github.io/bleunguts)** | **[CV PORTFOLIO](https://bleunguts.github.io/bleunguts/portfolio)** | **[2026-2025](https://bleunguts.github.io/bleunguts/portfolio2026)** | **[2023-2021](https://bleunguts.github.io/bleunguts/portfolio2023)** | **[2020-2013](https://bleunguts.github.io/bleunguts/portfolio2020)** | **[2013-2008](https://bleunguts.github.io/bleunguts/portfolio2013)** | **[2007-2003](https://bleunguts.github.io/bleunguts/portfolio2007)** | **[2003-2000](https://bleunguts.github.io/bleunguts/portfolio2003)** 
# _PORTFOLIO_

_This section outlines the projects I have been involved in during the period 2025 – 2026._

# (CIBC) Quantitative Solutions Group

_ **Period** __:_ May '25 – May '26

_ **Length** __:_ 1 year

_ **Team Members** __:_ Desk Quants, RAD Developers, Front-Office Tech Team

_ **Technologies** __:_ C# 9.0, .NET 9, C++ Interop, TPL, .NET Channels, Solace MC, KDB/Q (q timewindow functions), Python, ASP.NET Core, Grafana, Kibana, Bloomberg, Refinitiv RMDS, Broadway TOC, Excel

_ **Environments** __:_ Windows, Linux

_ **Methodology** __:_ Agile, Microservices, Low-Latency Messaging, Event-Driven Architecture

_ **Consultancy Experience:** _ Quant Developer, eFI Trading Platforms, Interest Rate Derivatives, Fixed Income Risk

_ **Description** __:_

Joined CIBC's Quantitative Solutions Group to build a greenfield electronic trading platform for interest rate swaps, integrating proprietary C++ quantitative libraries, real-time pricing models, and low-latency tools for front-office desks.

The eFI platform processes live market data streams and delivers real-time valuation, pricing analytics, and curve management tools to front-office traders.

[Responsibilities:](#)
The role demanded full technical ownership of quantitative tool delivery, from wrapping C++ pricing libraries and building C# front-office trading services to configuring low-latency calculation paths, automating diagnostics, and integrating streaming UI components. Led UAT and production releases for end-to-end price flows, indicative pricing streams, and live diagnostics tools while collaborating directly with desk quants and RAD developers to optimize front-office workflows.

[Involvement:](#)
Worked on fixed income pricing and yield curve construction methodologies (OIS, CORRA). Responsibilities included engineering multi-source pricing logic, constructing automated fallback and calculation chaining workflows, extending rates analytics across short-end bond yields and long-end swap rates, capturing underlying OTR bond changes during curve rolls, and converting pure Excel pricing sheets into high-performance C# components. Operationalized telemetry and monitoring using KDB/Q timewindow queries alongside Grafana and Kibana dashboards for live valuation stats.

[Skills Required:](#)
The role required strong domain knowledge in rates and fixed income derivatives, broad technical engineering depth spanning C# microservices, low-latency messaging, and C++ interop, alongside strong collaboration skills to partner effectively with desk quants, traders, and infrastructure engineers.

_ **Projects** __:_

_Greenfield C# / C++ Pricing Engine & Quant Integration_

[Objective:](#) Integrate proprietary C++ quantitative analytics into high-performance C# front-office services to enable low-latency real-time pricing for interest rate swaps.

- Integrated proprietary C++ quant libraries and calculators into C# front-office trading systems using native interop wrappers.
- Optimized low-latency calculation paths, introduced configurable CSV-driven error handling, and scripted automated pricing diagnostics.
- Standardized debugging, testing, and dependency mapping for core pricing utilities to accelerate desk releases.

_Multi-Source Rates & Yield Curve Construction Engine_

[Objective:](#) Build robust pricing logic and multi-curve management tools to calculate real-time swap rates derived from underlying bond yields and spreads.

- Designed and enhanced bond and swap pricing calculators, including multi-curve construction (OIS, CORRA) and curve management tools.
- Implemented multi-source pricing logic (e.g. deriving real-time swap rates from bond yield + swap spread) with automated fallback logic and calculation chaining.
- Extended analytics coverage across fixed income: short-end bond yields, long-end swap rates, price flows, curve rolls (capturing underlying OTR bond changes), and full conversions of pure Excel pricing sheets into native services.

_Low-Latency Streaming & Telemetry Operations_

[Objective:](#) Stream real-time pricing updates to front-office UIs and implement live operational diagnostics for market data flows.

- Collaborated with desk quants and RAD developers to streamline UI integration via Solace MC event streams and optimize front-office workflows.
- Operationalized KDB/Q timewindow queries alongside Grafana and Kibana dashboards for live valuation monitoring, pricing anomaly detection, and data flow tracking.
- Led UAT and production releases for end-to-end price flows, indicative pricing streams, and live diagnostics tools.