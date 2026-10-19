# Claude Certified Architect – Foundations (CCAR-F): What's Changed Since the utkarsh1agarwal Study Guide (as of October 19, 2026)

The exam itself hasn't changed since the repo was written: CCAR-F is still built on the Version 1.0 exam guide (effective July 2026), which is the same guide the repo links. Domains, weights, the 60-item / 4-of-6-scenario format, the 720 pass mark and the $125 fee all match. What has moved is everything around the exam. The rest of the certification program has expanded and is due for a content refresh in December. The official practice exam is gone. And Claude itself has changed so much (new models, renamed tools, a new structured-output API) that several of the guide's details now differ from the live docs. Keep the repo as your core, and use the additions below to deal with the drift.

## TL;DR

- **The blueprint the repo covers is still current.** The repo matches the current v1.0 guide on every exam fact: 5 domains at 27/18/20/20/15%, 60 items, 120 minutes, scaled 720/1,000, $125, 12-month validity, Pearson VUE delivery. Pearson's notice of a **December 7, 2026 content update** lists the Associate, Developer and Architect – Professional exams. It does **not** list CCAR-F.
- **Policy and program additions.** CCAR-F is now one of four certifications. The official practice exam was retired in the move to Pearson, and the guide's 12 sample questions are the only official practice material. Pearson and the FAQ say you can reschedule up to 48 hours before your exam, while the guide says 24, so plan around 48. Registration is limited to people at Claude Partner Network organizations who use a company email.
- **Technical drift to study.** Task→Agent tool rename. Slash commands merged into skills. `allowed-tools` now *pre-approves* tools rather than restricting them. `/context` sits alongside `/memory`. Structured outputs now go through `output_config.format` / `strict: true`. The newest models reject forced `tool_choice`. A new model lineup (Opus 5.5, Sonnet 5.5, Haiku 5.5, Fable 5.1). Sonnet 4.5 retires November 30, 2026. **On the exam, answer the way the guide frames things. Learn the current docs so the newer wording doesn't trip you up.**

## Key Findings

### 1. The baseline: what the repo covers

The repo is billed as a "free study guide, learning material & 6 mock exams" for the Claude Certified Architect – Foundations exam (it uses both "CCAF" and "CCAR-F").\[1\] It has:

- one study file per domain
- `about-the-exam.md`, `scenarios.md`, `study-plan.md`, `cheat-sheet.md`, `resources.md` and `faq.md`
- six timed mock exams (360 questions) with an interactive player\[1\]\[2\]

Its "at a glance" table lists:

- 60 scenario-based multiple-choice / multiple-response items\[1\]
- 4 scenarios drawn at random from a bank of 6\[1\]
- 120 minutes
- scaled 720/1000 to pass
- $125
- 12-month validity
- online proctored or Pearson VUE test center

The repo has 9 commits, 17 stars and 11 forks.\[1\] I couldn't open the commit history or the CHANGELOG to get exact dates. Karo Zieminski's Substack post "What Is the CCAR-F Exam, and Is It Worth It?" (Product with Attitude, July 31, 2026) links the repo as "this GitHub study guide, which includes six full mock exams with 360 questions," so it existed by then.

The repo's core idea matches the exam's philosophy well: "a structural or programmatic fix (a hook, a prerequisite, a `tool_use` schema, a scoped tool) beats a prompt-based fix almost every time."\[1\]

### 2. Current official exam facts

