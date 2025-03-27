# GroqWarden + INtrack — Ultimate AI-Powered Cybersecurity Automation Framework

![Banner](https://img.shields.io/badge/GroqWarden-AI--BugBounty--Automation-purple?style=flat-square&logo=groq)

> **Author**: xkdai | Powered by Groq | Private Research Toolkit  
> **Status**: Private Intelligence & Recon Framework | Phase 2+  
> **Mission**: Automate. Analyze. Triage. Fix. Repeat.

---

## Overview

GroqWarden is the core of your automated cybersecurity arsenal — seamlessly fusing AI agents, bug bounty reconnaissance, CVE intelligence, payload testing, and AI-enhanced reporting. Paired with INtrack, a multi-threaded internet-wide scanner, it forms a powerful dual-stack designed for red teamers, hunters, and future security ops platforms.

Built by a beginner bug bounty researcher climbing to pro-level using their *own tool*.

---

## Features

### GroqWarden
- **AI-Powered Agents**: Groq-driven recon, secrets, EXIF, payloads, CVEs, reporting
- **Smart Recon Stack**: Subdomain discovery, URL parsing, parameter extraction
- **EXIFTron v7.0**: Metadata analyzer + PoC builder + AI triage
- **PoC Auto-Builder**: Generates working PoCs from AI triage
- **Secrets Scanner**: TruffleHog, Nosey Parker integration
- **Discord Alerts**: All modules auto-notify you
- **HTML Reports**: Beautiful, structured Markdown and dashboards
- **File Organizer**: AI-sorted repo cleanup, blacklist + logs
- **GroqBanner + Injector**: ASCII banners auto-added
- **Fail Recovery**: FixerAgent heals and recovers failed tools

### INtrack
- **Full Network Crawling**: Subnets, hosts, ranges, and random IPs
- **Vuln Scanners**: CVEs, instance detection, IoT & exposure detection
- **Multi-threaded Engine**: Ultra-fast scanning
- **Recon Trigger**: Send data directly to GroqWarden agents

---

## Architecture (Mermaid)

```mermaid
graph TD
    A[Main.py] -->|safe_run| B[ReconAgent]
    A --> C[SecretsAgent]
    A --> D[IntelBot]
    A --> E[ScreenshotAgent]
    A --> F[PayloadAgent]
    A --> G[PoCAutoBuilder]
    A --> H[ReportAgent]
    A --> I[FixerAgent]
    A --> J[ToolRunnerAgent]
    A --> K[GroqCluster Parallelizer]
    A --> L[EXIFTron AI + S3]
    A --> M[DiscordNotifier]
    A --> N[AutoOrganizer + Smart Config]
    A --> O[Dorking AI Bot]
    A --> P[bCheck AI Bot]
    A --> Q[INtrack Scanner Trigger]

    B -->|Writes| recon_logs
    C -->|Extracts| secrets/
    D -->|Summarizes| intel/
    F -->|Tests| pocs/
    H -->|Outputs| reports/
    N -->|Moves| organized repo/



⸻

Usage

Start Main Flow

python3 main.py

Full Recon on Domain

[?] Run full scan on a domain? y
[?] Enter domain: example.com

Run Specific Agents

[?] Run PayloadAgent? y
[?] Enter URL: https://site.com/search?query=test

Run GroqHound (EXIF AI)

triage/image1.json --> AI Triage --> report & PoC

Run INtrack

python3 main.py -host 192.168.1.1 -instance wordpress



⸻

Folder Structure

/agents          - Core AI modules (Recon, Payload, CVE, EXIF)
/scripts         - Safe runners, organizers, groq tools
/user_tools      - User scripts, PoC gen, HTML recon, recon helpers
/output          - Response logs, raw outputs
/reports         - All Markdown reports & recon logs
/recon_logs      - Logs from subdomain/url scans
/triage          - Triaged metadata + AI results
/screenshots     - Screenshots from Groq agent
/pocs            - PoCs generated from payload/EXIF
/config          - settings.json, organizer_config.json
/utils           - Groq API, CVE fetcher, report builder
/web_ui          - (Coming soon) full web dashboard



⸻

Coming Soon
	•	Web UI with agent control, live logs
	•	GroqCluster fully parallel pipeline engine
	•	GroqWatcher: Auto-watcher for all new recon + triage
	•	GroqFixerBot: AI bot that refactors broken scripts and reports issues
	•	BCheck & Dorking AI Bots full integration
	•	Auto-update agent: Pulls from bcheck, medium, CVEs, and fixes everything

⸻

Future Company Vision

This framework will be at the core of an upcoming AI-powered cybersecurity platform tailored for automation-first security teams and bug bounty hackers. Our mission: make security automation smart, modular, and human-enhancing, not just scripted.

You’re watching the foundation of something huge. Built from scratch. Built from hunger.

⸻

Legal Disclaimer

This is a private, personal framework built for ethical testing, research, and education.
Never scan targets you do not own or lack explicit permission to test.

⸻

© 2025 Kdairatchi | xkdai | GroqWarden Project