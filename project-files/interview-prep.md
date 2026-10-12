# Interview Prep: Full Stack Developer, Healthcare Startup

How to use this: answers are built from facts already on your resume. Lines marked **[YOUR STORY]** need a real example from you. Don't fill those in with made-up details, because interviewers will ask follow-up questions.

---

## 1. Questions about the gaps (expect these first)

**"You don't have React or Node.js on your resume. Why should we consider you?"**
> "My strongest skill is the hardest part of this role to teach: making third-party integrations reliable. Every day I debug REST APIs, OAuth flows and payload mismatches across 12 production connectors. React and Node are learnable, and I'm actively building with them **[YOUR STORY: name the actual project or course]**. Debugging instincts in production take longer to develop, and I already have them."

**"The role asks for 3+ years. You have about 1.5."**
> "That's fair. What I'd point to is the scope of that time. I was promoted from Technical Advisor to Subject Matter Expert in about a year. I'm now the person who handles the hardest escalations, validates developer fixes before release and trains new and senior agents. I'm used to getting up to speed fast."

**"Have you worked with HIPAA?"**
> "Not directly, and I won't pretend I have. But the same principles already shape how I work: least-privilege access (I've built tag-based IAM policies in AWS), MFA and account hardening, and keeping sensitive data out of logs and tickets. I also hold Securiti's AI Security and Governance certification. My understanding is that HIPAA's Security Rule turns those principles into required administrative, physical and technical safeguards."
> *Only say the next part if you've actually read up on it:* mention PHI, the "minimum necessary" standard, BAAs and audit logging (see section 3).

---

## 2. Behavioral questions (STAR, from your real experience)

**"Tell me about a difficult bug you tracked down."**
- **S:** An eCommerce-to-QuickBooks sync was failing **[YOUR STORY: which connector and what the symptom was]**
- **A:** Traced the transaction by correlation ID in Splunk, replayed the request in Postman, isolated the cause (expired OAuth token / 429 / malformed JSON / data-model mismatch)
- **R:** Wrote the RCA for engineering, QA-validated the fix, no regressions across the other connectors **[add a metric if you have one]**

**"Tell me about working with engineers."**
→ Your structured failure reports for DevOps and engineering on sync-pipeline failures, which shortened resolution time.

**"Tell me about a time you made your team better."**
→ You documented recurring 400/401/429/500 failure patterns to cut repeat escalations, trained two batches of new hires and taught senior agents Splunk log analysis.

**"Why healthcare?"**
> **[YOUR STORY]** Make it personal and real. One option is to bridge from your current work: "Right now, when an integration breaks, someone's books are wrong. In healthcare, it's someone's care. I want my debugging work to matter that much."

**"Why leave a support role for development?"**
> "I already do the investigation half of engineering: finding root causes and validating fixes. I want to own the build half too."

---

## 3. Technical questions to study

### REST APIs & integration (your strength, so go deep)
- **HTTP status codes:** 400 means bad request/payload; 401 means unauthenticated (missing or expired token); 403 means authenticated but not allowed; 404 means not found; 429 means rate limited (back off, respect the `Retry-After` header); 500 means a server-side failure.
- **How would you make a third-party integration resilient?** Retries with exponential backoff on 429/5xx only, idempotency keys so retries don't duplicate data, token refresh before expiry, timeouts, validating incoming payloads against a schema, a dead-letter queue for failed records, and correlation IDs for tracing. *You've seen every one of these failure modes, so tell real stories.*
- **OAuth 2.0:** authorization code flow, access vs. refresh tokens, scopes. In health tech, **SMART on FHIR** is OAuth 2.0 applied to EHR access.
- **REST design:** use resource nouns (`/patients/{id}/observations`), the correct HTTP verbs, pagination, versioning (`/v1/`).

### Health data APIs (know the vocabulary)
- **FHIR** (HL7 FHIR, usually R4) is the modern standard for health data exchange: JSON resources over REST. Common resources: `Patient`, `Observation` (vitals, labs), `Encounter`, `MedicationRequest`, `Condition`.
- **HL7 v2** is the older pipe-delimited messaging format, still common in hospitals.
- Know that US rules (21st Century Cures Act / ONC) push EHRs to expose FHIR APIs. That's why startups can integrate with them.
- Practice idea: query the public HAPI FHIR test server with Postman. It's a 30-minute exercise that lets you say "I've worked with FHIR resources" truthfully.

### HIPAA basics
- **PHI** (Protected Health Information) is health information linked to an identifiable person.
- **Privacy Rule** covers who can use and disclose PHI. **Security Rule** covers administrative, physical and technical safeguards for electronic PHI. **Breach Notification Rule** covers what to do when a breach happens.
- **Minimum necessary** means only access or return the PHI a task actually needs.
- **BAA** (Business Associate Agreement) is required with any vendor that handles PHI. On AWS, sign the BAA and only use HIPAA-eligible services.
- **Engineering practice:** encrypt data in transit (TLS) and at rest, use role-based/least-privilege access, keep audit logs of who accessed what, **never put PHI in application logs, error messages or URLs**, and require MFA and session timeouts.

### PostgreSQL
- Joins (inner vs. left), `GROUP BY`/aggregates, indexes (and when they help), primary vs. foreign keys, transactions (ACID), and parameterized queries to prevent SQL injection.
- Likely live task: "Write a query for each patient's most recent lab result." Practice window functions (`ROW_NUMBER() OVER (PARTITION BY patient_id ORDER BY taken_at DESC)`) or `DISTINCT ON`.

### Node.js (study before the interview)
- Event loop and non-blocking I/O, `async/await` and Promises, error handling in async code.
- Express basics: routes, middleware (auth, validation, error handlers), connecting to Postgres with `pg` using parameterized queries.
- Environment variables for secrets (never commit API keys).

### React (study before the interview)
- Components and props, `useState`, `useEffect` (data fetching, dependency array, cleanup), lifting state up, controlled forms.
- Dashboard concerns: loading, error and empty states; pagination; not storing PHI in `localStorage`.
- Likely live task: "Fetch a list from an API and render it with a loading state and an error state."

---

## 4. Questions to ask them
1. "Which health data sources do you integrate with today: EHRs via FHIR, labs, wearables? Which one breaks most often?"
2. "How do you handle PHI in development and testing? Synthetic data, de-identified data?"
3. "How are HIPAA responsibilities split between engineering and a compliance owner?"
4. "What would a successful first 90 days look like for this hire?"
5. "How do you monitor integration health in production?" *(This gives you a natural opening to talk about your Splunk and RCA experience.)*

---

## 5. Prep checklist before the interview
- [ ] Fill in every **[YOUR STORY]** with a real, specific example
- [ ] Have 2–3 numbers ready (from your `[METRIC NEEDED]` list)
- [ ] Build or finish a small React + Node + Postgres project, ideally one that reads FHIR sandbox data
- [ ] Practice one Postgres query and one React fetch-and-render component out loud
- [ ] Read HHS's HIPAA Security Rule summary page so the section 3 points are your own knowledge
