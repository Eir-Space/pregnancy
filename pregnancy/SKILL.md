---
name: pregnancy
description: Manage pregnancy-specific health context and tracking using a focused `pregnancy.md` file plus synchronized updates to `health.md`. Use when a user is pregnant, may be pregnant, is discussing prenatal care, pregnancy symptoms, trimester-specific questions, pregnancy-safe guidance considerations, or when an agent needs to record pregnancy-related follow-up questions and milestones while keeping the master health record updated.
---

# Pregnancy

## Overview

Use this skill for pregnancy as a specific health event/context. Maintain detailed pregnancy information in `pregnancy.md`, while keeping `health.md` updated with pregnancy status, skill attachment, linked file entry, and any open follow-up questions.

## Core Workflow

Follow these steps in order unless the user requests a narrower action.

### 1. Confirm Scope and Safety

- Identify whether the user is:
  - pregnant (confirmed)
  - possibly pregnant (unconfirmed)
  - asking a general pregnancy question without personal status
- If the status is uncertain, coordinate with `health` skill behavior:
  - store in `Unconfirmed Findings` in `health.md`
  - ask a short confirmation question before treating pregnancy as confirmed
- If urgent symptoms are mentioned, prioritize urgent care / emergency guidance instead of routine tracking.

### 2. Update `health.md` (Master Record)

- Ensure `Pregnancy` appears in `## Active Health Contexts` when confirmed and active.
- Ensure `pregnancy` appears in `## Skill Attachments` (`Suggested` or `Active`).
- Ensure `pregnancy.md` appears in `## Linked Health Files` once created.
- Add or update pregnancy-related entries in `## Information Gaps & Follow-up Questions`.
- Add provenance and confidence for agent-added facts.

### 3. Create or Update `pregnancy.md` (Focused Record)

- Create `pregnancy.md` if it does not exist and pregnancy is confirmed (or the user explicitly wants pregnancy tracking).
- Use `pregnancy.md` for detailed, pregnancy-specific information that would clutter `health.md`.
- Keep the file human-readable and structured with stable headings.

### 4. Ask High-Value Pregnancy Follow-up Questions

- Ask only what materially affects guidance or safety.
- Prioritize:
  - gestational age / weeks pregnant
  - due date (or estimated due date)
  - urgent symptoms (bleeding, severe pain, severe headache, decreased fetal movement when applicable)
  - current prenatal care / clinician contact
  - current medications and supplements
- Store unanswered questions back in `health.md`.

### 5. Keep Advice Context-Aware and Conservative

- Frame answers with pregnancy context in mind.
- Avoid certainty when key details are missing.
- Encourage clinician follow-up for medication safety decisions and urgent symptoms.

## `pregnancy.md` Structure (Recommended)

Use these sections when relevant. Skip sections that do not apply.

```markdown
# Pregnancy Record

## Pregnancy Status
- **Status:** Confirmed / Suspected / Postpartum
- **Source:** user_reported / clinician_verified / journal_inferred
- **Confidence:** High / Medium / Low
- **Last Confirmed:** YYYY-MM-DD

## Key Dates
- **Estimated Due Date (EDD):** YYYY-MM-DD (if known)
- **Gestational Age:** 12 weeks + 3 days (if known)
- **Last Menstrual Period (LMP):** YYYY-MM-DD (optional)

## Pregnancy History (Optional)
- **Gravida/Para:** GxPy (if known and user is comfortable sharing)
- **Previous Pregnancies:** Brief summary
- **Relevant Prior Complications:** e.g. gestational diabetes, preeclampsia

## Current Symptoms / Concerns
- **Symptoms:** nausea, fatigue, etc.
- **Questions:** user concerns for next visit or current discussion
- **Red Flags Reported:** none / list

## Medications and Supplements (Pregnancy-Relevant)
- **Prenatal Vitamin:** yes/no/details
- **Other Medications:** list and note prescriber
- **Medication Questions for Clinician:** list

## Prenatal Care
- **Primary Pregnancy Care Team:** OB/GYN / Midwife / Clinic
- **Next Appointment:** YYYY-MM-DD (if known)
- **Tests / Screening Planned:** optional

## Follow-up Questions
- Open questions specific to pregnancy context that still need answers

## Notes
- Free-text notes and clarifications
```

## Sync Rules with `health.md`

- `health.md` remains the master health record and index.
- `pregnancy.md` is the detailed companion file.
- When updating `pregnancy.md`, also check whether `health.md` needs updates in:
  - `Active Health Contexts`
  - `Skill Attachments`
  - `Linked Health Files`
  - `Information Gaps & Follow-up Questions`
- Keep summaries short in `health.md` and details in `pregnancy.md`.

## Safety Boundaries

- Do not treat routine tracking as a substitute for prenatal care.
- Escalate urgent symptoms using urgent/emergency care guidance.
- Do not provide definitive medication safety decisions without appropriate clinical confirmation.
- State limitations clearly when gestational age or symptoms are unclear.

## References

- Read `references/pregnancy-record-pattern.md` for a canonical `pregnancy.md` template and `health.md` sync checklist.
