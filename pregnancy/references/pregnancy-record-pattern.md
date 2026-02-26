# Pregnancy Record Pattern (`pregnancy.md`)

Use this template when creating or updating a focused pregnancy record.

## Purpose

- Store detailed pregnancy-specific information in `pregnancy.md`
- Keep `health.md` as the master record and index
- Ensure portable behavior across agents using the `pregnancy` skill

## Recommended File Name

- `pregnancy.md`

If multiple pregnancy records are needed:
- `pregnancy-2026.md`
- `pregnancy-postpartum-2026.md`

## Recommended Template

```markdown
# Pregnancy Record

## Pregnancy Status
- **Status:** Confirmed
- **Source:** user_reported
- **Confidence:** High
- **Last Confirmed:** YYYY-MM-DD

## Key Dates
- **Estimated Due Date (EDD):** YYYY-MM-DD (if known)
- **Gestational Age:** [weeks/days] (if known)
- **Last Menstrual Period (LMP):** YYYY-MM-DD (optional)

## Pregnancy History (Optional)
- **Gravida/Para:** GxPy (if known)
- **Prior Pregnancy Complications:** none / list

## Current Symptoms / Concerns
- **Symptoms:** list
- **Questions:** list
- **Red Flags Reported:** none / list

## Medications and Supplements
- **Prenatal Vitamin:** details
- **Medications:** list
- **Questions for Clinician:** list

## Prenatal Care
- **Care Team:** OB/GYN / Midwife / Clinic
- **Next Appointment:** YYYY-MM-DD
- **Tests / Screening Planned:** optional

## Follow-up Questions
- Open items for future conversations

## Notes
- Free-text notes
```

## `health.md` Sync Checklist

When creating or updating `pregnancy.md`, check `health.md` for:

1. `Active Health Contexts`
- Add/update `Pregnancy` when confirmed and active
- Include `Source`, `Confidence`, `Last Confirmed`

2. `Unconfirmed Findings`
- Use this instead when pregnancy is only inferred or uncertain

3. `Skill Attachments`
- Ensure `pregnancy` is present (`Suggested` or `Active`)

4. `Linked Health Files`
- Add/update `pregnancy.md` entry with `Skill: pregnancy`

5. `Information Gaps & Follow-up Questions`
- Persist unanswered high-value questions (gestational age, urgent symptoms, care team, meds/supplements)

## High-Value Follow-up Questions (Ask Sparingly)

- How many weeks pregnant are you (or what is your estimated due date)?
- Have you had a prenatal visit yet?
- Are you having any urgent symptoms (heavy bleeding, severe pain, severe headache, fainting, etc.)?
- What medications and supplements are you currently taking?

Ask only what is needed for safety and useful context.
