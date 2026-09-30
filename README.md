Source Quality Decay Predictor
Pre-Spend Intelligence for Programmatic Job Advertising
What This Is

A proof-of-concept interactive web tool that predicts source quality decay in programmatic job advertising campaigns — estimating when and why applicant quality will collapse across channels, before budget is committed.

Built to explore a specific gap in programmatic recruitment platforms: by the time Cost-Per-Application (CPA) rises enough to trigger spend reallocation, the apply fraud and candidate recirculation causing it typically started 2–3 weeks earlier. Most platforms react to this signal. This tool tries to anticipate it.

Live tool: https://savantika5814-svg.github.io/sqd-tool/

The Problem It Targets

Programmatic recruitment platforms like Joveo's MOJO are highly effective at reactive optimization — detecting quality drops and reallocating spend in response. But the underlying decay follows a predictable behavioural chain:

Apply Friction
     ↓
Candidate Frustration → Spray-Apply Behaviour
     ↓
Genuine Candidate Pool Exhausted
     ↓
Channel Recirculates Stale Profiles
     ↓
Bot & Fraud Entry (inflated applications, collapsed hire rate)
     ↓
CPA Spikes → Platform Detects → Reallocates
             ↑
     2–3 weeks of budget already wasted

The core question: If these patterns are consistent enough across channels, role types, and geographies — could they be predicted before spend is committed, not after?

What the Tool Does

Configure a campaign across six parameters:

Parameter	Options
Role Type	Technology, Analytics, Finance, Operations, Sales, HR
Seniority	Entry, Mid, Senior, Leadership
Geography	Tier 1 Metro, Tier 2 City, US, UK, APAC
Campaign Duration	4 / 6 / 8 / 12 weeks
Channels	Naukri, LinkedIn, Indeed, Google Jobs, Shine, Monster, Meta, ZipRecruiter

Outputs:

Decay curve chart — projected Source Quality Score (Hires ÷ Applications) week-by-week per channel, with fraud entry zone highlighted
Summary KPIs — channels at high risk, average quality drop, earliest fraud entry week, % budget to deploy before decay threshold
Per-channel cards — peak quality, end-of-campaign quality, % decay, quality-retained bar, estimated fraud entry week
Budget reallocation table — channel-level action (Increase / Cap at optimal window / Front-load & cap), optimal spend window, rationale
Behavioural funnel — visual explanation of why decay happens, from friction to fraud
Key Insight: Why Channels Decay Differently
Channel	Peak Quality	Decay Rate	Fraud Entry	Why
LinkedIn	Highest	Slowest	Week 5	Professional network, higher intent, stronger fraud controls
Naukri	High	Moderate	Week 3	Large active pool but aggregator exposure increases recirculation
Indeed	Moderate	Moderate	Week 4	High volume, mixed intent, fraud enters mid-campaign
Google Jobs	Moderate	Fast	Week 3	Aggregated listings attract bot traffic early
Shine / Monster	Lower	Fast	Week 2	Smaller active pool exhausted quickly, high fraud exposure

Modifiers applied by role type (Analytics roles attract higher intent), seniority (Senior roles see lower decay), and geography (Tier 2 cities see ~12% quality reduction vs metro).

Three Things This Model Surfaces

1. Apply friction selects against quality, not just quantity. When friction is high, candidates who push through aren't the most qualified — they're the least selective. A high application count on a high-friction channel is a warning sign, not a success metric.

2. Spray-apply and bot behaviour are indistinguishable at the surface level. Both inflate application count while collapsing hire rate. But they need different responses — friction reduction fixes spray-apply, fraud suppression fixes bots. A platform treating them identically will fix the wrong thing.

3. The decay curve is a lagging signal. By the time CPA rises enough to trigger reallocation, the fraud and recirculation causing it started 2–3 weeks earlier. If behavioural patterns are consistent, the entry conditions for decay may be predictable before spend is committed.

Methodology & Honest Limitations

This is a proof-of-concept built on synthetic data. It is not a production model.

What informed the decay rate estimates:

Joveo's MOJO platform brochure — which explicitly identifies apply fraud and spam as the primary drivers of poor application-to-hire conversion
Joveo's Auto Insurer case study — showing 221% improvement in click-to-apply from reducing form friction, confirming friction as a measurable quality signal
Joveo's Inergroup case study — highlighting that without centralised visibility, quality decay goes undetected until CPA has already spiked
General knowledge of programmatic advertising fraud patterns from industry literature

What real validation would require:

Per-candidate application velocity data (time between applications across roles)
JD read-time before apply (to distinguish genuine vs spray-apply behaviour)
Actual source quality scores over campaign duration from a live platform
Channel-level fraud rate data over time

The behavioural chain (friction → frustration → spray-apply → audience exhaustion → fraud entry) is a hypothesis about mechanism, not a validated causal model. The fraud entry weeks and decay rates are estimated, not measured.

Tech Stack
Layer	Technology
Frontend	HTML5, CSS3, Vanilla JavaScript
Charting	Chart.js 4.4.1
Fonts	DM Sans, DM Mono (Google Fonts)
Hosting	GitHub Pages
Data	Synthetic — generated from probabilistic decay model

No backend. No database. Fully client-side. All decay calculations run in the browser.

Project Context

Built as a self-initiated analytical project while researching Joveo's programmatic recruitment platform for a Business Operations Intern application.

The goal was not to replicate what MOJO does — but to explore what a pre-spend intelligence layer upstream of MOJO might look like, and whether the behavioural drivers of quality decay are predictable enough to act on before a campaign launches.

Author

Avantika Sharma BBA — Finance & Business Analytics, Birla Institute of Technology Mesra (CGPA: 8.59/10) linkedin.com/in/avantika70 · github.com/savantika5814-svg

Proof-of-concept · Synthetic data · Not affiliated with Joveo
