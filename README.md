# rahul-legal-india


> **Licence.** Apache License 2.0 (see `LICENSE`). Built from Anthropic's `claude-for-legal` repository (see `LICENSE-NOTICE.md`), rewritten for Indian law. The skill `skills/dpdp-analyze` is by Mayank Dsouza under the MIT licence (see `skills/dpdp-analyze/LICENSE-MIT.txt`). This is a draft-help tool for an advocate. It is not legal advice.
A custom plugin for Rahul Kumar, built from Anthropic's open `claude-for-legal` repo (Apache-2.0) and rewritten for Indian law and Rahul's own rules.

## The main promise

- It asks before it acts. It does not assume.
- It never uses a case that did not come from a real source (the Courrt tool, or text Rahul pasted). Every case comes with name, court, year, citation and a link.
- It quotes a section only from a retrieved source. Otherwise it says `[section text not retrieved - verify]`.
- Everything is a draft for Rahul to check. It saves to `D:/Temp/Output`, asks before overwriting, and never deletes.

## Install

**Claude (Cowork / desktop app):** open Customize, then Plugins, and upload `rahul-legal-india.zip`.

**Claude Code:** unzip `rahul-legal-india-marketplace.zip`, then run `/plugin marketplace add <folder>` and `/plugin install rahul-legal-india@rahul-legal-india`.

## First step

Run `/rahul-legal-india:cold-start-interview`. It asks short questions and saves your profile.

## Tools it uses if they are connected

- **Courrt** (Supreme Court and High Court judgments, central and state Acts)
- **LegalInk Inka** (BNS/BNSS/BSA lookup, notice replies)
- **indian-contracts-drafting** plugin (for drafting deeds and agreements)

If a tool is not connected, the skill says so. It does not fill the gap from memory.

## If Courrt is lost

Use `/rahul-legal-india:judgment-source-fallback`. It finds High Court and Supreme Court orders and judgments through the official portals (eCourts High Court Services, the Supreme Court website, the Allahabad High Court ILR and AFR page), free open data on AWS, two GitHub tools, and Indian Kanoon for leads. The full list, with addresses and limits, is in `references/judgment-sources.md`. `legal-research` and `verify-citations` call this skill by themselves when Courrt does not answer. The rule stays the same: no case is used unless a real source returned it in this chat.

## Skills (57)

### Set-up, research and checking

- `/rahul-legal-india:cold-start-interview` - Set up the plugin once. Asks Rahul short questions and saves his practice profile (courts, language, output folder, preferences).
- `/rahul-legal-india:customize` - Change one part of the practice profile or one skill's behaviour (language, output folder, formats, escalation, style).
- `/rahul-legal-india:verify-citations` - Check every case and section in a draft against real sources. Use before filing or sending anything, or when Rahul says 'verify', 'check citations', 'are these cases real'. Flags anything that cannot be confirmed.
- `/rahul-legal-india:legal-research` - Start research on an Indian law question: find the right statute text and real judgments, with links.
- `/rahul-legal-india:old-to-new-code-mapper` - Map IPC, CrPC and Evidence Act sections to BNS, BNSS and BSA (and back), with the section text.
- `/rahul-legal-india:judgment-source-fallback` - Find High Court and Supreme Court orders and judgments when Courrt is not connected or not answering, using official portals, free open data and other listed sources.

### Litigation

