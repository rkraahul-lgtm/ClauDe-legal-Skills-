# What happened to each skill in claude-for-legal

Status words: **Adapted** = rewritten for Indian law and Rahul's rules. **Merged** = folded into another skill. **Dropped** = US-only or not useful for Rahul now (can be added later if he asks).

| Repo plugin | Repo skill | Status | Now / Reason |
|---|---|---|---|
| litigation-legal | matter-intake | Adapted | matter-intake |
| litigation-legal | matter-briefing | Adapted | matter-briefing |
| litigation-legal | matter-update | Adapted | matter-update |
| litigation-legal | matter-close | Adapted | matter-close |
| litigation-legal | matter-workspace | Merged | matter-intake (matter folders) |
| litigation-legal | chronology | Adapted | chronology |
| litigation-legal | demand-draft | Adapted | legal-notice-draft |
| litigation-legal | demand-intake | Adapted | notice-intake |
| litigation-legal | demand-received | Adapted | notice-received |
| litigation-legal | subpoena-triage | Adapted | summons-triage |
| litigation-legal | deposition-prep | Adapted | cross-exam-prep |
| litigation-legal | brief-section-drafter | Adapted | petition-section-drafter |
| litigation-legal | legal-hold | Adapted | document-preservation-notice |
| litigation-legal | privilege-log-review | Adapted | document-review-log |
| litigation-legal | portfolio-status | Adapted | portfolio-status |
| litigation-legal | oc-status | Adapted | co-counsel-status |
| litigation-legal | claim-chart | Dropped | US patent claim charts |
| litigation-legal | cold-start-interview | Adapted | cold-start-interview |
| litigation-legal | customize | Adapted | customize |
| commercial-legal | review | Merged | contract-review |
| commercial-legal | vendor-agreement-review | Adapted | contract-review |
| commercial-legal | saas-msa-review | Merged | contract-review |
| commercial-legal | nda-review | Adapted | nda-review |
| commercial-legal | amendment-history | Adapted | amendment-history |
| commercial-legal | renewal-tracker | Adapted | renewal-tracker |
| commercial-legal | escalation-flagger | Adapted | escalation-flagger |
| commercial-legal | stakeholder-summary | Adapted | stakeholder-summary |
| commercial-legal | review-proposals | Adapted | review-proposals |
| commercial-legal | matter-workspace | Merged | matter-intake |
| commercial-legal | cold-start-interview | Adapted | cold-start-interview |
| commercial-legal | customize | Adapted | customize |
| corporate-legal | board-minutes | Adapted | board-minutes |
| corporate-legal | written-consent | Adapted | written-consent |
| corporate-legal | entity-compliance | Adapted | entity-compliance |
| corporate-legal | material-contract-schedule | Adapted | material-contract-schedule |
| corporate-legal | closing-checklist | Adapted | closing-checklist |
| corporate-legal | tabular-review | Adapted | tabular-review |
| corporate-legal | diligence-issue-extraction | Adapted | diligence-issue-extraction |
| corporate-legal | deal-team-summary | Adapted | deal-team-summary |
| corporate-legal | integration-management | Dropped | Post-merger integration; not part of current practice. Can add. |
| corporate-legal | ai-tool-handoff | Dropped | Depends on US deal tools |
| corporate-legal | matter-workspace | Merged | matter-intake |
| corporate-legal | cold-start-interview | Adapted | cold-start-interview |
| corporate-legal | customize | Adapted | customize |
| privacy-legal | use-case-triage | Adapted | dpdp-check |
| privacy-legal | pia-generation | Adapted | dpdp-check |
| privacy-legal | dpa-review | Adapted | dpdp-check (contract part) and contract-review |
| privacy-legal | dsar-response | Adapted | data-principal-request |
| privacy-legal | reg-gap-analysis | Merged | dpdp-check |
| privacy-legal | policy-monitor | Dropped | US/EU feed monitoring |
| privacy-legal | matter-workspace | Merged | matter-intake |
| privacy-legal | cold-start-interview | Adapted | cold-start-interview |
| privacy-legal | customize | Adapted | customize |
| employment-legal | termination-review | Adapted | employment-review |
| employment-legal | hiring-review | Adapted | employment-review |
| employment-legal | worker-classification | Adapted | employment-review |
| employment-legal | wage-hour-qa | Merged | employment-review |
| employment-legal | policy-drafting | Merged | employment-review |
| employment-legal | handbook-updates | Merged | employment-review |
| employment-legal | internal-investigation | Adapted | internal-inquiry |
| employment-legal | investigation-open | Adapted | internal-inquiry |
| employment-legal | investigation-add | Adapted | internal-inquiry |
| employment-legal | investigation-memo | Adapted | internal-inquiry |
| employment-legal | investigation-query | Merged | internal-inquiry |
| employment-legal | investigation-summary | Merged | internal-inquiry |
| employment-legal | leave-tracker | Dropped | US leave law (FMLA, USERRA) |
| employment-legal | log-leave | Dropped | US leave law |
| employment-legal | expansion-kickoff | Dropped | US multi-country HR expansion |
| employment-legal | expansion-update | Dropped | US multi-country HR expansion |
| employment-legal | international-expansion | Dropped | US multi-country HR expansion |
| employment-legal | matter-workspace | Merged | matter-intake |
| employment-legal | cold-start-interview | Adapted | cold-start-interview |
| employment-legal | customize | Adapted | customize |
| ip-legal | cease-desist | Adapted | ip-notice-draft |
| ip-legal | infringement-triage | Adapted | ip-notice-draft (facts and proof part) |
| ip-legal | clearance | Dropped | US trademark/patent clearance tools |
| ip-legal | fto-triage | Dropped | US patent freedom-to-operate |
| ip-legal | invention-intake | Dropped | US patent practice |
| ip-legal | ip-clause-review | Merged | contract-review |
| ip-legal | oss-review | Dropped | Open-source licence scans; tech-company task |
| ip-legal | portfolio | Dropped | IP portfolio registers (USPTO) |
| ip-legal | takedown | Dropped | US DMCA takedown |
| ip-legal | matter-workspace | Merged | matter-intake |
| ip-legal | cold-start-interview | Adapted | cold-start-interview |
| ip-legal | customize | Adapted | customize |
| law-student | case-brief | Adapted | case-brief |
| law-student | socratic-drill | Adapted | socratic-drill |
| law-student | irac-practice | Adapted | irac-practice |
| law-student | outline-builder | Adapted | outline-builder |
| law-student | flashcards | Adapted | flashcards |
| law-student | study-plan | Adapted | study-plan |
| law-student | legal-writing | Adapted | legal-writing |
| law-student | cold-call-prep | Adapted | class-prep |
| law-student | exam-forecast | Adapted | exam-forecast |
| law-student | session | Adapted | study-session |
| law-student | bar-prep-questions | Dropped | US bar exam (MBE). Can be re-based to AIBE if wanted. |
| law-student | cold-start-interview | Adapted | cold-start-interview |
| law-student | customize | Adapted | customize |
| legal-clinic | client-intake | Merged | matter-intake |
| legal-clinic | client-letter | Adapted | client-letter |
| legal-clinic | plain-language-letters | Merged | client-letter |
| legal-clinic | client-comms-log | Merged | matter-update |
| legal-clinic | deadlines | Merged | limitation-and-deadlines |
| legal-clinic | memo | Adapted | legal-memo |
| legal-clinic | research-start | Adapted | legal-research |
| legal-clinic | status | Merged | portfolio-status |
| legal-clinic | draft | Merged | petition-section-drafter |
| legal-clinic | form-generation | Dropped | US court forms |
| legal-clinic | build-guide | Dropped | Clinic-specific |
| legal-clinic | ramp | Dropped | Clinic-specific |
| legal-clinic | semester-handoff | Dropped | Clinic-specific |
| legal-clinic | supervisor-review-queue | Dropped | Clinic-specific |
| legal-clinic | cold-start-interview | Adapted | cold-start-interview |
| legal-clinic | customize | Adapted | customize |
| regulatory-legal | policy-diff | Dropped | US/EU regulatory feeds; can add Indian regulator tracking |
| regulatory-legal | policy-redraft | Dropped | same |
| regulatory-legal | reg-feed-watcher | Dropped | same |
| regulatory-legal | gap-surfacer | Dropped | same |
| regulatory-legal | gaps | Dropped | same |
| regulatory-legal | comments | Dropped | US rulemaking comments |
| regulatory-legal | matter-workspace | Merged | matter-intake |
| regulatory-legal | cold-start-interview | Adapted | cold-start-interview |
| regulatory-legal | customize | Adapted | customize |
| product-legal | feature-risk-assessment | Dropped | Product counsel work (US/EU focus) |
| product-legal | is-this-a-problem | Dropped | same |
| product-legal | launch-review | Dropped | same |
| product-legal | marketing-claims-review | Dropped | US advertising rules |
| product-legal | matter-workspace | Merged | matter-intake |
| product-legal | cold-start-interview | Adapted | cold-start-interview |
| product-legal | customize | Adapted | customize |
| ai-governance-legal | ai-inventory | Dropped | EU AI Act / US focus |
| ai-governance-legal | aia-generation | Dropped | same |
| ai-governance-legal | policy-monitor | Dropped | same |
| ai-governance-legal | policy-starter | Dropped | same |
| ai-governance-legal | reg-gap-analysis | Dropped | same |
| ai-governance-legal | use-case-triage | Dropped | same |
| ai-governance-legal | vendor-ai-review | Dropped | same |
| ai-governance-legal | matter-workspace | Merged | matter-intake |
| ai-governance-legal | cold-start-interview | Adapted | cold-start-interview |
| ai-governance-legal | customize | Adapted | customize |
| legal-builder-hub | * | Dropped | Skill-store management for the US repo (10 skills). Not needed. |

New skills with no match in the repo: verify-citations, old-to-new-code-mapper, limitation-and-deadlines, stamp-and-registration-check, drafting-handoff, ip-notice-draft (partly).
