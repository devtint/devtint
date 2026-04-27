<div align="center">

# TYRELL

security researcher, tool developer, automation nerd from bangkok.

i break things, figure out why they break, then build tools so others can break them faster.

[portfolio](https://tintnaingwin.vercel.app) · [telegram](https://t.me/BadCodeWriter) · [github](https://github.com/devtint)

</div>

---

### who i am

currently studying digital technology at kasem bundit university. when i'm not in class, i'm building security tools, writing automation scripts, and poking at whatever network i can find.

i started with simple python scripts and got obsessed. now most of what i do sits somewhere between offensive security, full-stack development, and just general automation of things that shouldn't need to be manual.

my approach: read the source, test the edge cases, automate the boring parts, document the weird parts.

---

### what i'm working with

| languages | frameworks & runtime | security & ops |
| :---: | :---: | :---: |
| <img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white" /> | <img src="https://img.shields.io/badge/next.js-000000?style=for-the-badge&logo=next.js&logoColor=white" /> | <img src="https://img.shields.io/badge/nuclei-00C4CC?style=for-the-badge" /> |
| <img src="https://img.shields.io/badge/typescript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" /> | <img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black" /> | <img src="https://img.shields.io/badge/burp_suite-FF6633?style=for-the-badge&logo=burp-suite&logoColor=white" /> |
| <img src="https://img.shields.io/badge/javascript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" /> | <img src="https://img.shields.io/badge/node.js-339933?style=for-the-badge&logo=node.js&logoColor=white" /> | <img src="https://img.shields.io/badge/owasp-000000?style=for-the-badge&logo=owasp&logoColor=white" /> |
| <img src="https://img.shields.io/badge/bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white" /> | <img src="https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" /> | <img src="https://img.shields.io/badge/kali_linux-557C94?style=for-the-badge&logo=kali-linux&logoColor=white" /> |
| <img src="https://img.shields.io/badge/go-00ADD8?style=for-the-badge&logo=go&logoColor=white" /> | <img src="https://img.shields.io/badge/fastapi-009688?style=for-the-badge&logo=fastapi&logoColor=white" /> | <img src="https://img.shields.io/badge/wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" /> |

---

### current focus

```
vulnerability research      -->  learning how things break at the protocol level
security automation         -->  building tools that do the repetitive recon work
web app pentesting          -->  api security, auth bypasses, logic flaws
reverse engineering         -->  static analysis, binary patching basics
ai integration in tooling   -->  using llms to help with template generation and triage
```

---

### projects

#### security tooling

---

**[NUCLEI_CNM](https://github.com/devtint/NUCLEI_CNM)**

a full management platform built around the nuclei vulnerability scanner. the goal was to get past the limitations of running nuclei directly from the cli and give it a proper operational interface.

what it actually does:
- full dashboard for managing nuclei scan templates, targets, and active scans
- ai-powered template suggestions based on target fingerprint and technology stack
- multi-node scan distribution so you can run concurrent campaigns without overloading a single machine
- real-time vulnerability feed with severity tagging, deduplication, and history tracking
- export-ready reports in json, pdf, and markdown for client deliverables
- api-first design so you can wire it into your existing security pipeline
- built on react + next.js frontend with a python/fastapi backend and postgres storage

---

**[CAPTIVE_AUDIT](https://github.com/devtint/CAPTIVE_AUDIT)**

purpose-built toolkit for testing captive portal security. most security tools are not designed with captive portals in mind, so a lot of common bypass techniques and misconfigurations go undetected.

what it actually does:
- multi-threaded authentication bypass probing across a configurable set of payloads and logic variations
- dns poisoning and dhcp spoofing detection tests
- automated mapping of the full portal flow: unauthenticated state, redirect chain, session handling, and post-auth behavior
- header injection testing for x-forwarded-for and other common proxy bypass vectors
- ssl stripping detection and certificate validation checks
- real-time network packet capture with protocol analysis at the ip, tcp, and http layers
- structured html and pdf report output with evidence attachments and remediation notes
- a web-based interface for running audits on-site from a laptop or termux session on android

---

**[SecurityHeaderScanner](https://github.com/devtint/SecurityHeaderScanner)**

an automated engine that checks how well web applications are configured at the http header level. this sounds boring but misconfigured headers are one of the most consistent sources of real-world vulnerabilities.

what it actually does:
- complete validation of all major security headers: csp, hsts, x-frame-options, referrer-policy, permissions-policy, cors, cto, and more
- detailed breakdown of what each header value actually means and what the risks are if it is missing or misconfigured
- owasp-aligned scoring rubric with weighted severity for each finding
- custom policy support, so you can define what an acceptable header configuration looks like for your specific environment
- diff mode, so you can compare a production site against a baseline and catch regressions
- integrates directly into ci/cd pipelines via github actions or any ci runner that supports cli tools
- outputs findings as json, junit xml (for ci test result dashboards), or human-readable markdown

---

**[Js-And-Endpoints-scanner](https://github.com/devtint/Js-And-Endpoints-scanner)**

a browser extension and cli combo for extracting hidden surface area from javascript files. js bundles contain a lot more information than most developers realize.

what it actually does:
- static regex analysis across loaded js files looking for api endpoints, internal routes, function names, and parameter names
- secret detection: api keys, tokens, base64-encoded credentials, environment variable names, and internal service urls
- real-time interception of xhr and fetch requests to build a live endpoint map during manual browsing
- exportable sitemap of discovered endpoints with method, parameter, and origin information
- supports both the browser extension interface for interactive recon and a headless cli mode for automated scanning pipelines
- deobfuscation support for common webpack and terser bundle patterns

---

**[API_PENTEST](https://github.com/devtint/API_PENTEST)**

an automated framework for finding vulnerabilities specific to rest and graphql api surfaces.

what it actually does:
- automated api crawling and surface discovery from openapi specs, postman collections, or live traffic capture
- fuzzing for broken object level authorization (bola/idor), mass assignment, and schema injection
- authentication bypass testing across jwt, api keys, session tokens, and oauth2 flows
- rate limiting and business logic abuse detection
- graphql introspection analysis and query fuzzing
- custom payload injection at every parameter, header, and body field
- integration with burp suite as an extension for use in manual testing sessions

---

#### tools and utilities

---

**[antigravity-usage](https://github.com/devtint/antigravity-usage)**

a monitoring utility for ai model consumption and quota tracking. built because i was burning through tokens without realizing it.

what it actually does:
- real-time tracking of token usage across all api calls to supported llm providers
- estimated cost calculation based on current provider pricing, updated regularly
- usage aggregation by project, model, and time period for proper budget management
- alert system that warns you before you hit quota limits
- export to csv or json for billing reconciliation

---

**[free-stack](https://github.com/devtint/free-stack)**

a living documentation repo covering how to run a full production web stack completely free by chaining together the free tiers of various cloud providers.

what it actually does:
- detailed setup guides for frontend (vercel/netlify), backend (fly.io/render), database (supabase/neon), and cache (upstash) layers
- performance benchmarks comparing different free-tier combinations under realistic load
- architecture diagrams for the most common use cases: api + db, full-stack saas, static site with serverless functions
- cost breakdowns showing exactly when and how you hit limits, and what to upgrade first
- community-contributed configurations for popular frameworks including next.js, fastapi, and express

---

**[WarpConfGen](https://github.com/devtint/WarpConfGen)**

configuration generator for cloudflare warp and wireguard-based zero trust setups.

what it actually does:
- automated generation of wireguard configuration files compatible with cloudflare warp endpoints
- device registration flow automation through the cloudflare api
- split-tunneling configuration support with per-app routing rules
- batch generation for managing multiple device configs across a team
- custom dns configuration injection and validation

---

### github stats

<div align="center">
  <img src="https://streak-stats.demolab.com?user=devtint&theme=default&hide_border=true&date_format=j%20M%5B%20Y%5D" height="165" />
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=devtint&theme=default" height="165" />
</div>

<div align="center">
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=devtint&theme=default&utcOffset=7" width="49%" />
  <img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=devtint&theme=default" width="49%" />
</div>

<div align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=devtint&theme=github-compact&hide_border=true" width="100%" />
</div>

---

### reach out

i'm open to collaboration, interesting security problems, or just talking about tools and techniques.

[telegram @BadCodeWriter](https://t.me/BadCodeWriter)

---

<div align="center">
  <sub>devtint · building things that break things · bangkok</sub>
</div>
