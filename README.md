# ![](image.png) ReconMind — AI-Powered AtomicHunter v2.0 Agent

## 🧠 What is ReconMind?
ReconMind is an AI-powered AtomicHunter v2.0 agent that thinks and hunts like a **penetration tester**. Instead of just running tools, it uses an LLM brain (Claude / Llama / Groq) to make decisions at every step — selecting targets, chaining findings, filtering false positives, and generating platform-ready reports.


COMPLETE TOOL STRUCTURE

AtomicHunter/
├── atomichunter.py          # Main entry point
├── requirements.txt         # Dependencies
├── core/
│   ├── config.py           # Configuration (multi-AI support)
│   ├── engine.py           # Main engine (100+ modules)
│   ├── findings.py         # Finding management
│   ├── reporter.py         # Report generator (HTML/JSON/CSV/PDF)
│   ├── ai_analyzer.py      # Universal AI (OpenAI/Claude/Gemini/Kimi/Custom)
│   ├── utils.py            # Logger, Colourizer, FileManager
│   ├── cli.py              # Command line parser
│   ├── banner.py           # ASCII banners
│   └── __init__.py
├── modules/
│   ├── recon.py            # Modules 1-20 (Subdomain, DNS, Port, etc.)
│   ├── web.py              # Modules 21-60 (XSS, SQLi, SSRF, etc.)
│   ├── api.py              # Modules 61-80 (API security)
│   ├── cloud.py            # Modules 81-92 (AWS, Azure, GCP)
│   └── network.py          # Modules 93-113 (SSL, Headers, Services)
├── reports/                # Output directory
└── wordlists/              # Wordlists

🚀 STEP-BY-STEP USAGE GUIDE

Step 1: Install Dependencies
kali
sudo apt update
sudo apt install python3-pip python3-dev
cd AtomicHunter
pip3 install -r requirements.txt

Windows:
# Install Python 3.8+ from python.org
# Open Command Prompt as Administrator
cd AtomicHunter
pip install -r requirements.txt

macOS:
# Install Homebrew first: /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install python3
cd AtomicHunter
pip3 install -r requirements.txt

Step 2: Basic Scan (Auto-discovers bugs)
python atomichunter.py -d target.com --modules all

# What it does:

    Enumerates subdomains
    Scans ports
    Probes alive URLs
    Detects technologies
    Runs all 100+ modules
    Generates HTML report

# Step 3: Full Scan with ALL 100+ Modules
python atomichunter.py -d target.com --modules all

# Step 4: Scan with AI Analysis (ANY AI Provider)
OpenAI (GPT-4):
python atomichunter.py -d target.com --ai-provider openai --ai-key sk-xxxxxxxx

# Anthropic (Claude):
python atomichunter.py -d target.com --ai-provider anthropic --ai-key sk-ant-xxxxxxxx

# Google Gemini:
python atomichunter.py -d target.com --ai-provider gemini --ai-key AIzaSyxxxxxxxx

# Kimi (Moonshot):
python atomichunter.py -d target.com --ai-provider kimi --ai-key sk-xxxxxxxx

# Custom AI API:
python atomichunter.py -d target.com --ai-provider custom --ai-key YOUR_KEY --ai-url https://api.custom.com/v1/chat --ai-model gpt-4

Step 5: Specific Modules Only
# Web vulnerabilities only
python atomichunter.py -d target.com -m xss,sqli,ssrf,lfi

# API security only
python atomichunter.py -d target.com -m api_discovery,api_authentication,api_bola

# Cloud security only
python atomichunter.py -d target.com -m s3_finder,azure_blob,gcp_bucket

# Network only
python atomichunter.py -d target.com -mssl_scanner,header_security,cookie_security

Step 6: High Performance Scan
python atomichunter.py -d target.com --threads 100 --timeout 20 --rate-limit 0.01

Step 7: Custom Output & Reports
# HTML report (default)
python atomichunter.py -d target.com -o /path/to/output -f html

# JSON report
python atomichunter.py -d target.com -f json

# CSV report
python atomichunter.py -d target.com -f csv

# All formats
python atomichunter.py -d target.com -f all

Step 8: Authenticated Scan
# Bearer token
python atomichunter.py -d target.com --auth-token "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9..." --auth-type bearer

# Basic auth
python atomichunter.py -d target.com --auth-token "dXNlcjpwYXNzd29yZA==" --auth-type basic

