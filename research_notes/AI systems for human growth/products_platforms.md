# Products and Platforms for Accelerating Human Learning and Growth: Design Mechanisms and Evidence (as of 2026-11-23)

Method note: about 23 web searches. Direct page fetches were blocked for some hosts in this session (fortune.com, news.harvard.edu), so some findings rely on search-result summaries of primary pages. Each claim is labeled VENDOR (self-reported or marketing), PRESS (journalism), or INDEPENDENT (RCT or third-party evaluation) where that matters.

## Q1. Mastery and adaptive platforms: core mechanics and evidence of outcomes

### Takeaway
The strongest platforms share one architecture: a fine-grained prerequisite graph, a per-learner model of each node (mastery probability or memory half-life), a high mastery bar before advancing, and scheduled spaced review. Independent evidence for software of this kind clusters at small effects, roughly 0.05 to 0.20 SD per year. Large claims (Math Academy at "3-4x" speed, Alpha at "2x" learning and "top 1-2%") are self-reported, and Alpha's own internal data undercuts its claim. Engagement and dosage are the binding constraints, more than algorithm quality.

### Cited Findings
**Math Academy (knowledge graph + FIRe + mastery learning)**
- FIRe (Fractional Implicit Repetition) extends spaced repetition to hierarchical subject matter. A review of an advanced topic "trickles down" as implicit, partial credit to the prerequisite topics it encompasses. Credit is discounted when a simpler topic is reviewed too early. Companion mechanism: "Spaced Repetition Compression" chooses reviews whose implicit repetitions clear other due reviews, which minimizes the total number of reviews — [Skycak, "Individualized spaced repetition in hierarchical knowledge structures"](https://www.justinmath.com/individualized-spaced-repetition-in-hierarchical-knowledge-structures); [gwern mirror](https://gwern.net/doc/www/www.justinmath.com/9af2ce40376e836660c237a0e971d1896a163eee.html)
- Partial credit for implicit reviews of prerequisites is a deliberate design choice — [Frank Hecker's review of *The Math Academy Way*](https://frankhecker.com/2025/02/14/math-academy-part-7/); full book draft: [The Math Academy Way (PDF)](https://www.justinmath.com/files/the-math-academy-way.pdf)
- The knowledge graph reportedly has about 2,800 or more math topics, with prerequisite and "encompassing" edges. This figure comes from a third-party podcast summary, so it is less authoritative — [podwise summary](https://podwise.ai/dashboard/episodes/7308168)
- XP is roughly one minute of focused effort. There is a daily XP goal, and XP rewards correct answers and good habits (penalties for guessing or skipping). The diagnostic uses a high mastery bar, so it often sends students back to foundational topics — [Math Academy: How it works](https://mathacademy.com/how-it-works)
- VENDOR: FIRe "compresses what normally takes 180 classroom hours into 20-40 hours" — [Math Academy homepage / How our AI works](https://mathacademy.com/how-our-ai-works)
- VENDOR: Skycak says students "typically learn about 3-4x as fast as a normal class." In the original Pasadena program, 6th and 7th graders covered prealgebra through precalculus and took AP Calculus BC in 8th grade. No comparison group or score table was found — [AEI "Report Card" podcast notes](https://justinmath.com/aei-the-report-card-podcast/)
- Independent user critique: XP can feel like Duolingo-style point chasing, and the system mislabeled first-time material as "review" — [LessWrong first-month experience report](https://www.lesswrong.com/posts/HxtYuHpa3jzrWsrdm/my-first-month-with-math-academy-an-experience-report-from-a); see also [Andy Matuschak's notes on Math Academy](https://notes.andymatuschak.org/Math_Academy)
- No independent peer-reviewed evaluation of FIRe or of Math Academy's outcomes was found (see Gaps).

**Alpha School / "2 Hour Learning"**
- Model: about 2 hours a day of app-based academics (adaptive software), with adults as "guides" rather than teachers, and the rest of the day spent on life-skills workshops. In practice, an observer reports kids on the "two-hour platform" from about 9-9:30am until noon-12:30pm — [Astral Codex Ten review (blogger account)](https://www.astralcodexten.com/i/166959786/the-two-hour-platform)
- VENDOR: Officials claim students land in the top 1-2% nationally — [ProPublica](https://propublica.org/article/alpha-school-texas-vouchers-ai)
- PRESS (internal data reported by the NYT, summarized by CTV and AOL): only 42% of Alpha students met the network's own goal of learning 2x as fast in both math and reading. About half of K-8 students on its private campuses missed the 2x math goal, and about 1 in 5 missed reading targets — [CTV News](https://www.ctvnews.ca/sci-tech/article/what-if-i-told-you-this-school-had-no-teachers-is-ai-schooling-the-future-of-education-or-a-risky-bet/); [AOL](https://www.aol.com/articles/told-school-had-no-teachers-110046449.html)
- Stanford's Victor Lee says Alpha is refusing independent research access. Alpha says it has hired learning scientists to assess outcomes — [CTV News](https://www.ctvnews.ca/sci-tech/article/what-if-i-told-you-this-school-had-no-teachers-is-ai-schooling-the-future-of-education-or-a-risky-bet/)
- Texas campuses entered the state voucher program (Sept 2026) — [Texas Tribune](https://texastribune.org/2026/09/02/alpha-school-texas-vouchers-ai); November 2026 coverage of tuition and learning goals — [Fortune, 2026-11-14](https://fortune.com/2026/11/14/alpha-school-ai-students-tuition-learning-goals) (page could not be fetched; listed only as the latest coverage)

**Khan Academy and Khanmigo**
- INDEPENDENT RCT (NBER w35620, Oreopoulos and Low): a two-year cluster RCT in 18 Tennessee middle schools, with Khanmigo configured to coach rather than answer. Intent-to-treat effect about 0.06-0.08 SD per year. The estimated effect of a full year of active use is about 0.14 SD, similar to Khan practice without AI — [NBER](https://www.nber.org/papers/w35620); [Stanford SCALE summary](https://scale.stanford.edu/ai/repository/one-click-away-ai-tutoring-khanmigo-two-year-school-experiment)
- The binding constraint was engagement. The median student messaged the tutor on only a third of practice days, and in only 17% of the exercise sessions where they made a mistake — [Stanford SCALE](https://scale.stanford.edu/ai/repository/one-click-away-ai-tutoring-khanmigo-two-year-school-experiment); [KQED MindShift: "Students didn't get answers from Khanmigo; they didn't want its questions either"](https://www.kqed.org/mindshift/66662/students-didnt-get-answers-from-khanmigo-they-didnt-want-its-questions-either)
- Khan's own framing: the experimental range for math practice software is 0.05-0.20 SD — [Khan Academy blog](https://blog.khanacademy.org/?p=22104)
- VENDOR A/B test: giving Khanmigo the student's learning history improved next-item correctness by +2.7% to +3.4% — [Khan Academy blog: building a better AI tutor](https://blog.khanacademy.org/?p=21314)
- INDEPENDENT (Stanford, about 200,000 students): mastery-based math practice (Khan) yields benefits, with caveats (Jan 2026) — [Stanford News](https://news.stanford.edu/stories/2026/01/online-mastery-math-practice-software-educational-impact-research)
- Khan measures outcomes by "skills to proficient" (mastered skills as the unit of progress) — [Khan blog](https://blog.khanacademy.org/?p=13201)

**Duolingo (Birdbrain, half-life regression, Max)**
- Half-life regression (Settles and Meeder, ACL 2016) estimates each word's memory half-life as h = 2^(Θ·x) from features of the learner's history. Its prediction error was about half that of the earlier Leitner system. Code is MIT-licensed — [ACL paper](https://preview.aclanthology.org/fix_video/P16-1174.pdf); [GitHub](https://www.github.com/duolingo/halflife-regression); [Duolingo blog](https://blog.duolingo.com/how-we-learn-how-you-learn)
- Birdbrain predicts the probability that a given learner gets a given exercise right, using IRT-inspired logistic regression updated after every exercise, and uses it to pick exercises at the right difficulty — [IEEE Spectrum](https://spectrum.ieee.org/duolingo). The sources do not confirm whether HLR runs inside Birdbrain.
- 2026 academic follow-up: a mixed-effects HLR feeding a random forest, for explainable spaced repetition — [PMLR v339](https://proceedings.mlr.press/v339/ilidio26a.html)
- Efficacy evidence is thin or self-commissioned. The 2012 Vesselinov and Grego study was Duolingo-commissioned with a small sample. A 2024 Duolingo efficacy paper reports reading and listening gains through CEFR A2 (second-hand descriptions) — [analysis page (lower reliability)](https://deepaksood619.github.io/education/competitors/duolingo-analysis)
- The "engagement over learning" critique: the app's main aim is to keep you on it "whether you're learning or not" — [Android Authority](https://androidauthority.com/duolingo-defense-poll-result-3547001); low-effort recall creates an "illusion of mastery" (opinion) — [DEV](https://dev.to/yaptech/duolingos-shallow-learning-trap-gamified-streaks-harmful-habits-4134)
- AI-first backlash: commentary on the stock drop and brand damage (causation not established) — [UX Collective](https://uxdesign.cc/ai-first-did-duolingo-make-a-fatal-mistake-ed610df666d5); heavy AI-feature users spend 11.1 min/day, which may reflect selection rather than effect — [Apptopia](https://apptopia.com/en/insights/ai-threat-to-duolingo-overstated/)

**Carnegie Learning / Cognitive Tutor (knowledge tracing)**
- INDEPENDENT RCT (RAND/ETS, more than 17,000 students, 147 schools, 7 states, Cognitive Tutor Algebra I): no effect in year 1. In year 2, +8 percentile points (about 0.20 SD), which is the basis for the vendor's "nearly doubled" claim — [EdWeek 2013](https://edweek.org/education/study-hybrid-algebra-program-nearly-doubled-math-learning/2013/06)
- Evidence for ESSA rates the HS math solution "strong," but the average effect across 3 studies is +0.03, with +0.21 for the second cohort — [Evidence for ESSA](https://evidenceforessa.org/program/carnegie-learning-high-school-math-solution)
- Implementation fidelity matters. In a 2012 West Virginia evaluation, very few students met recommended usage — [WVDE report](https://new.wvde.us/wp-content/uploads/2018/01/MiddleSchoolAlgebraReadinessInitiative2012.pdf); WWC intervention report — [IES WWC](https://ies.ed.gov/ncee/wwc/Docs/InterventionReports/wwc_cogtutor_083110.pdf)

**Squirrel AI**
- "Nanoscale" knowledge points: courses are split into the smallest conceptual pieces with a knowledge graph. For comparison, a textbook might use about 3,000 points and ALEKS about 1,000. MIT Tech Review flags a test-prep focus and worries about standardization — [MIT Technology Review, 2019](https://www.technologyreview.com/2019/08/02/131198/china-squirrel-has-started-a-grand-experiment-in-ai-education-it-could-reshape-how-the/)
- VENDOR: 7-9% greater learning gains versus human teachers — [OEB Insights](https://oeb.global/oeb-insights/?p=8929); its studies are company-affiliated with no independent replication (lower-reliability source) — [analysis page](https://deepaksood619.github.io/education/competitors/squirrel-ai-analysis)

### Inferences
- The replicable core is cheap: (1) a prerequisite graph, (2) a per-node state (mastery estimate + last review + stability), (3) a high mastery bar, (4) spaced reviews that are made cheaper by counting advanced practice as partial review of prerequisites (the FIRe idea), and (5) a time-based effort unit (XP ≈ minutes of focused work) with penalties for gaming.
- Effect sizes in the wild (0.05-0.2 SD) are much smaller than vendor claims (2-4x). The difference is mostly dosage and motivation: Math Academy's best results come from self-selected, highly motivated learners. A solo motivated student resembles that group, so the gains may be closer to vendor claims for them, but this is unverified.
- The Khanmigo trial shows that an AI tutor bolted onto practice adds little if learners don't invoke it. A personal system should make the AI's intervention proactive (triggered on errors) rather than opt-in.

### Gaps
- No independent peer-reviewed evaluation of Math Academy or FIRe. No published AP score distributions.
- Not researched in this pass (no sourced findings): Brilliant (interactive problem-first lessons; no outcome studies found), Synthesis Tutor (no results surfaced), Duolingo Max (Explain My Answer / Roleplay / Video Call; no efficacy data found).
- Alpha's internal data is reported second-hand through the NYT. The Fortune November 2026 article could not be fetched.
- Newark/Khan three-year longitudinal study results were not found.

## Q2. AI-lab learning products: how they constrain the AI to teach rather than answer, and outcomes

### Takeaway
All three labs constrain behavior mainly with system instructions: Socratic questioning, hints, one step at a time, checks for understanding, and memory-based personalization. Google has additionally fine-tuned a pedagogy model (LearnLM). The only published learning outcomes come from Google-affiliated trials (Eedi UK, Sierra Leone) and from adjacent academic RCTs (Harvard physics, Bastani PNAS). Anthropic's own research documents the failure mode these modes target: 47% of student conversations are direct delegation, and AI-assisted coding lowered comprehension by 17 percentage points.

### Cited Findings
**Anthropic**
- Claude for Education and Learning mode launched in April 2025 (Socratic, "guides discovery rather than answering") — [Anthropic Education Report](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- Usage analysis of about 1M student conversations: 39.3% creating or refining material, 33.5% technical explanations or solutions. CS students were 36.8% of conversations versus 5.4% of degrees. 47% of conversations were "direct" (minimal effort, delegation) — [Anthropic Education Report](https://www.anthropic.com/research/anthropic-education-report-how-university-students-use-claude); [The Decoder](https://the-decoder.com/students-delegate-higher-level-thinking-to-ai-anthropic-study-finds/)
- August 2025: Learning mode extended to all Claude.ai users, and Claude Code got "Explanatory" and "Learning" output styles — [Engadget](https://www.engadget.com/ai/anthropic-brings-claudes-learning-mode-to-regular-users-and-devs-170018471/); [AlternativeTo](https://alternativeto.net/news/2025/8/claude-s-learning-mode-is-now-available-to-all-users-with-new-coding-styles)
- Claude Code Learning style: Claude does routine implementation but inserts `TODO(human)` markers for meaningful pieces the learner must write, and adds "Insight" notes. The Explanatory style adds Insights about design choices and tradeoffs. Styles are set via `/config` → Output style and saved to `.claude/settings.local.json`. Custom output styles are files that modify the system prompt — [Claude Code docs: output styles](https://code.claude.com/docs/en/output-styles); `/output-style` command reportedly removed in v2.1.91 — [horadecodar](https://horadecodar.com.br/pedir-explicacao-claude/)
- INDEPENDENT-ish (Anthropic RCT, Jan 2026, n=52 mostly junior devs learning the Trio library): AI group quiz about 50% versus about 67% for hand-coding (d=0.738, p=0.01). No significant speedup (23 vs 25 min). The largest gap was on debugging. Learners who asked conceptual follow-up questions scored higher. Heavy delegators scored below 40% — [Anthropic research](https://www.anthropic.com/research/AI-assistance-coding-skills); [arXiv 2601.20245](https://arxiv.org/html/2601.20245v1); [InfoQ](https://www.infoq.com/news/2026/02/ai-coding-skill-formation)

**OpenAI ChatGPT Study Mode**
- Launched 2025-07-29 for Free/Plus/Pro/Team. Implemented as custom system instructions written with teachers and learning scientists, not a trained model. Socratic questions, hints, self-reflection prompts, and personalization via memory — [OpenAI](https://openai.com/index/chatgpt-study-mode/); [OpenAI Help](https://help.openai.com/en/articles/11780217-study-mode); [InfoQ](https://www.infoq.com/news/2025/08/study-mode-chatgpt)
- No published learning-outcome study found. One podcast claims it was later "killed," which is unverified and conflicts with other coverage — [Podbean](https://www.podbean.com/media/share/pb-vevns-1974a8b?download=1)

**Google LearnLM / Gemini Guided Learning / NotebookLM**
- LearnLM is fine-tuned for pedagogy. In the tech report, educators preferred it by +31% over GPT-4o, Claude 3.5 Sonnet, and Gemini 1.5 Pro (vendor evaluation) — [LearnLM tech report, arXiv 2412.16429](https://arxiv.org/html/2412.16429)
- Eedi UK exploratory RCT (n=165): LearnLM-supported tutoring made students 5.5 pp more likely to solve novel problems on later topics versus human tutors alone — [arXiv 2512.23633](https://arxiv.org/html/2512.23633v1)
- Sierra Leone pre-registered RCT (n=1,763, grades 7-8, with Fab AI): 12 or more hours of Guided Learning over 8 weeks significantly improved learning. Google's conversion is 1.8-2.5 "years" of progress (vendor conversion; dose-conditional) — [Google LearnLM](https://cloud.google.com/solutions/learnlm)
- Guided Learning launched August 2025. It is more structured and quiz-heavy, and critics call its auto-generated quizzes and flashcards sometimes unhelpful — [Digit](https://www.digit.in/features/general/googles-guided-learning-versus-chatgpts-study-mode-which-is-better.html); [WhyTryAI comparison](https://www.whytryai.com/p/ai-study-modes)

**Adjacent independent RCTs on tutor design**
- Bastani et al., PNAS 2025 (about 1,000 Turkish HS students): unrestricted "GPT Base" raised practice scores 48% but lowered unassisted exam scores 17%. "GPT Tutor" with guardrails raised practice 127% and showed no exam harm (and no clear gain). Tutor users overestimated their own performance — [PNAS via RePEc](https://ideas.repec.org/a/nas/journl/v122y2025pe2422633122.html); [Wharton Knowledge](https://knowledge.wharton.upenn.edu/article/without-guardrails-generative-ai-can-harm-education/)
- Kestin et al., Scientific Reports 2025 (Harvard PS2, n=194, crossover): an AI tutor built on pedagogical best practices (one step at a time, never the full solution) produced median gains more than double those of in-class active learning, in 49 vs 60 minutes. Short-term, two topics, one course — [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC12179260/); [Hechinger](https://hechingerreport.org/proof-points-ai-tutor-harvard-physics/)
- Reviewer comparisons: ChatGPT is the most practice-oriented, Gemini the most structured and quiz-heavy, and Claude works inside Projects with your own docs — [Tom's Guide](https://www.tomsguide.com/ai/i-tested-chatgpt-5-study-mode-vs-claude-learning-mode-with-7-prompts-heres-the-winner); [EdTech Insiders](https://edtechinsiders.substack.com/p/study-modes-the-new-ai-battleground)

### Inferences
- "Study mode" is mostly a prompt. Any solo user can replicate it in Claude with a Project or system prompt or a Claude Code custom output style. The real differentiators are the *structure around* the prompt: curriculum, a mastery state, scheduled retrieval, and well-crafted step-by-step solutions (the Harvard tutor had pre-written expert solutions).
- Bastani's finding of "practice up, exam flat, overconfidence" is the key warning. Performance during AI-assisted practice is not learning. A growth OS must include unassisted retrieval tests as ground truth.
- The Anthropic coding RCT gives a concrete rule: use AI for conceptual questions and explanations, and write or debug code yourself while learning. This matches the `TODO(human)` design.

### Gaps
- No outcome studies for Claude Learning mode or ChatGPT Study Mode.
- The Eedi and Sierra Leone numbers come from summaries; the full papers were not read. NotebookLM learning outcomes were not found.

## Q3. Coding-specific platforms with AI: what works for learning programming in the AI era

### Takeaway
The dominant pattern is a Socratic, scoped AI tutor attached to a structured curriculum with automated tests (CS50 Duck, Boot.dev's Boots). Guardrails leak: the CS50 Duck still emits code blocks up to about a quarter of the time despite instructions. Evidence on durable skill points to separating "learn mode" (human writes code, AI explains) from "produce mode."

### Cited Findings
- CS50.ai / Duck (Harvard): piloted in Summer 2023 with about 70 students, then thousands online and about 500 on campus in Fall 2023. It has "pedagogical guardrails" to guide rather than give solutions. Students said they felt they had "a personal tutor" — [Liu et al., "Teaching CS50 with AI" (SIGCSE 2024)](https://cs.harvard.edu/malan/publications/V1fp0567-liu.pdf)
- Follow-up "Improving AI in CS50" paper and a 2026 Gazette interview: despite explicit instructions, the Duck still responds with code blocks up to about a quarter of the time — [Liu et al. follow-up](https://cs.harvard.edu/malan/publications/fp0627-liu.pdf); [Harvard Gazette, Sept 2026](https://news.harvard.edu/gazette/story/2026/09/taming-the-duck-for-starters/)
- RAG-based course tutors (RAGMan) answered in-scope questions accurately 98% of the time — [arXiv 2407.15718](https://arxiv.org/html/2407.15718v1)
- Boot.dev: a gamified backend curriculum (XP, quests) with "Boots," a Socratic AI that gives hints rather than solutions on the current lesson. Its own warning: AI "can quickly become a crutch" — [Boot.dev about](https://boot.dev/about); [tooldirectory review (July 2026)](https://tooldirectory.ai/tools/boot-dev). An independent 2026 review says it "makes it harder to pretend you learned," but advises adding at least two independent projects — [CourseFacts/DEV review](https://dev.to/royce_fabbd83cb268312e928/bootdev-review-2026-backend-developer-path-pricing-verdict-hk8). Some users find Boots a slower path than reference docs — [Trustpilot](https://www.trustpilot.com/review/www.boot.dev?page=2)
- Anthropic coding-skills RCT (see Q2): AI delegation while learning a new library lowered comprehension by 17 pp, mostly in debugging. Conceptual questioning preserved learning — [Anthropic](https://www.anthropic.com/research/AI-assistance-coding-skills)

### Inferences
- What works: (a) a curriculum with test-graded exercises, (b) an AI scoped to the current exercise with "hint ladders" and no full solutions, (c) human-written code for the target skill, and (d) real projects beyond the platform. For a Claude-based student: use the Learning output style (`TODO(human)`) for skill-building repos, the default style for throwaway or production work, and periodic no-AI debugging drills.
- Prompt-only guardrails are leaky (Duck at about 25%), and a self-directed learner can simply bypass them. Self-binding has to come from routine and deliberate mode choice, not technical enforcement.

### Gaps
- No sourced findings gathered on Exercism (human mentoring plus test-runner), Codecademy AI, Scrimba, Educative, Launch School (mastery-based, no time limit), or Recurse Center (self-directed retreat). Searches returned nothing usable, and no outcome data exists for these in the sources found.

## Q4. Personal growth, coaching, and journaling AI: evidence

### Takeaway
Evidence is weak. Apps such as Rosebud cite general research (expressive writing, conversational-agent meta-analyses) rather than trials of their own product. The nearest rigorous work is an RCT of a different generative-AI wellbeing app (Flourish). User reports include both strong benefit and rumination or reinforcement of negative thoughts.

### Cited Findings
- Rosebud's "science" page cites expressive-writing literature and a 2023 meta-analysis showing conversational AI reduced distress. There is no product RCT. Founders say they worked with licensed therapists — [Rosebud science](https://www.rosebud.app/science); [Fast Company](https://www.fastcompany.com/91167593/rosebud-ai-journaling-app-writing-partner)
- Mixed user reviews: some call it better than therapy, while others say it reinforced negative thoughts or raised stress (anecdotal) — [Trustpilot](https://www.trustpilot.com/review/rosebud.app?page=3); [Bustle review](https://www.bustle.com/wellness/rosebud-therapy-app-review-features-price)
- Flourish ("Sunnie") preregistered RCT: n=486 undergrads, 6 weeks, fall 2024, waitlist control. Effect sizes not captured in this research — [arXiv 2601.11530](https://arxiv.org/pdf/2601.11530)

### Inferences
- For a growth OS, reflection features should be designed as structured prompts tied to goals and learning logs (what did I try, what failed, what's next), with explicit anti-rumination rules, rather than open-ended emotional chat whose effects are unproven.

### Gaps
- No evidence gathered on Reflection.app, AI career coaching, or habit apps. No peer-reviewed RCTs of commercial AI coaching apps were found.

## Q5. Business incentives that distort these products, and lessons for a self-built system

### Takeaway
The recurring distortion is optimizing for proxies such as DAU, streaks, time-in-app, practice-session correctness, and parent-pleasing "2x" metrics, instead of retained, transferable skill. Every rigorous study above shows that the proxy and the true outcome can diverge (practice up, exam down). A self-built system has no engagement incentive and can optimize directly for unassisted retention and transfer.

### Cited Findings
- Duolingo is criticized for engagement-first design (streaks, notifications), staying on the app "whether you're learning or not" — [Android Authority](https://androidauthority.com/duolingo-defense-poll-result-3547001)
- Proxy divergence: GPT Base raised practice +48% while lowering exam −17%. Tutor users were overconfident — [Wharton](https://knowledge.wharton.upenn.edu/article/without-guardrails-generative-ai-can-harm-education/)
- Low voluntary use of the pedagogical tutor: students "didn't want its questions" — [KQED](https://www.kqed.org/mindshift/66662/students-didnt-get-answers-from-khanmigo-they-didnt-want-its-questions-either). Friction-ful pedagogy competes with frictionless general chatbots (implied by 47% direct delegation in Claude data) — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- Opacity: Alpha refuses independent evaluation while marketing top-1-2% outcomes and expanding via vouchers — [CTV](https://www.ctvnews.ca/sci-tech/article/what-if-i-told-you-this-school-had-no-teachers-is-ai-schooling-the-future-of-education-or-a-risky-bet/); [ProPublica](https://propublica.org/article/alpha-school-texas-vouchers-ai)
- Headline versus average effects: Carnegie's "nearly doubled" (year-2 cohort) versus an average of +0.03 across studies — [Evidence for ESSA](https://evidenceforessa.org/program/carnegie-learning-high-school-math-solution)
- Test-score optimization: Squirrel AI is oriented toward standardized test gains — [MIT Tech Review](https://www.technologyreview.com/2019/08/02/131198/china-squirrel-has-started-a-grand-experiment-in-ai-education-it-could-reshape-how-the/)
- Gamification can turn learning into point-chasing even in a mastery system (Math Academy XP critique) — [LessWrong](https://www.lesswrong.com/posts/HxtYuHpa3jzrWsrdm/my-first-month-with-math-academy-an-experience-report-from-a)

### Inferences (design blueprint for a Claude-powered solo "growth OS")
1. **Learner model as a file.** Keep a skills graph (YAML or JSON) with nodes, prerequisites, "encompasses" edges, and per-node state: mastery estimate, last_reviewed, stability or half-life, and evidence links. Claude reads and updates it each session. This is Math Academy, Duolingo, and Khan's "learning history" (+3% next-item correctness) done by hand.
2. **Scheduler.** Use HLR- or FSRS-style half-lives with FIRe-style partial credit, so practicing advanced items refreshes prerequisites and the review load shrinks.
3. **Mastery bar plus unassisted checks.** Advance only after correct, AI-free retrieval spaced over days. Treat AI-assisted performance as non-evidence (Bastani).
4. **Tutor mode constraints.** Use a custom Claude Code output style or Project prompt: one step at a time, never the full solution first, ask a prediction question before explaining, and `TODO(human)` for target skills (Kestin; Anthropic Learning style). Make the tutor intervene on errors rather than waiting to be asked (Khanmigo engagement lesson).
5. **Two explicit modes.** "Learn" mode (human writes code, AI explains conceptually) versus "Ship" mode (delegation allowed). Log which mode each session used. Delegation while learning cost 17 pp of comprehension.
6. **Effort metric, not streaks.** Track XP as focused minutes on items at the edge of competence, penalize gaming, and review weekly against outcomes (retention-test scores, projects shipped), not activity counts.
7. **Honest dashboards.** Report calibration (predicted vs actual quiz score) to counter AI-induced overconfidence.
8. **Reflection with structure.** A short weekly retro tied to goals. Avoid open-ended rumination loops, since evidence for AI journaling is thin.

### Gaps
- No direct evidence on how well a self-built LLM learning system works for a single motivated adult. The blueprint is inferred from institutional products and RCTs on adolescents and undergraduates.