- `/rahul-legal-india:matter-intake` - Open a new litigation matter: collect facts, parties, court, stage, dates and documents, then create the matter folder.
- `/rahul-legal-india:matter-briefing` - Make a short briefing note on one matter from its file: facts, status, dates, what is pending, what is risky. Use before a hearing or meeting, or when Rahul says 'brief me on', 'where are we on'.
- `/rahul-legal-india:matter-update` - Record what happened today in a matter (hearing, order, filing, client call) and update next steps and dates.
- `/rahul-legal-india:matter-close` - Close a matter: check nothing is pending, list outcomes and documents to keep, and write a closing note.
- `/rahul-legal-india:chronology` - Build a dated timeline of events from documents, with the source for every entry.
- `/rahul-legal-india:legal-notice-draft` - Draft a legal notice (demand notice) to be sent for a client: facts, demand, time limit, consequences.
- `/rahul-legal-india:notice-intake` - Take in a client's complaint or demand before a notice is sent: facts, proof, amount, and what the client wants.
- `/rahul-legal-india:notice-received` - Handle a legal notice received by a client: read it, list allegations, check the deadline, and draft a point-wise reply.
- `/rahul-legal-india:summons-triage` - Triage a summons, notice of motion or process received: what court, what it wants, when to appear, what to do first.
- `/rahul-legal-india:cross-exam-prep` - Prepare to cross-examine or examine a witness: list the points to prove or break, with the document for each, and question outlines.
- `/rahul-legal-india:petition-section-drafter` - Draft one section of a petition, plaint, written statement, application, appeal or written argument: facts, grounds, prayer, or argument point.
- `/rahul-legal-india:limitation-and-deadlines` - Work out limitation and other time limits for a filing or step, showing the working and the source.
- `/rahul-legal-india:portfolio-status` - Show the status of all open matters in one table: forum, stage, next date, pending work, risk.
- `/rahul-legal-india:co-counsel-status` - Track work given to junior advocates, outside or local counsel in other courts: what was asked, due dates, replies, follow-ups.
- `/rahul-legal-india:document-preservation-notice` - Draft a notice to a client or other person to keep documents, messages and devices safe because a dispute is coming.
- `/rahul-legal-india:document-review-log` - Review a set of documents and log each one: type, date, who, relevance, confidential or privileged-looking, and how to produce or object.
- `/rahul-legal-india:client-letter` - Write a clear, formal letter or email to a client explaining where the matter stands, advice given, or what is needed.
- `/rahul-legal-india:legal-memo` - Write an internal legal memo or opinion note on a question: facts, issue, law, analysis, conclusion, with real sources only.
- `/rahul-legal-india:ip-notice-draft` - Draft a cease-and-desist or infringement notice for trademark, copyright or passing off for an Indian client, after checking facts and proof.

### Contracts and employment

- `/rahul-legal-india:contract-review` - Review a vendor, service, SaaS, supply or other commercial agreement under Indian law: risky clauses, missing clauses, suggested changes.
- `/rahul-legal-india:nda-review` - Review or triage a non-disclosure agreement for an Indian client: one-way or mutual, scope, term, exceptions, remedies, dispute clause.
- `/rahul-legal-india:amendment-history` - Read a main agreement and all its amendments, side letters and renewals, and show what the contract says now.
- `/rahul-legal-india:renewal-tracker` - Keep a register of contracts with renewal and notice dates, and warn before notice windows close.
- `/rahul-legal-india:escalation-flagger` - Decide whether a contract issue needs to go to a senior person or the client's board, and draft the short escalation note.
- `/rahul-legal-india:stakeholder-summary` - Turn a legal review into a short plain note for a client or business person who is not a lawyer.
- `/rahul-legal-india:review-proposals` - Compare the other side's redline or counter-draft against our last draft and the client's position: what changed, what is acceptable, what to push back on.
- `/rahul-legal-india:stamp-and-registration-check` - Check what stamp duty and registration an Indian document may need, by state and type, and flag risks of an unstamped or unregistered document.
- `/rahul-legal-india:drafting-handoff` - Route a drafting request to the right Indian contract drafting skill (NDA, employment, sale deed, lease, loan, shareholders, GPA/SPA, will, arbitration clause, service agreement) after collecting the facts.
- `/rahul-legal-india:employment-review` - Review an employment issue under Indian law: offer letter, termination, notice, dues, worker classification, workplace complaint steps.
- `/rahul-legal-india:internal-inquiry` - Plan and record an internal workplace inquiry: scope, witnesses, evidence list, interview outline, findings note.