| Item | Current official value | Source | Repo status |
|---|---|---|---|
| Name / code | Claude Certified Architect – Foundations, **CCAR-F** | v1.0 exam guide; Pearson VUE | ✅ (uses CCAF alias too) |
| Guide version | **Version 1.0 · Effective July 2026** (v0.1 Feb 2026, v0.2 June 2026) | Exam guide document control | ✅ links the same PDF |
| Items / format | 60; multiple-choice and multiple-response, "each item states how many responses to select" | Exam guide | ✅ |
| Structure | 4 scenarios drawn from a bank of 6 | Exam guide | ✅\[3\] |
| Time | 120 minutes; plan "about 135 minutes of total seat time" | FAQ | ✅ (seat time likely missing)\[4\] |
| Passing score | Scaled 720 on a 100–1,000 scale; percent-correct by domain on the score report | Exam guide; FAQ | ✅\[3\]\[4\] |
| Fee | $125 (rose from $99 effective June 30, 2026) | FAQ; Skilljar checkout | ✅\[4\]\[5\] |
| Discounts | Select/Preferred/Global Premier partners get 50% off; Global Premier get 100% through Dec 31, 2026 | FAQ | ⚠️ verify\[4\] |
| Validity / renewal | 12 months; free, non-proctored renewal assessment if done on time; a lapse means retaking the full exam at full fee | Exam guide §15; FAQ | ✅ validity; ⚠️ renewal details\[3\]\[4\] |
| Retakes | Waits of 14 / 30 / 90 days after the 1st / 2nd / 3rd fail; max 4 attempts per rolling 12 months; full fee for each attempt | Pearson VUE; exam guide | ⚠️ verify\[3\]\[6\] |
| Reschedule / cancel | **48 hours** (Pearson and FAQ) vs **24 hours** (guide §11) | Pearson VUE; FAQ; guide | ⚠️ conflict\[3\]\[6\] |
| Eligibility | Claude Partner Network organizations only; partner email on a recognized domain; age 18+ | FAQ | ⚠️ verify |
| Rules | Closed book; English only; no translation tools or AI | FAQ | ⚠️ verify |
| Registration validity | 5 years from registration | FAQ | likely missing |
| Practice exam | **Retired** in the move to Pearson; the guide's sample questions are the only official practice | FAQ | ⚠️ verify\[4\] |

Audience: the guide describes the ideal candidate as "a solution architect who designs and implements production applications with Claude" with "6+ months of practical experience building with Claude APIs, Agent SDK, Claude Code, and MCP."\[3\]\[7\] The FAQ says there is no formal prerequisite.\[2\]\[4\]

How registration works:

1. Register and pay by card on the certification's page in Anthropic Partner Academy.\[2\]\[4\]
2. You receive an email with a Pearson link.\[4\]
3. Schedule either OnVUE online proctoring or a test center.\[4\]\[7\]

Residents of Iran are suspended from testing (both online and at test centers) as of September 8, 2026. IDs from Belarus, Cuba, North Korea, Russia, Syria and restricted regions of Ukraine can't be used for OnVUE, so those candidates must test at a center.\[4\]

### 3. What changed since about July 2026 (official)

- **Four certifications, not one.** Anthropic's July 23 blog announced three new role-based credentials.\[8\]\[9\]\[10\] The lineup is now:

  | Certification | Code | Fee |
  |---|---|---|
  | Associate – Foundations | CCAO-F | $99 |
  | Developer – Foundations | CCDV-F | $125 |
  | Architect – Foundations | CCAR-F | $125 |
  | Architect – Professional | CCAR-P | $175\[4\]\[6\] |

  Architect – Professional has no formal prerequisite, and Foundations does not upgrade to it automatically.\[4\]\[11\]
- **Exam refresh on December 7, 2026.** Pearson (page updated 2026-10-16): "The Associate – Foundations, Developer – Foundations, and Architect – Professional exams will include updated content starting on this date. Updated exam guides will be available on November 17, 2026."\[6\]
  - CCAR-F is not on that list.
  - I found no Anthropic statement explaining why CCAR-F was left out, or saying whether it will get a new guide.
  - The CCAR-F page still links the same v1.0 PDF.\[5\]
  - Anthropic's policies page warns: "If we substantially update an exam, holders may need to pass the current version to stay certified." It also says retake waiting periods and attempt counts reset when an exam moves to a new version.\[12\]
  - **Check the CCAR-F page again on November 17.**
- **Pearson move (June 30, 2026).** Delivery moved from ProctorFree to Pearson and badges moved to Credly. Earlier six-month credentials were extended to 12 months.\[13\] Score reports from ProctorFree-era exams are no longer available.\[4\]\[8\]
- **Claude Academy.** Anthropic Academy became Claude Academy at academy.claude.com on August 20, 2026. It now covers Claude.ai, Cowork, Claude Code, Claude Tag and the Claude Platform. vanja.io's tracker reports that the Academy catalogue file, "regenerated on October 9, now lists 308 resources: 27 courses, 124 tutorials and 157 use cases," with "Introduction to Claude Tag" as the newest course according to Pasquale Pillitteri.
  - Partner prep for CCAR-F is still a list of general courses, not a dedicated course: AI Fluency, Building with the Claude API, Claude on Google Cloud and Introduction to MCP.\[14\]\[15\]
  - Architect – Professional has its own prep course.\[16\]

