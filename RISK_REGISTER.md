# Risk Register — AI System Ownership

This document captures known and anticipated risks in a production AI system and how they are managed under an ownership model.

The goal is not zero risk, but **controlled, visible, and mitigated risk**.

---

## Risk Management Principles

- Risks are identified early and reviewed continuously
- Mitigation is preferred over avoidance
- Systems degrade gracefully rather than fail hard
- Ownership includes accountability for outcomes

---

## Risk Register

### R1 — AI Output Invalid or Incomplete
- **Category:** AI / Model Behavior
- **Impact:** Incorrect downstream actions, user-facing errors
- **Likelihood:** Medium
- **Mitigation:**
  - Strict input validation
  - Structured output expectations
  - Post-response validation
  - Deterministic fallback logic
- **Owner:** System Owner

---

### R2 — Prompt Drift Over Time
- **Category:** AI / Prompt Engineering
- **Impact:** Reduced accuracy, unpredictable behavior
- **Likelihood:** Medium
- **Mitigation:**
  - Versioned prompts
  - Controlled prompt updates
  - Monitoring output variance
- **Owner:** System Owner

---

### R3 — OAuth Token Expiry or Refresh Failures
- **Category:** Authentication
- **Impact:** Workflow failures, degraded user experience
- **Likelihood:** Medium
- **Mitigation:**
  - Token lifecycle audits
  - Explicit refresh handling
  - Clear error surfacing
- **Owner:** System Owner

---

### R4 — Third-Party API Rate Limits
- **Category:** Integration
- **Impact:** Partial outages, workflow delays
- **Likelihood:** High
- **Mitigation:**
  - Rate-limit isolation
  - Backoff and retry policies
  - Async execution where applicable
- **Owner:** System Owner

---

### R5 — n8n Workflow Overload
- **Category:** Orchestration
- **Impact:** Timeouts, cascading failures
- **Likelihood:** Medium
- **Mitigation:**
  - Workflow decomposition
  - Async boundaries
  - Reduced synchronous fan-out
- **Owner:** System Owner

---

### R6 — AI Cost Escalation
- **Category:** Cost / Operations
- **Impact:** Unexpected spend
- **Likelihood:** Medium
- **Mitigation:**
  - Token and usage limits
  - Monitoring and alerts
  - Fallbacks for non-critical paths
- **Owner:** System Owner

---

### R7 — Observability Gaps
- **Category:** Operations
- **Impact:** Delayed incident response
- **Likelihood:** Medium
- **Mitigation:**
  - End-to-end tracing
  - Explicit error logging
  - Failure visibility before optimization
- **Owner:** System Owner

---

## Review Cadence

- Risks reviewed during system changes
- New risks added when architecture evolves
- High-impact risks escalated early with mitigation options

---

## Ownership Statement

Risk management is a continuous responsibility.  
I own the identification, communication, and mitigation of risks in the systems I operate.