### Company and deal work

- `/rahul-legal-india:board-minutes` - Draft or tidy minutes of a board, committee or general meeting of an Indian company from notes or a recording transcript.
- `/rahul-legal-india:written-consent` - Draft a resolution passed by circulation (without a meeting) for directors or members of an Indian company, with covering note and approval record.
- `/rahul-legal-india:entity-compliance` - Build a calendar of company and entity filings and meetings (Registrar of Companies, tax, labour and others) for an Indian entity.
- `/rahul-legal-india:material-contract-schedule` - List a company's important contracts with key terms in one schedule for a sale, investment, audit or disclosure.
- `/rahul-legal-india:closing-checklist` - Create and update a closing checklist for a deal (share transfer, investment, asset sale, loan): documents, signatories, approvals, filings, status.
- `/rahul-legal-india:tabular-review` - Pull the same set of facts out of many documents into one table (dates, parties, clauses, amounts).
- `/rahul-legal-india:diligence-issue-extraction` - Go through due diligence documents and list issues by area with severity and a source for each.
- `/rahul-legal-india:deal-team-summary` - Write a short status note for the deal team or client: what is done, what is stuck, what is needed from whom.

### Data protection

- `/rahul-legal-india:dpdp-check` - Check a product, process or contract that uses personal data against India's data protection law (DPDP Act 2023 and rules): roles, consent, notice, children, data sharing, transfers.
- `/rahul-legal-india:dpdp-analyze` - Deeper DPDP Act 2023 and DPDP Rules 2025 analysis, section by section, using the Act text, a rules summary and a compliance checklist kept inside the plugin. From github.com/mksd0398/dpdp-act-skill (MIT licence).
- `/rahul-legal-india:data-principal-request` - Handle a request from a person about their personal data (access, correction, erasure, grievance): steps, deadline, reply draft.

### Study (Lawctopus and exams)

- `/rahul-legal-india:case-brief` - Help Rahul brief a case: facts, issue, holding, reasoning, rule. Works from the judgment text.
- `/rahul-legal-india:socratic-drill` - Quiz Rahul by questions, push back on weak answers, and not give the answer until he has tried.
- `/rahul-legal-india:irac-practice` - Practise Issue, Rule, Application, Conclusion on Indian law problems: gives a fact problem, grades Rahul's answer, does not rewrite it.
- `/rahul-legal-india:outline-builder` - Build a course outline from Rahul's notes, class material and the Act text: topics, rules, section numbers, cases (real ones only).
- `/rahul-legal-india:flashcards` - Make flashcards from Rahul's notes or an Act: question on one side, answer and section on the other.
- `/rahul-legal-india:study-plan` - Make a day-by-day study plan from Rahul's syllabus, dates and free hours.
- `/rahul-legal-india:legal-writing` - Give feedback on Rahul's own legal writing (answer, article, note, petition draft): structure, clarity, plain words, citation form.
- `/rahul-legal-india:class-prep` - Prepare Rahul for a class, a mock, or a viva: key points, likely questions from the material, and a few practice questions.
- `/rahul-legal-india:exam-forecast` - Look at Rahul's past papers, syllabus and notes and list the topics that came up often and may come again.
- `/rahul-legal-india:study-session` - Run a study session: Rahul picks what to work on and the skill picks the right tool (drill, brief, outline, cards).

## What was left out

See `references/repo-skill-map.md`. US-only skills (DMCA, FMLA, EU AI Act, US patent work, US bar exam) were dropped.

## Words explained

- **Plugin**: a bundle of skills you add to Claude.
- **Skill**: one saved task with steps Claude follows.
- **MCP / tool**: a connection that lets Claude look things up, like Courrt.
- **Provisional mode**: working with plain defaults before the profile is set up.