### 4. Where the v1.0 guide now differs from current Claude docs

The exam is written against the guide. Several guide details have since moved in the product. Learn both versions.\[2\]

| Guide says (exam answer) | Current reality | Source |
|---|---|---|
| Subagents are spawned with the **Task** tool; `allowedTools` must include "Task"\[3\] | "In version 2.1.63, the Task tool was renamed to Agent. Existing Task(...) references... still work as aliases"\[17\] | Claude Code subagent docs |
| Slash commands live in `.claude/commands/`; skills live in `.claude/skills/` | Custom commands have been merged into skills. `.claude/commands/` still works, and a skill wins if both exist at the same path\[18\] | Claude Code skills docs and community guides |
| `allowed-tools` *restricts* a skill's tool access | `allowed-tools` = "Tools Claude can use without asking permission"; `disallowed-tools` = "Tools removed from Claude's available pool while this skill is active"\[19\] | Claude Code skills docs; Claude Academy |
| `@import` syntax; `/memory` to check loaded files | The syntax is `@path/to/file`; run `/context` to see what loaded under "Memory files."\[2\] Imports don't save context, but path-scoped rules do\[20\] | Claude Code memory docs |
| Structured output = `tool_use` + JSON schema; `tool_choice: "any"` or forced | Structured outputs are generally available via `output_config.format` (JSON outputs) and `strict: true` (strict tool use)\[21\] | Platform structured-outputs docs\[2\] |
| Forced `tool_choice` ("any" / named tool) | Returns a **400 error** on Fable 5.1 / Mythos 5.1 (since Sept 1), Opus 5.5 (Sept 22) and Sonnet 5.5 (Sept 28); use `auto` + strict tool use instead\[22\] | Platform release notes |
| Batch can't do multi-turn tool calling | Batches can carry multi-turn history and run Anthropic server tools, but still can't complete a client-side tool loop\[2\] | Karo Zieminski's guide-vs-docs comparison (community)\[2\] |

**Exam strategy:** if a question asks how to guarantee a tool call or structured output, the guide-consistent answer (`tool_choice: "any"` / a forced tool, `tool_use` + schema) is what gets marked correct. The certification FAQ calls the exam guide "the authoritative source for exam scope."\[4\] In real projects, use the current docs.

### 5. Model lineup and deprecations (affects examples, not blueprint)

According to the Claude Platform release notes, the current models are:

| Model | Released | Pricing (input / output per MTok) |
|---|---|---|
| Claude Fable 5.1 | Sep 1 | $10 / $50 |
| Claude Opus 5.5 | Sep 22 | $4 / $20 |
| Claude Sonnet 5.5 | Sep 28 | — |
| Claude Haiku 5.5 | Oct 7 | — |

All four have a 1M context window and 128k max output.\[23\]

Deprecations:

- Retired: Sonnet 4 and Opus 4 (June 15) and Opus 4.1 (August 5).\[22\]
- Sonnet 4.5 was deprecated September 30, 2026 and retires from the Claude API November 30, 2026.\[24\]

If any mock answer or explanation in the repo names these older models or uses manual `budget_tokens` thinking, treat it as illustrative only. The guide puts "performance benchmarking or model comparison metrics" out of scope.\[3\] Issam Louhmam, who wrote 360 practice questions (he is not reporting as an exam taker), notes on DEV Community that "a bigger model or a bigger context window... rarely fixes attention, tool selection or missing information. It's only the answer when the question is about capacity itself."

Other new platform features stay **outside the CCAR-F blueprint**: Managed Agents, the compaction API, cache diagnostics and fast mode. The guide explicitly excludes "Prompt caching implementation details (beyond knowing it exists)," streaming, computer use, vision, and cloud-provider configuration.\[3\] Don't over-study them for this exam.

### 6. Community signals (unofficial, self-reported)