# With cookies
python atomichunter.py -d target.com --cookies "session=abc123;token=xyz789"

Step 9: With Proxy (Burp Suite, etc.)

python atomichunter.py -d target.com --proxy http://127.0.0.1:8080

📊 REPORT OUTPUT
Reports are saved in reports/ directory:

| Format      | File                     | Description                       |
| ----------- | ------------------------ | --------------------------------- |
| HTML        | `report_target.com.html` | Beautiful dashboard with charts   |
| JSON        | `report_target.com.json` | Machine-readable findings         |
| CSV         | `report_target.com.csv`  | Spreadsheet format                |
| AI Analysis | `ai_analysis.md`         | AI-powered vulnerability analysis |

🎯 100+ MODULES LIST

| #   | Module                        | Category | Severity |
| --- | ----------------------------- | -------- | -------- |
| 1   | Subdomain Enumeration         | Recon    | Info     |
| 2   | DNS Resolution                | Recon    | Info     |
| 3   | Port Scanner                  | Recon    | Info     |
| 4   | HTTP Probe                    | Recon    | Info     |
| 5   | Screenshot Taker              | Recon    | Info     |
| 6   | Technology Fingerprint        | Recon    | Info     |
| 7   | WHOIS Lookup                  | Recon    | Info     |
| 8   | ASN Lookup                    | Recon    | Info     |
| 9   | Certificate Transparency      | Recon    | Info     |
| 10  | Subdomain Permutation         | Recon    | Info     |
| 11  | DNS Zone Transfer             | Recon    | Critical |
| 12  | Reverse DNS                   | Recon    | Info     |
| 13  | IP Range Discovery            | Recon    | Info     |
| 14  | CDN Detector                  | Recon    | Info     |
| 15  | WAF Detector                  | Recon    | Info     |
| 16  | Favicon Hash                  | Recon    | Info     |
| 17  | Email Harvester               | Recon    | Info     |
| 18  | Social Media Scanner          | Recon    | Info     |
| 19  | Pastebin Scanner              | Recon    | Info     |
| 20  | GitHub Dorking                | Recon    | Info     |
| 21  | XSS Scanner                   | Web      | High     |
| 22  | SQL Injection                 | Web      | Critical |
| 23  | SSRF Detector                 | Web      | High     |
| 24  | Open Redirect                 | Web      | Medium   |
| 25  | CRLF Injection                | Web      | High     |
| 26  | CORS Scanner                  | Web      | High     |
| 27  | JWT Scanner                   | Web      | Critical |
| 28  | LFI/RFI Scanner               | Web      | Critical |
| 29  | Command Injection             | Web      | Critical |
| 30  | XXE Scanner                   | Web      | Critical |
| 31  | SSI Scanner                   | Web      | High     |
| 32  | Path Traversal                | Web      | High     |
| 33  | File Upload Scanner           | Web      | Medium   |
| 34  | IDOR Scanner                  | Web      | High     |
| 35  | Business Logic                | Web      | Medium   |
| 36  | CSRF Scanner                  | Web      | Medium   |
| 37  | Clickjacking                  | Web      | Medium   |
| 38  | Host Header Injection         | Web      | High     |
| 39  | HTTP Request Smuggling        | Web      | High     |
| 40  | Cache Poisoning               | Web      | High     |
| 41  | Web Cache Deception           | Web      | Medium   |
| 42  | Race Condition                | Web      | Medium   |
| 43  | Mass Assignment               | Web      | High     |
| 44  | GraphQL Scanner               | Web      | Medium   |
| 45  | SOAP Scanner                  | Web      | Info     |
| 46  | WebSocket Scanner             | Web      | Info     |
| 47  | JSONP Scanner                 | Web      | Medium   |
| 48  | Prototype Pollution           | Web      | High     |
| 49  | DOM Clobbering                | Web      | Medium   |
| 50  | Template Injection            | Web      | Critical |
| 51  | Expression Language Injection | Web      | Critical |
| 52  | Deserialization Scanner       | Web      | High     |
| 53  | HTTP Parameter Pollution      | Web      | Medium   |
| 54  | Unicode Normalization         | Web      | Low      |
| 55  | Homograph Attack              | Web      | Low      |
| 56  | Tabnabbing                    | Web      | Low      |
| 57  | Reverse Tabnabbing            | Web      | Low      |
| 58  | Browser Cache Leak            | Web      | Low      |
| 59  | HXXP Scanner                  | Web      | Info     |
| 60  | Directory Bruteforce          | Web      | Info     |
| 61  | API Discovery                 | API      | Info     |
| 62  | API Versioning                | API      | Info     |
| 63  | API Authentication            | API      | High     |
| 64  | API Rate Limit                | API      | Medium   |
| 65  | API Parameter Tampering       | API      | Medium   |
| 66  | API Injection                 | API      | Critical |
| 67  | API Mass Assignment           | API      | High     |
| 68  | API BOLA                      | API      | High     |
| 69  | API BFLA                      | API      | Critical |
| 70  | API Excessive Data            | API      | High     |
| 71  | API Unsafe HTTP               | API      | Medium   |
| 72  | API Lack Resources            | API      | Medium   |
| 73  | API Improper Assets           | API      | Medium   |
| 74  | API Insuff Logging            | API      | Info     |
| 75  | API Broken Auth               | API      | Critical |
| 76  | API Excessive Data 2          | API      | High     |
| 77  | API Injection 2               | API      | Critical |
| 78  | API Injection 3               | API      | High     |
| 79  | API Mass Assignment 2         | API      | High     |
| 80  | API Security Scanner          | API      | Info     |
| 81  | S3 Bucket Finder              | Cloud    | Critical |
| 82  | Azure Blob Finder             | Cloud    | High     |
| 83  | GCP Bucket Finder             | Cloud    | High     |
| 84  | Cloud Metadata                | Cloud    | Critical |
| 85  | IAM Policy Scanner            | Cloud    | Info     |
| 86  | Cloud Function Scanner        | Cloud    | Info     |
| 87  | Container Registry            | Cloud    | Info     |
| 88  | Kubernetes Scanner            | Cloud    | Critical |
| 89  | Docker Scanner                | Cloud    | Critical |
| 90  | Terraform Scanner             | Cloud    | Critical |
| 91  | CloudFormation Scanner        | Cloud    | Info     |
| 92  | Serverless Scanner            | Cloud    | Info     |
| 93  | SSL Scanner                   | Network  | High     |
| 94  | Header Security               | Network  | Medium   |
| 95  | Cookie Security               | Network  | Medium   |
| 96  | HSTS Scanner                  | Network  | Medium   |
| 97  | Security Headers              | Network  | Medium   |
| 98  | CSP Scanner                   | Network  | Medium   |
| 99  | X-Frame-Options               | Network  | Low      |
| 100 | X-XSS-Protection              | Network  | Low      |
| 101 | Referrer Policy               | Network  | Low      |
| 102 | Permissions Policy            | Network  | Info     |
| 103 | DNSSEC Scanner                | Network  | Info     |
| 104 | SPF Scanner                   | Network  | Low      |
| 105 | DKIM Scanner                  | Network  | Low      |
| 106 | DMARC Scanner                 | Network  | Low      |
| 107 | SMTP Scanner                  | Network  | Info     |
| 108 | SSH Scanner                   | Network  | Info     |
| 109 | Redis Scanner                 | Network  | Critical |
| 110 | Mongo Scanner                 | Network  | Critical |
| 111 | Elastic Scanner               | Network  | Critical |
| 112 | Jenkins Scanner               | Network  | High     |
| 113 | GitLab Scanner                | Network  | Info     |

⚡ QUICK START COMMANDS
# Clone and setup
git clone <repo-url> AtomicHunter
cd AtomicHunter
pip install -r requirements.txt

# Basic scan
python atomichunter.py -d example.com

# Full scan with AI
python atomichunter.py -d example.com --ai-provider openai --ai-key YOUR_KEY

# Fast scan
python atomichunter.py -d example.com --threads 100

# Specific modules
python atomichunter.py -d example.com -m xss,sqli,ssrf

# With proxy
python atomichunter.py -d example.com --proxy http://127.0.0.1:8080

# Authenticated
python atomichunter.py -d example.com --auth-token "Bearer xxx"

🖥️ PLATFORM SUPPORT
Table
| Platform      | Status | Command                   |
| ------------- | ------ | ------------------------- |
| Kali Linux    | ✅ Full | `python3 atomichunter.py` |
| Ubuntu/Debian | ✅ Full | `python3 atomichunter.py` |
| Windows 10/11 | ✅ Full | `python atomichunter.py`  |
| macOS         | ✅ Full | `python3 atomichunter.py` |
| Docker        | ✅ Full | `docker run atomichunter` |


