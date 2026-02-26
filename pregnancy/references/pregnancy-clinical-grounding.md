# Pregnancy Clinical Grounding (High-Level, Evidence-Oriented)

Use this reference to ground an agent's pregnancy-related responses with the most important clinical focus areas, safety priorities, and follow-up questions.

## Scope

- This reference is **not reviewed by a medical professional**.
- This is a high-level grounding reference for agents, not a clinical protocol.
- Use it to improve relevance and safety when answering health questions for a pregnant person.
- Do not use it to replace emergency care, prenatal care, or clinician-specific recommendations.
- Region-specific recommendations vary; ask the user's country/region when guidance depends on local practice.

## What Pregnancy Changes for the Agent

Pregnancy is an active health context that should change how the agent frames general health advice because it can affect:
- medication safety considerations
- evaluation of symptoms and urgency
- nutrition/supplement counseling
- preventive care priorities (vaccination, prenatal care, screening)
- management of pre-existing conditions (for example diabetes, hypertension)

## Highest-Priority Focus Areas

When interacting with a pregnant user, prioritize these areas first.

### 1. Immediate Safety / Urgent Warning Signs

Screen for urgent symptoms early when the user reports new or severe symptoms. If present, prioritize urgent or emergency care guidance instead of routine tracking.

Examples of high-concern symptoms include:
- trouble breathing
- chest pain
- severe abdominal pain
- heavy bleeding
- severe headache (especially if persistent or concerning)
- fainting / severe dizziness
- severe swelling or vision changes (context-dependent concern)
- seizures

Also ask about gestational age and whether the user has contacted a pregnancy clinician, because urgency thresholds and likely causes vary by stage and history.

### 2. Pregnancy Status and Timing

The most important contextual variables for pregnancy guidance are:
- whether pregnancy is confirmed vs suspected
- gestational age / weeks pregnant
- estimated due date (EDD)
- postpartum status (if recently delivered)

Many questions cannot be answered safely or accurately without timing context.

### 3. Prenatal Care Linkage

Check whether the user has:
- an OB/GYN, midwife, or prenatal clinic
- upcoming prenatal visits
- access barriers (cost, transport, scheduling, language)

If they are not connected to prenatal care, prioritize helping them organize that next step.

### 4. Medication and Supplement Review

Pregnancy should trigger medication caution review. Ask about:
- prescription medications
- OTC medications
- supplements/herbals
- prenatal vitamins

Folate/folic acid intake is a high-value topic to check early. Use current public-health guidance as a baseline and defer to clinician-specific recommendations when higher-risk situations apply (for example prior neural tube defect history or other conditions that may require different dosing).

Do not provide definitive medication safety decisions when uncertain. Encourage clinician/pharmacist review, especially before starting/stopping medications.

### 5. Chronic Conditions and Prior Pregnancy Risks

Pregnancy-related guidance changes significantly when the user has:
- diabetes (including prior gestational diabetes)
- hypertension
- thyroid disease
- asthma
- seizure disorders
- mental health conditions
- prior pregnancy complications (for example preeclampsia, preterm birth)

Capture these in `health.md` and `pregnancy.md` because they affect follow-up priorities.

### 6. Vaccination and Preventive Care Context

Pregnancy care often includes vaccine discussions and preventive counseling. Do not assume status; ask what has been received and what a clinician has recommended.

### 7. Mental Health and Social Support

Pregnancy care is not only physical. Ask briefly about:
- mood/anxiety concerns
- sleep
- support system
- safety concerns (if appropriate and context allows)

Use a supportive tone and escalate urgent safety concerns appropriately.

## High-Value Follow-up Questions (Ask Sparingly)

Ask only what materially improves safety or guidance. Start with 1-3 questions.

Core questions:
1. How many weeks pregnant are you (or what is your estimated due date)?
2. What symptoms are you having right now, and are any severe or getting worse?
3. Have you had a prenatal visit yet / do you have an OB-GYN or midwife?
4. What medications and supplements are you taking (including OTC and herbal)?

Ask more only if necessary for the user's immediate question.

## What to Store in `pregnancy.md` (Most Useful Fields)

Prioritize storing:
- confirmation status + source + confidence
- gestational age / EDD (if known)
- current symptoms and red flags reported
- medications/supplements
- prenatal care team and next appointment
- follow-up questions still unanswered

Keep `health.md` as the master index and summary; keep details in `pregnancy.md`.

## Updating `health.md` in Parallel

When pregnancy is confirmed or strongly suspected:
- `Active Health Contexts`: add/update `Pregnancy` (confirmed)
- `Unconfirmed Findings`: use for suspected pregnancy until confirmed
- `Skill Attachments`: ensure `pregnancy` is suggested/active
- `Linked Health Files`: add/update `pregnancy.md`
- `Information Gaps & Follow-up Questions`: persist unanswered critical questions

## Safety Boundaries for Agents

- Do not diagnose pregnancy complications.
- Do not over-reassure when urgent symptoms are present.
- Do not give definitive medication safety advice without appropriate sources/clinical confirmation.
- State uncertainty and recommend appropriate escalation when details are incomplete.

## Source Maintenance

This reference should be reviewed regularly and clinician-checked before major releases.

### Review Status

- Not reviewed by a medical professional (as of 2026-02-26)

### Last Reviewed

- 2026-02-26

### Source Priorities

Use primary, authoritative sources first:
- national professional societies (for example ACOG)
- public health agencies (for example CDC)
- WHO / national guideline bodies
- government health information portals

### Sources (reviewed for this file)

- CDC Hear Her campaign: warning signs during and after pregnancy (`Pregnancy and Postpartum Warning Signs`)
- CDC: vaccination guidance before, during, and after pregnancy
- CDC: folic acid guidance (birth defects prevention)
- HHS Office on Women's Health: prenatal care and prenatal testing overview
- WHO: healthy pregnancy / maternal health guidance
- ACOG patient guidance pages (prenatal care, routine tests, and warning signs) for cross-checking phrasing and priorities

Add URLs and refresh dates whenever this file is updated.

## Source URLs (Current Set)

- https://www.cdc.gov/hearher/pregnancy-postpartum-warning-signs/index.html
- https://www.cdc.gov/vaccines-pregnancy/about/vaccines.html
- https://www.cdc.gov/folic-acid/about/index.html
- https://womenshealth.gov/pregnancy/youre-pregnant-now-what/prenatal-care-and-tests
- https://www.who.int/health-topics/maternal-health
- https://www.acog.org/womens-health/faqs/routine-tests-during-pregnancy
- https://www.acog.org/womens-health/faqs/pregnancy-faq027-prenatal-care
- https://www.acog.org/womens-health/faqs/pregnancy-faq169-warning-signs-of-problem-pregnancy