- **What the exam rewards.** WenHao Yu (882/1000, exam August 24, 2026) says the exam "wants the mechanically cleanest answer, not the one that gets by in practice." He adds that wrong answers favor "add more examples, write a more precise description, switch to a stronger model, tell it to check itself."\[7\]
- **Time pressure.** At 2 minutes per question, long English scenarios are hard. Yu went from 4–5 minutes per question to finishing with 15 minutes to spare.\[7\]
- **Difficulty varies widely.** Karo Zieminski's guide collects these reports:
  - Matthew Purcell prepared for about six hours on top of daily Claude use and scored 811.
  - Akshay Kokane studied for almost two weeks and raised his practice score from 677 to 910 before passing.
  - Prasad Rao studied for two weeks.
  - A Reddit r/ClaudeAI post titled "I have failed the Claude CCAR-F exam" says an experienced cloud architect failed with 598 after three weeks despite high mock scores.

  Szymon Paluch (passed July 15) said "the sample questions I studied were easier than those on my exam form."\[25\]\[26\]
- **Stale or wrong mocks.** Zawanah's exam report, as cited by Zieminski, "warns that some mock answers are ambiguous or wrong." Third-party sites selling "dumps" breach the NDA and should be avoided.\[12\]
- **Gap in the reports.** No first-hand report I found says whether the newer features (Agent rename, `output_config.format`, 5.5 models) appeared on the exam. Candidates cite the NDA.

## Gap Analysis

**(a) What the repo covers well**

- All exam logistics in the README match the current v1.0 guide.
- It maps all six scenarios to domains.\[1\]
- Its "deterministic beats probabilistic" principle and the upstream-root-cause rule match the sample questions closely (Q1, Q7, Q8).
- Six mock exams, including hard mode.\[1\] They are useful for building speed, which candidates say is a real constraint.\[7\]

**(b) Outdated or possibly inaccurate**

- Possibly wrong: the reschedule window (if the repo says 24 hours, flag 48 hours instead).
- Possibly wrong: any mention of an official practice exam, ProctorFree, the $99 fee or 6-month validity. I couldn't read `about-the-exam.md` to check.
- Any code examples using older model IDs (Sonnet 4/4.5, Opus 4/4.1) or manual extended thinking.
- "CCAF" is a community alias. The official code is CCAR-F.\[2\]

**(c) What to add, in priority order**

1. **The Dec 7 refresh watch.** Add a note to re-check the CCAR-F page and the exam guide on November 17, 2026, and to book before or after accordingly.
2. **A "guide vs current docs" appendix** covering Task/Agent, commands/skills, `allowed-tools`/`disallowed-tools`, `@path`/`/context`, `output_config.format`/`strict`, forced `tool_choice` 400s, and batch nuances. Mark the exam answer and the current behavior side by side.
3. **The 12 official sample questions.** Make them the calibration set. They are now the *only* official practice.
4. **Policy updates.** 48-hour reschedule. 5-year registration window. Partner-only eligibility and 18+. Partner-tier discounts. English-only and closed-book rules. 14-day appeal window. About 135 minutes of seat time. Renewal is free only if done on time.
5. **The four-certification landscape.** CCAO-F, CCDV-F, CCAR-P with fees, plus the fact that there are no prerequisites between them.
6. **A current model lineup sidebar and deprecation dates.** Mark it as context only, not exam content.
7. **Out-of-scope reminders.** Don't spend time on Managed Agents, caching internals, streaming, computer use or vision for CCAR-F.

## Recommendations

- **If you can test before December 7, do it.** The v1.0 blueprint is stable and the repo matches it. CCAR-F isn't in the announced refresh, but confirm on November 17.
- **Study order:**
  1. Read the official guide in full, especially the task statements in §6 and the appendix's in-scope and out-of-scope lists.
  2. Use the repo's domain files, with Domain 1 first at 27%.
  3. Build the guide's four preparation exercises hands-on.
  4. Calibrate against the 12 sample questions and the repo's mocks under timed conditions.
  5. Review the guide-vs-docs differences above.
- **Primary sources to bookmark:**
  - the CCAR-F certification page and exam guide PDF on anthropic-partners.skilljar.com
  - the certification FAQ
  - Pearson VUE's Anthropic page
  - the Claude Code docs on subagents, skills and memory at code.claude.com
  - the Platform structured-outputs docs, release notes and model deprecations at platform.claude.com
  - Anthropic's July 23 certifications blog post at claude.com

## Caveats

