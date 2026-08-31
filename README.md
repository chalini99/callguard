
CallGuard

## AI Scam-Call Counter-Intelligence Agent

> Don't just identify suspicious calls. Investigate them.

CallGuard is a defensive AI security application that uses CALL-E to investigate potentially suspicious phone communications through real phone conversations.

Instead of relying only on phone-number reputation, CallGuard conducts a structured investigation, analyzes conversational evidence, identifies scam indicators, calculates a risk score, and generates a reusable scam signature.

---

## 🚨 The Problem

Scam calls are becoming increasingly convincing.

Common examples include:

- Fake bank and KYC calls
- OTP and verification scams
- Fake job and internship offers
- Fake course and training offers
- Payment and investment scams
- Government or company impersonation
- Remote-access scams

Traditional caller-ID systems mainly answer:

> "Is this number suspicious?"

CallGuard asks a different question:

> "What is this caller actually trying to do?"

---

## 💡 How CallGuard Works

```text
Suspicious phone number
        ↓
   CALL-E investigation
        ↓
 Real phone conversation
        ↓
 Conversation transcript
        ↓
   Scam Analyzer
        ↓
 Risk score + red flags
        ↓
 Reusable scam signature
        ↓
   Scam Intelligence
📞 CALL-E Integration

CallGuard uses CALL-E to conduct an authorized outbound investigation call.

During the investigation, the AI:

Identifies itself as an AI security investigator.
Asks what organization or service the caller represents.
Asks why the caller contacted the recipient.
Determines what action the caller wants.
Detects requests involving sensitive information, payments, or remote access.
Asks how the caller can be independently verified.
Ends the conversation after sufficient evidence is collected.

CALL-E is invoked at runtime through its CLI/MCP integration.

🧠 Scam Analysis

CallGuard analyzes conversational evidence rather than relying only on the phone number.

The analyzer can detect indicators such as:

Financial context
KYC claims
OTP requests
Credential requests
Urgency
Threats
Payment requests
Remote-access requests

The detected indicators are combined into a reusable scam signature.

Example
FINANCIAL_CONTEXT + KYC + OTP_REQUEST + URGENCY

Example result:

Risk Level: HIGH
Risk Score: 70/100
Confidence: 90%

Likely scam type:

Potential Fake KYC / Bank Impersonation
🧬 Scam Intelligence

CallGuard stores reusable behavioral scam signatures locally.

If multiple investigations produce the same signature, the system tracks its occurrence count and latest investigation summary.

Example:

HIGH
Potential Fake KYC / Bank Impersonation

FINANCIAL_CONTEXT + KYC + OTP_REQUEST + URGENCY

Seen 2 times

This allows CallGuard to move beyond one-time detection toward reusable conversational scam intelligence.

🛡️ Safety

CallGuard is intended for defensive security research and authorized testing.

The investigation agent:

Identifies itself as an AI assistant.
Does not impersonate real organizations or individuals.
Does not request real OTPs, passwords, PINs, CVVs, or banking credentials.
Does not request payments.
Does not request remote device access.
Uses neutral questions to gather conversational evidence.

Never use CallGuard to obtain, store, or expose real authentication credentials or financial secrets.

CALL-E calls can have real-world effects and should only be made to numbers you are authorized to investigate.

🏗️ Project Structure
callguard/
│
├── public/
│   ├── index.html
│   ├── app.js
│   └── style.css
│
├── src/
│   ├── analysis/
│   │   └── scamAnalyzer.js
│   │
│   ├── calle/
│   │   └── calleService.js
│   │
│   ├── database/
│   │   └── scamDatabase.js
│   │
│   └── server.js
│
├── .gitignore
├── package.json
└── package-lock.json
⚙️ Installation
Requirements
Node.js
npm
CALL-E CLI
Authorized CALL-E account
Install dependencies
npm install
Authenticate with CALL-E

Install the CALL-E CLI according to the official CALL-E installation instructions and authenticate your account.

Verify authentication:

calle auth status
Start CallGuard
npm start

The application runs locally on:

http://localhost:3000
🔍 Example Investigation

A controlled investigation can produce evidence such as:

Caller:
"I am calling from your bank's KYC department."

Caller:
"Your KYC has expired and you need to complete verification immediately."

Caller:
"Yes, I need the OTP."

CallGuard can identify:

FINANCIAL_CONTEXT
KYC
OTP_REQUEST
URGENCY

and generate:

FINANCIAL_CONTEXT + KYC + OTP_REQUEST + URGENCY
🌐 API
Health Check
GET /api/health
Scam Intelligence
GET /api/signatures

These endpoints expose the application's health status and stored scam intelligence.

🔮 Future Scope

CallGuard is designed to expand beyond the demonstrated KYC/bank impersonation scenario.

Potential future categories include:

Fake job and internship scams
Fake course and certification scams
Investment scams
Delivery and courier scams
Government impersonation
Technical-support scams
Payment fraud
And others

Future versions could also support larger shared scam-signature datasets and stronger cross-investigation correlation.
```
