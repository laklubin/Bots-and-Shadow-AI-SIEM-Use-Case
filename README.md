# Bots & Shadow AI — SIEM Detection Use Cases

63 SIEM detection use cases covering automated (bot) threats and ungoverned AI usage, each with its **log sources**, a **detection expression**, and a **sample log**.

- **Banking Bot Login (22)** — bots logging in to banking applications: credential stuffing, headless browsers, residential proxy rotation, datacenter ASN traffic, JA3/JA4 mismatch, mobile API abuse without app attestation, OTP brute force, emulator farms, session replay, impossible travel, and the account takeover fraud chain through to beneficiary addition and cash-out
- **OWASP Automated Threats (21)** — the complete OAT taxonomy, OAT-001 Carding through OAT-021 Denial of Inventory
- **Shadow AI (20)** — unsanctioned GenAI access, sensitive data and source code leaving for public models, shadow browser extensions, unregistered MCP servers, agentic over-reach, AI in CI/CD, leaked model API keys, and departed-employee access to self-registered AI tenants

## Files

- `index.html` — the published, filterable use case library (GitHub Pages)
- `usecases.json` — the structured dataset behind it

Live site: https://laklubin.github.io/Bots-and-Shadow-AI-SIEM-Use-Case/

## Data model

Each use case in `usecases.json`:

| Field | Description |
|---|---|
| `id` | Stable identifier (`BANK-BOT-001`, `OAT-008`, `SAI-014`) |
| `name` | **Use case name** |
| `domain` | Banking Bot Login / OWASP Automated Threats / Shadow AI |
| `category` | Threat category (Credential Stuffing, Data Exfiltration, ...) |
| `severity` | Critical / High / Medium / Low |
| `oat` | Related OWASP Automated Threat event, where one applies |
| `description` | What the adversary is doing and why it matters |
| `log_sources` | **Log sources** that carry the evidence |
| `detection` | Pseudo-query detection logic |
| `sample_log` | **Sample log** in the shape the source product emits |

## Caveats

**Sample logs are synthetic and illustrative.** Field names follow the shape of real products (F5 Advanced WAF, Akamai Bot Manager, Cloudflare, Okta, Entra ID sign-in logs, Netskope, Zscaler, Palo Alto, CrowdStrike Falcon, Defender for Endpoint, Apigee, GitHub secret scanning) but all IPs, customer IDs, hostnames and domains are fabricated or reserved for documentation use.

**Detection expressions are starting points, not tuned rules.** Every threshold here must be baselined against your own traffic before deployment — the right number for a retail bank's login endpoint is not the right number for anyone else's.

Sources: [OWASP Automated Threats to Web Applications](https://owasp.org/www-project-automated-threats-to-web-applications/), [OWASP GenAI Security Project](https://genai.owasp.org)

Maintained by LK for detection engineering and AI assurance reference.