- I couldn't read the repo's individual files or its commit dates. My judgments about what it covers come from the README and file structure.
- I found no official explanation of the December 7 update, of why CCAR-F was left out, or of what content changes are coming.
- Community experiences are self-reported and unverified. Some sites in this space sell question dumps, which breach the NDA, and their pass claims shouldn't be trusted.
- Program details have changed without notice before: the Global Premier waiver was moved from August 31 to December 31 without notice.\[8\] Re-check prices and policies at checkout.

## Sources

1. [GitHub - utkarsh1agarwal/claude-architect-exam-guide: Free study guide, learning material & 6 mock exams for Anthropic's Claude Certified Architect – Foundations (CCAF / CCAR-F) exam.](https://github.com/utkarsh1agarwal/claude-architect-exam-guide)
2. [What Is the CCAR-F Exam, and Is It Worth It? A Decision Guide for Claude Builders](https://karozieminski.substack.com/p/claude-certified-architect-foundations-exam)
3. <https://everpath-course-content.s3-accelerate.amazonaws.com/instructor/6nizmqk8tpzpfjvt6qmmav7rh/public/1783542750/Claude+Certified+Architect+%E2%80%93+Foundations+Exam+Guide.pdf>
4. [FAQ - Certifications](https://anthropic-partners.skilljar.com/page/faq-certifications)
5. [Claude Certified Architect – Foundations Certification](https://anthropic-partners.skilljar.com/claude-certified-architect-foundations-certification)
6. [Claude Certification Program | AI, Machine Learning & LLM Development](https://www.pearsonvue.com/us/en/anthropic.html)
7. [How I Passed the Claude Certified Architect Exam (CCAR-F): 882/1000, No Question Bank | WenHao Yu](https://yu-wenhao.com/en/blog/ccar-f-exam-experience/)
8. [Claude Certification Changes, Month by Month](https://credfarmer.com/blog/claude-certification-changes)
9. [Claude Certifications in 2026: What the Exam Guides Reveal](https://shajeelafzal.com/blog/claude-certifications-2026)
10. [Four role-based certifications for the people who put Claude to work for customers](https://claude.com/blog/four-role-based-claude-certifications)
11. [Claude Certifications 2026: All 4 Exams Compared](https://credfarmer.com/certifications)
12. [Policies - Certifications](https://anthropic-partners.skilljar.com/page/policies-certifications)
13. [Claude Certifications: All Four Exams, Costs and Eligibility](https://trainingcamp.com/articles/claude-certifications-explained-all-four-anthropic-exams-costs-and-who-can-take-them/)
14. [Claude Certified Architect - Foundations Prep Courses](https://anthropic-partners.skilljar.com/page/claude-certified-architect-foundations-prep-courses)
15. [Raising Steam on Anthropic’s New Certifications](https://loginov-rocks.medium.com/raising-steam-on-anthropics-new-certifications-62e0d14cc8e0)
16. [Claude Certification Exam Prep Courses](https://anthropic-partners.skilljar.com/page/claude-certification-exam-prep-courses)
17. [Create custom subagents - Claude Code Docs](https://code.claude.com/docs/en/sub-agents)
18. [claude-howto/03-skills/README.md at main · luongnv89/claude-howto · GitHub](https://github.com/luongnv89/claude-howto/blob/main/03-skills/README.md)
19. [Extend Claude with skills - Claude Code Docs](https://code.claude.com/docs/en/skills)
20. [How Claude remembers your project - Claude Code Docs](https://code.claude.com/docs/en/memory)
21. [Structured outputs - Claude Platform Docs](https://platform.claude.com/docs/en/build-with-claude/structured-outputs)
22. [Claude Platform release notes](https://platform.claude.com/docs/en/release-notes/overview)
23. [Claude Models Comparison 2026: Claude 4 to Opus 5.5](https://felloai.com/ultimate-claude-model-comparison/)
24. [Claude Sonnet 4.5 deprecated: retirement date and how to switch](https://madrobot.blog/2026/10/13/claude-sonnet-4-5-retirement-date-november-30-deprecated-how-to-switch/)
25. [Claude Certified Architect Foundations: my exam experience - DEV Community](https://dev.to/szymonpaluch/claude-certified-architect-foundations-my-exam-experience-1fdn)
26. [60 Claude Certified Architect Exam Questions & Answers (CCAR-F)](https://szymonpaluch.com/blog/posts/claude-certified-architect-practice-questions)
