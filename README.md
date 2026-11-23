# Recruiter GDPR Erasure

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent_Skills-Compatible-6f42c1)](https://agentskills.io)

An [Agent Skill](https://agentskills.io) for handling unsolicited recruiter outreach—cold emails, LinkedIn InMails, and speculative headhunter messages—under **UK GDPR** and the **Data Protection Act 2018**.

Paste any unwanted recruiter message into your AI coding/productivity agent (Claude Code, Gemini CLI, Codex CLI, Cursor, Antigravity, etc.), and this skill will extract the sender's details, draft a formal statutory erasure & direct-marketing objection notice, and log the case to a **Google Sheets tracker** so you can monitor the 1-month statutory compliance window for potential **Information Commissioner's Office (ICO)** escalation.

---

## Features & Workflow

When triggered by an unsolicited recruiter message, the skill follows a 3-step workflow:

1. **Extract Outreach Details**
   Automatically parses the date received, recruiter name, recruitment agency/company, pitched role, and recruiter contact email or profile URL.

2. **Draft a Formal UK GDPR Statutory Notice**
   Generates a concise, strictly formal, ready-to-send response asserting:
   - **Article 21(2) UK GDPR (Right to Object to Direct Marketing):** Exercises the *absolute* right to object to direct marketing—controllers cannot claim "legitimate interest" to override this and must cease marketing processing immediately.
   - **Article 17 UK GDPR (Right to Erasure / "Right to be Forgotten"):** Demands permanent deletion of personal data across all internal databases, ATS/CRM platforms (e.g., Bullhorn, Greenhouse), and candidate talent pools, while prohibiting third-party onward sharing.
   - **Statutory Confirmation & ICO Escalation:** Requires written confirmation within the statutory **one-month** timeframe and puts the agency on notice of referral to the **ICO** in the event of non-compliance or continued contact.

3. **Maintain a Compliance Tracker in Google Sheets**
   Creates or appends to a `Recruiter GDPR Erasure Tracker` spreadsheet to audit responses and follow up on overdue requests:

   | Column | Description |
   | :--- | :--- |
   | **Date Notified** | `YYYY-MM-DD` date the formal notice was sent |
   | **Agency / Company** | Name of the recruitment firm |
   | **Recruiter Name** | Name of the sender |
   | **Contact Email / URL** | Recruiter's email address or LinkedIn profile URL |
   | **Subject / Pitch** | Role or client pitched (e.g., SWE, Quant Dev) |
   | **1-Month Deadline** | Statutory response deadline (`Date Notified` + 30 days) |
   | **Status** | `Notice Sent` / `Confirmed Deleted` / `Non-Compliant / Follow-up` |
   | **Notes / Legal Escalation** | Follow-up history, repeated contact evidence, or ICO case reference |

---

## Scope & Applicability

- **Jurisdiction:** Designed for **UK GDPR** and the **UK Data Protection Act 2018**, which apply to recruitment agencies established in the UK or processing personal data of individuals located in the UK.
- **No Negotiation Tone:** Keeps responses strictly formal and statutory—avoiding casual replies or ambiguity that agencies might treat as ongoing engagement.

---

## Installation

### Option 1: Install via `skills` CLI (Recommended)

Works across Claude Code, Gemini CLI, Codex CLI, Cursor, and other Agent Skills–compatible tools:

```bash
npx skills add xuyangkang/recruiter-gdpr-erasure
```

### Option 2: Manual Installation

Clone this repository and copy `skills/recruiter-gdpr-erasure` into your agent's skills directory:

| Tool | User-Level Skills Directory | Project-Level Directory |
| :--- | :--- | :--- |
| **Claude Code** | `~/.claude/skills/` | `.claude/skills/` |
| **Gemini CLI / Antigravity** | `~/.gemini/skills/` | `.gemini/skills/` |
| **Codex CLI** | `~/.codex/skills/` | `.codex/skills/` |

**macOS / Linux:**

```bash
git clone https://github.com/xuyangkang/recruiter-gdpr-erasure.git
mkdir -p ~/.claude/skills
cp -r recruiter-gdpr-erasure/skills/recruiter-gdpr-erasure ~/.claude/skills/
```

**Windows (PowerShell):**

```powershell
git clone https://github.com/xuyangkang/recruiter-gdpr-erasure.git
New-Item -ItemType Directory -Force -Path "$HOME\.claude\skills" | Out-Null
Copy-Item -Recurse "recruiter-gdpr-erasure\skills\recruiter-gdpr-erasure" "$HOME\.claude\skills\"
```

---

## Usage & Customization

### Quick Start

Paste an unsolicited recruiter email or LinkedIn message into your agent:

```text
Got another cold recruiter email—draft a UK GDPR erasure notice and log it:

From: Jane Doe <jane@example-recruiting.co.uk>
Subject: Senior Quant Developer role - London (£250k+)
Hi, I came across your profile and wanted to reach out about an exciting HFT role...
```

### Optional Setup

- **Pre-fill Your Signature:** Replace `[Your Name]` in [`skills/recruiter-gdpr-erasure/SKILL.md`](./skills/recruiter-gdpr-erasure/SKILL.md) with your full name so generated notices require zero manual editing.
- **Google Sheets Integration:** Connect a Google Workspace / Google Sheets MCP server or CLI tool to your agent if you want step 3 (creating and appending rows in `Recruiter GDPR Erasure Tracker`) to run automatically. Without an active Sheets integration, the agent will output the formatted row ready to paste.

---

## Repository Structure

```text
recruiter-gdpr-erasure/
├── README.md
├── LICENSE
└── skills/
    └── recruiter-gdpr-erasure/
        └── SKILL.md
```

---

## Disclaimer

This project provides standardized correspondence templates and personal tracking workflows for exercising statutory data protection rights under UK GDPR. It is provided for informational and productivity purposes only and **does not constitute legal advice**. If you require formal legal representation or advice regarding data protection violations, consult a qualified legal professional or refer to official guidance from the [Information Commissioner's Office (ICO)](https://ico.org.uk/).

## License

Released under the [MIT License](./LICENSE).
