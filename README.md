

⸻

# GroqWarden x INtrack

The Ultimate AI-Powered Bug Bounty, Recon & Security Automation Framework
Created by xkdai — from script kiddie to elite, one scan at a time.

 

 


⸻

# What Is This?

This is the fusion of GroqWarden and INtrack — an intelligent, auto-healing, AI-enhanced recon and scanning system that:
	•	Performs deep reconnaissance, payload fuzzing, PoC building, and EXIF analysis
	•	Uses Groq AI for triage, banner generation, file classification, decision-making, and agent assistance
	•	Integrates parallel scanning, modular agents, and auto-organized output
	•	Includes the INtrack engine for network-level, CVE, IoT, and web scanner automation

⸻

# Roadmap

graph TD
    Start[Start: main.py]
    subgraph Core Modules
        A[ReconAgent]
        B[SecretsAgent]
        C[IntelBot]
        D[PayloadAgent]
        E[ScreenshotAgent]
        F[ReportAgent]
        G[ToolRunnerAgent]
        H[PoCAutoBuilder]
        I[EXIFBot]
        J[BCheckBot]
        K[DorkingBot]
    end

    subgraph Groq Intelligence
        L[GroqCluster]
        M[GroqHound]
        N[FixerAgent]
        O[GroqBannerGen]
    end

    subgraph AutoSystems
        P[AutoOrganizer]
        Q[AutoUpdateBot]
        R[LogWatcher]
    end

    Start --> A & B & C --> D --> E --> F --> G
    G --> H & I --> J --> K
    A & G --> L
    L --> M --> N
    M --> P & Q & R



⸻

Folder Structure

groqwarden/
├── agents/             # Modular AI-powered agents
├── user_tools/         # Scripts, recon helpers, utilities
├── utils/              # Groq API, CVE fetchers, Discord notifier, etc.
├── config/             # JSON configs and blacklists
├── output/             # Raw output files from scans
├── triage/             # JSON/metadata PoC triage results
├── recon_logs/         # Full recon logs by timestamp
├── reports/            # Markdown + TXT final reports
├── pocs/               # Stored payload and PoC files
├── screenshots/        # Site screenshots + HTML dump
├── web_ui/             # Optional Gradio dashboard (optional)
├── fullscan.py         # Complete recon + fuzz workflow
├── main.py             # CLI runner and orchestrator
├── setup.py            # CLI setup for installing
├── README.md           # This file



⸻

How to Use

Install

git clone https://github.com/kdairatchi/groqwarden.git
cd groqwarden
pip install -r requirements.txt

Set your Groq API Key in a .env file:

GROQ_API_KEY=your_key_here

Basic Run

python3 main.py

You’ll be prompted for:
	•	Full scan
	•	Report generation
	•	Payload fuzzing
	•	Manual recon
	•	Agent testing
	•	Running your own scripts

⸻

Full Scan Mode

python3 fullscan.py --domain example.com

This includes:
	•	Subdomain enum (subfinder, amass)
	•	URL collection (waybackurls, katana)
	•	Vulnerability detection (nuclei, ffuf, dalfox)
	•	Screenshot capture
	•	PoC auto-generation
	•	Secrets/JS/API key analysis

⸻

Agents

Each core agent can run standalone or through main.py:

Agent	Function
ReconAgent	Subdomain, URL, and parameter recon
SecretsAgent	Detect secrets in JS and static files
IntelBot	Collect passive info from multiple sources
PayloadAgent	Fuzzing with XSS/SSRF/SQLi payloads
ScreenshotAgent	Capture visual snapshots of all targets
ReportAgent	Generate and save structured reports
ToolRunnerAgent	External scanner runner (nmap, zap, burp, etc.)
PoCAutoBuilder	Auto-build HTML/JS PoCs from payload data
GroqHoundAgent	AI triage and clustering of vulnerabilities
BCheckBot	Analyze bchecks and perform behavioral checks from data/bchecks/
DorkingBot	Generate + test dorks, analyze findings with Groq AI
FixerAgent	Fixes errors, missing modules, broken logic
AutoOrganizer	Organize all output automatically using Groq + user logic
AutoUpdateBot	Updates agents, scripts, config files, and regenerates intelligence



⸻

How Is It Smart?
	•	GroqCluster distributes tasks for concurrent LLM triage
	•	All safe_run() wrapped — tool never crashes, FixerAgent heals it
	•	Auto-banner generation with signature xkdai
	•	Organized outputs that evolve and refactor with every run
	•	Metadata-aware (e.g., EXIF triage, secrets analyzer, CVE PoC builders)

⸻

Coming Soon
	•	Web UI for monitoring and controlling agents
	•	GroqShell – ask natural language and have it spawn tools
	•	Webhook C2 via Discord + command execution via bot
	•	INtrack deep integration with automatic port+service-based agent launching
	•	Frogy Scoring System – risk level assigned to each recon result
	•	Dashboard Heatmap
	•	Log Replayer – AI bot learns from logs and re-runs smarter next time

⸻

Contributions

All tools are designed to learn with the user.
You don’t have to be an expert — this is built for beginner bug bounty hunters looking to:
	•	Automate their recon
	•	Understand payload behavior
	•	Learn from Groq’s suggestions
	•	Build their own toolkit with swagger

⸻

License

MIT — use it, break it, fork it, grow with it.

⸻