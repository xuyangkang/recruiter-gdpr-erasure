---
name: recruiter-gdpr-erasure
description: Handles unsolicited recruiter emails and cold outreach by drafting formal UK GDPR Article 17 / Article 21 erasure and objection notices, and maintains a tracking log in Google Sheets. Use when the user receives recruiter spam, headhunter messages, or wants to exercise their Right to be Forgotten against recruitment agencies.
---

# Recruiter GDPR Erasure & Tracking

Drafts legally binding formal UK GDPR notices to headhunters and recruitment agencies exercising the Right to Erasure and Objection to Direct Marketing, while logging details in a Google Sheets tracker for potential ICO escalations or legal action.

## When to Use

- The user shares an unsolicited recruiter email, LinkedIn InMail, or outreach message.
- The user asks to draft a response demanding personal data deletion under UK GDPR.
- The user wants to track which recruitment agencies have received formal statutory notices.

## Workflow

### 1. Extract Details

From the email or message provided by the user, identify:

- **Date Received**
- **Recruiter Name**
- **Agency / Company Name**
- **Target Role / Pitch** (e.g. HFT SWE, quant dev, etc.)
- **Recruiter Contact / Email**

### 2. Generate the Formal Legal Notice

Provide a ready-to-send formal response asserting:

- **Article 21(2) UK GDPR:** Absolute right to object to direct marketing (mandatory immediate cessation of marketing processing).
- **Article 17 UK GDPR:** Right to erasure ("Right to be Forgotten") across all internal databases, ATS/CRM systems (e.g., Bullhorn, Greenhouse), and candidate pools.
- **Confirmation Demand:** Statutory obligation to confirm erasure in writing within one calendar month.
- **Escalation Warning:** Notice of referral to the Information Commissioner's Office (ICO) in case of non-compliance or continued contact.

#### Standard Response Template

```text
Subject: Formal Notice: Objection to Direct Marketing & Request for Erasure under UK GDPR

Hi [Recruiter's Name],

I am not interested in opportunities from [Agency Name] or any roles you represent, and I am not open to new roles. Please stop sending unsolicited communications.

Regardless of how or where you obtained my personal contact details, your firm operates within the UK and is subject to the Data Protection Act 2018 and UK GDPR.

Please treat this communication as a formal notice exercising my statutory rights:
1. Article 21(2) UK GDPR (Right to Object to Direct Marketing): Cease processing my personal data for direct marketing purposes immediately.
2. Article 17 UK GDPR (Right to Erasure): Permanently erase all personal data relating to me across all your systems, internal databases, ATS/CRM platforms, and talent pools.
3. Third-Party Restrictions: Ensure my details are not stored, forwarded, or shared with any third-party clients or partner networks.

Please confirm in writing within the statutory one-month timeframe once full erasure is completed.

Continued unsolicited contact or failure to comply will be reported directly to the Information Commissioner's Office (ICO).

Best regards,
[Your Name]
```

### 3. Log to Google Sheets Tracker

Maintain a spreadsheet (titled `Recruiter GDPR Erasure Tracker`) with the following schema:

- **Date Notified**: YYYY-MM-DD
- **Agency / Company**: Name of recruitment firm
- **Recruiter Name**: Name of sender
- **Contact Email / URL**: Recruiter email or LinkedIn profile
- **Subject / Pitch**: What role or firm they pitched
- **1-Month Deadline**: Date + 30 days
- **Status**: `Notice Sent` / `Confirmed Deleted` / `Non-Compliant / Follow-up`
- **Notes / Legal Escalation**: Details of repeated contact, ICO report reference, or lawyer notes

If the tracker spreadsheet does not exist yet, create it with these headers. If it exists, append the new row.

## Gotchas

- UK GDPR applies to any agency processing data of UK residents or operating in the UK.
- Direct marketing objection under Art 21(2) is **absolute**; the controller has no legitimate interest override.
- Never acknowledge interest or negotiate; keep tone strictly formal, legal, and concise.
