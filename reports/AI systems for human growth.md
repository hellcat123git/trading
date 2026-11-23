# Measure Unaided Skill, Not AI-Assisted Performance

The most consistent finding across controlled trials, commercial products, open-source tools and practitioner reports is that AI reliably improves how well you perform *while it is switched on*, and only under specific conditions improves what you can do *once it is switched off*. In a field RCT of about 1,000 students, unconstrained ChatGPT access raised practice scores 48% but cut AI-free exam scores 17%. In Anthropic's own coding trial, AI users scored 50% on a follow-up quiz against 67% for people who coded by hand, and the biggest gap was in debugging. By contrast, tutors that make the learner attempt first, give hints rather than answers, and are grounded in vetted solutions produced gains of roughly 0.3–0.6 SD. In real deployments the limiting factors are engagement and honest measurement, not clever algorithms. Khanmigo's two-year RCT delivered about 0.06–0.08 SD per year because students rarely called on it. The big claims from Alpha School and Math Academy, and the idea that AI "solves Bloom's 2-sigma problem", are either unverified or contradicted by data. In 2026, open-source builders independently settled on one pattern: the LLM teaches, and deterministic code decides. That means a separate blind grader, a scheduler built on FSRS (a modern spaced-repetition algorithm), on-disk records of every grade, and hooks for nudges. For a beginner CSBS (Computer Science & Business Systems) student who cannot yet tell whether Claude is right, the earlier growth-OS design points the right way but has too many parts and too little checking. AI-off assessment and an external verification layer must become its centre. The seven-agent team should shrink to three roles. The second brain must serve recall testing rather than replace it. The first version should take one weekend to build. No one has yet measured whether a personal Claude growth system builds lasting skill, so this one has to measure itself.

## AI lifts performance on the spot and drains learning unless it is constrained

### The core science is old and robust, and AI does not change it

The well-established findings of learning science are the yardstick for every AI system. **Retrieval practice** (testing yourself) has an overall effect of g ≈ 0.61 across 272 effect sizes, and testing beat restudying by about 0.51 ([Adesope et al. 2017](https://doi.org/10.3102/0034654316689306)). **Spacing** has a robust benefit across 317 experiments ([Cepeda et al. 2006](https://doi.org/10.1037/0033-2909.132.3.354)). Interleaving, which means mixing problem types within a session, averages g = 0.42. But it *hurts* for word lists (g = −0.39) and helps most when the categories are easy to confuse ([Brunmair & Richter 2019](https://pubmed.ncbi.nlm.nih.gov/31556629/)). So the student should mix recursion with iteration, or the different SQL JOIN types, rather than mixing unrelated subjects. **Generating** an answer yourself beats reading it, d ≈ 0.40 ([Bertsch et al. 2007](https://doi.org/10.3758/BF03193441)). **Mastery learning** averages about 0.52 SD, with bigger effects for weaker students ([Kulik et al. 1990](https://doi.org/10.3102/00346543060002265)).

Two findings matter especially for a beginner. First, novices learn new procedures better from **worked examples** than from unguided problem-solving ([Kirschner, Sweller & Clark 2006](https://doi.org/10.1207/s15326985ep4102_1)). That support becomes harmful as expertise grows, so it should fade ([Kalyuga et al. 2003](https://doi.org/10.1207/S15326985EP3801_4)). Second, **productive failure** works for concepts but not for procedures. Struggling with a problem before instruction raised conceptual knowledge by g ≈ 0.36, with no benefit for procedural knowledge ([Sinha & Kapur 2021](https://doi.org/10.3102/00346543211019105)).

The ideas at the weak end are the ones popular productivity culture tends to sell. Matching teaching to "learning styles" has almost no support ([Pashler et al. 2008](https://doi.org/10.1111/j.1539-6053.2009.01038.x)). Growth-mindset interventions average d ≈ 0.08 ([Sisk et al. 2018](https://doi.org/10.1177/0956797617739704)). Deliberate practice explained only about 12% of performance variance overall, and about 4% in education ([Macnamara et al. 2014](https://pubmed.ncbi.nlm.nih.gov/24986855/)). A reanalysis puts it at 29–61% after correcting for measurement error ([Frontiers 2019](https://frontiersin.org/article/10.3389/fpsyg.2019.02396/full)), so its ingredients still matter: a specific goal at the edge of your ability, immediate feedback, and refinement.

The concept that ties all of this to AI is the **learning–performance distinction**. How well you do during training is an unreliable sign of learning. Conditions that slow you down now, such as spacing, interleaving and testing, often improve retention later ([Soderstrom & Bjork 2015](https://doi.org/10.1177/1745691615569000)). Harvard physics students in active-learning classes learned more but *felt* they had learned less ([Deslauriers et al. 2019](https://doi.org/10.1073/pnas.1821936116)). AI is the most powerful fluency machine ever built. That makes it the most powerful generator of illusions of competence too, unless the system deliberately puts difficulty back in.

### The realistic ceiling is about 0.3–0.4 SD, not two sigma

Many AI-tutor pitches promise to deliver Bloom's "2-sigma" tutoring effect (a two-standard-deviation gain). The original curve was hand-drawn and stylized. Only 1 of 65 tutoring studies in the underlying review found about 2 SD ([von Hippel, Education Next](https://www.educationnext.org/two-sigma-tutoring-separating-science-fiction-from-science-fact/)). Pooling 96 tutoring RCTs gives about **0.37 SD, and none reached 2 SD** ([Nickow, Oreopoulos & Quan, NBER](https://www.nber.org/papers/w27476.pdf)), and effects shrink further at scale ([Kraft et al. 2024](https://edworkingpapers.com/sites/default/files/ai24-1031.pdf)).

Recent meta-analyses report ChatGPT effects of g = 0.867 ([Wang & Fan 2025](https://ideas.repec.org/a/pal/palcom/v12y2025i1d10.1057_s41599-025-04787-y.html)) and g = 0.573 ([Doo & Park 2026](https://www.irrodl.org/index.php/irrodl/article/view/8775)). Those figures should be read as inflated. Most of the primary studies measure performance with the AI present or immediately afterwards, run for short periods, and are not blinded. A personal growth OS that aims for honest, durable gains of a few tenths of an SD per subject, compounded across years and courses, is aiming at something real. One that promises 2x or 10x is selling.

### How you use AI matters more than whether you use it

The well-designed trials agree on what makes the difference. In Bastani et al., students with an unrestricted "GPT Base" interface scored 48% higher in practice and 17% *lower* on the AI-free exam. A "GPT Tutor" version, with teacher-designed hints and no answers revealed, largely removed that harm, but it produced no clear exam gain ([PNAS via IDEAS](https://ideas.repec.org/a/nas/journl/v122y2025pe2422633122.html); [Wharton](https://knowledge.wharton.upenn.edu/article/without-guardrails-generative-ai-can-harm-education/)). Harvard's physics tutor was built to scaffold one step at a time, never hand over the full solution, and draw on instructor-written answers. It more than doubled median gains compared with an active-learning class, an effect of 0.63 SD ([Kestin et al. 2025](https://pmc.ncbi.nlm.nih.gov/articles/PMC12179260/)), though that was on single lessons with an immediate post-test.

Two other trials paired AI with human oversight. A teacher-facilitated Copilot program in Nigeria produced +0.31 SD in six weeks ([World Bank](https://openknowledge.worldbank.org/entities/publication/15e1ff08-15ae-4f7a-b2a8-d146e6c113ee/full)). Supervised LearnLM tutoring raised the chance of solving a *novel* problem by 5.5 percentage points over human tutors ([arXiv 2512.23633](https://arxiv.org/abs/2512.23633v1)). Every positive result came with constraint, grounding, human oversight, or a combination.

For a CS student, the most relevant evidence is Anthropic's skill-formation RCT. Fifty-two junior engineers learned the unfamiliar Trio async library, half with an AI assistant. The AI users finished only about 2 minutes faster, which was not significant. They then scored **50% vs 67%** on an AI-free quiz (d = 0.738), with the largest gap on debugging questions ([Anthropic](https://www.anthropic.com/research/AI-assistance-coding-skills); [arXiv 2601.20245](https://www.arxiv.org/pdf/2601.20245)). The interaction patterns are associational and come from tiny groups, but they are the most practical evidence available:

| Usage pattern (Anthropic Trio RCT) | Mean quiz score | Design implication |
|---|---|---|
| Full AI delegation | 39% | Block in learn mode |
| Progressive reliance (questions drift into handing over the task) | 35% | Detect drift within a session |
| AI-as-debugger (paste error, accept fix) | 24% | Require a hypothesis first |
| Conceptual questions only, fix own errors | 65% | Default learn-mode behaviour |
| Code plus explanation | 68% | Acceptable for unfamiliar APIs |
| Generate, then ask comprehension questions | 86% | Default ship-mode behaviour |

Two lab experiments on programming found the same thing. Using an LLM to *generate* solutions covered more topics but produced less understanding of each, while using it for *explanations* improved understanding ([Lehmann et al.](https://arxiv.org/abs/2409.09047)). One counter-example deserves weight. Novices aged 10–17 who used Codex in a structured curriculum that included later manual work showed no loss on subsequent unaided tasks ([Kazemitabaar et al. 2023](https://doi.org/10.1145/3544548.3580919)). AI is not harmful in itself; using it as a substitute for your own work is.

### A student who can't judge Claude's output is the one most at risk

The student's stated difficulty, not being able to tell whether Claude's output is right, is not a side issue. It is how the harm happens. Eye-tracking and interview work with novices found that students who already had a plan used AI to go faster and ignored bad suggestions. Struggling students had their metacognitive difficulties *compounded*, and several left with an illusion of competence ([Prather et al. 2024](https://arxiv.org/abs/2405.17739)). LLMs widened the gap between students with low and high prior knowledge, and students' perceived benefit exceeded the real benefit ([Lehmann et al.](https://arxiv.org/abs/2409.09047)). A survey of 319 knowledge workers found that **more confidence in the AI went with less critical thinking, and more self-confidence went with more** ([Lee et al. 2025, Microsoft Research/CMU](https://www.microsoft.com/en-us/research/?p=1135061)). In a randomized study, ChatGPT users improved their essays most but showed no greater knowledge gain or transfer. They also spent less time evaluating their own work, a pattern the authors called "metacognitive laziness" ([Fan et al.](https://arxiv.org/abs/2412.09315v1)).

The design consequence is direct. A beginner cannot be the system's quality check, so the system has to move that judgment outside the student until the student can do it. Test suites are the arbiter of correctness. A blind grader is the arbiter of understanding. A calibration log, comparing predicted with actual scores, is the arbiter of self-assessment. Verifying AI output then becomes a skill track in its own right. It is also the job-market skill: commentators expect juniors who lean on AI before building fundamentals to lose skills, while experienced engineers gain because they can review the output ([Osmani](https://addyosmani.com/blog/agentic-engineering/)).

## Engagement and honest metrics decide outcomes more than algorithms do

### The best platforms share a cheap core, and independent effects are small

Math Academy, Duolingo, Khan Academy, Carnegie Learning and Squirrel AI converge on one architecture:

- a fine-grained prerequisite graph;
- a per-learner estimate for each node, either a mastery probability or a memory half-life;
- a high bar for mastery before moving on;
- scheduled spaced review.

Math Academy's FIRe (Fractional Implicit Repetition) adds a smart refinement. Practising an advanced topic counts as partial, discounted review of the prerequisites it contains, which shrinks the total review load ([Skycak](https://www.justinmath.com/individualized-spaced-repetition-in-hierarchical-knowledge-structures)). Duolingo's half-life regression roughly halved prediction error compared with the older Leitner box system ([Settles & Meeder, ACL 2016](https://preview.aclanthology.org/fix_video/P16-1174.pdf)). The community FSRS-6 benchmark beats SM-2, Anki's older algorithm, in about 99.6% of collections ([benchmark](https://expertium.github.io/Benchmark.html)). FSRS predicts memory better; nobody has tested in an RCT whether it improves human learning outcomes.

Independent evaluations of software of this kind are sobering. Khan's own framing puts the experimental range for math practice software at **0.05–0.20 SD** ([Khan Academy blog](https://blog.khanacademy.org/?p=22104)). Carnegie's Cognitive Tutor showed no effect in its first year and about 0.20 SD in the second ([EdWeek](https://edweek.org/education/study-hybrid-algebra-program-nearly-doubled-math-learning/2013/06)), averaging +0.03 across the studies Evidence for ESSA reviewed ([Evidence for ESSA](https://evidenceforessa.org/program/carnegie-learning-high-school-math-solution)).

The most instructive result is Khanmigo's two-year cluster RCT. With the AI set to coach rather than answer, the intent-to-treat effect was about 0.06–0.08 SD per year, no better than Khan practice without AI ([NBER w35620](https://www.nber.org/papers/w35620)). The reason was engagement. The median student messaged the tutor on only a third of practice days, and in **only 17% of exercise sessions where they made a mistake** ([Stanford SCALE](https://scale.stanford.edu/ai/repository/one-click-away-ai-tutoring-khanmigo-two-year-school-experiment)). A KQED headline summed it up: students "didn't get answers from Khanmigo; they didn't want its questions either" ([KQED](https://www.kqed.org/mindshift/66662/students-didnt-get-answers-from-khanmigo-they-didnt-want-its-questions-either)).

This is the central tension for a self-directed learner. A tutor that teaches well creates friction, and friction loses to a frictionless general chatbot sitting in the next tab. Anthropic found that 47% of student conversations with Claude were "direct" delegation ([Anthropic Education Report](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)).

### Separating hype from evidence

| Claim | Who says it | What the evidence shows |
|---|---|---|
| AI tutors deliver Bloom's 2-sigma | Many AI-ed pitches; human-skill-tree README frames Bastani as "48–127%" gains ([repo](https://github.com/24kchengYe/human-skill-tree)) | Best tutoring RCTs average ~0.37 SD ([NBER](https://www.nber.org/papers/w27476.pdf)). In Bastani, the unguarded condition *hurt* exam scores ([Wharton](https://knowledge.wharton.upenn.edu/article/without-guardrails-generative-ai-can-harm-education/)) |
| Alpha School: "2x learning," "top 1–2%" | Vendor ([ProPublica](https://propublica.org/article/alpha-school-texas-vouchers-ai)) | Internal data reported by the NYT: only 42% of students met the 2x goal in both math and reading; independent research access refused ([CTV News](https://www.ctvnews.ca/sci-tech/article/what-if-i-told-you-this-school-had-no-teachers-is-ai-schooling-the-future-of-education-or-a-risky-bet/)) |
| Math Academy: "3–4x as fast as a normal class" | Founder ([AEI podcast notes](https://justinmath.com/aei-the-report-card-podcast/)) | No comparison group or independent evaluation found; strong mechanism, self-selected users |
| "Study modes" are a new pedagogy | OpenAI, Anthropic | ChatGPT Study Mode is custom system instructions, not a trained model ([OpenAI](https://openai.com/index/chatgpt-study-mode/)); no outcome studies for Study Mode or Claude Learning mode |
| Prompt guardrails stop answer-giving | Implied by tutor products | CS50's Duck still returns code blocks up to about a quarter of the time ([Harvard Gazette](https://news.harvard.edu/gazette/story/2026/09/taming-the-duck-for-starters/)) |
| ChatGPT meta-analyses: g ≈ 0.87 | [Wang & Fan 2025](https://ideas.repec.org/a/pal/palcom/v12y2025i1d10.1057_s41599-025-04787-y.html) | Primary studies mostly measure with AI present, short and unblinded; inflated |
| "Your brain on ChatGPT" proves brain rot | Press coverage | n = 54 (18 in the crossover), not peer reviewed; the author rejects "brain rot" readings ([Scientific American](https://www.scientificamerican.com/article/does-using-chatgpt-really-change-your-brain-activity/)) |

The pattern behind the hype is that metrics get substituted. Products optimize what is easy to measure and pleasant to report: daily active users, streaks, practice correctness, "2x" parent-facing claims. Every rigorous study shows that these can move opposite to retained skill. A self-built system has no engagement incentive, which is a real advantage. It also gives up the external accountability present in every successful trial: teachers in Nigeria, supervisors in LearnLM, and tutors coached by AI in Stanford's Tutor CoPilot, which raised topic mastery by 4–9 percentage points at about $20 per tutor per year ([Stanford NSSA](https://nssa.stanford.edu/studies/tutor-copilot-human-ai-approach-scaling-real-time-expertise)). A solo system has to replace that accountability with scheduled AI-off checks and some human contact.

### Motivation research favours autonomy, if-then plans and forgiving habits over gamification

Lasting self-directed learning depends on autonomy, competence and relatedness. Intrinsic motivation, and motivation the learner identifies with, predicted persistence and performance across 344 samples; pressure from outside did not ([Howard et al. 2021](https://doi.org/10.1177/1745691620966789)). Expected tangible rewards undermined intrinsic motivation, d ≈ −0.34 ([Deci, Koestner & Ryan 1999](https://doi.org/10.1037/0033-2909.125.6.627)). That is why point-chasing critiques follow both Duolingo ([Android Authority](https://androidauthority.com/duolingo-defense-poll-result-3547001)) and even Math Academy's XP system ([LessWrong](https://www.lesswrong.com/posts/HxtYuHpa3jzrWsrdm/my-first-month-with-math-academy-an-experience-report-from-a)).

Implementation intentions, specific "if X, then I do Y" plans, improve goal attainment with d ≈ 0.65 ([Gollwitzer & Sheeran 2006](https://doi.org/10.1016/S0065-2601(06)38002-1)). Habits took a median of 66 days to become automatic, and missing a single day did not derail them ([Lally et al. 2010](https://doi.org/10.1002/ejsp.674)).

Feedback is powerful but risky. It averages d ≈ 0.41, yet about **a third of feedback interventions reduced performance**, especially feedback aimed at the person rather than the task ([Kluger & DeNisi 1996](https://doi.org/10.1037/0033-2909.119.2.254)). AI journaling and coaching apps have no product RCTs. Rosebud cites general research ([Rosebud](https://www.rosebud.app/science)), and users report both benefit and rumination ([Trustpilot](https://www.trustpilot.com/review/rosebud.app?page=3)). Sleep is the cheapest lever. Sleep deprivation before learning impairs encoding with g ≈ 0.62 ([Newbury et al. 2021](https://doi.org/10.1037/bul0000348)).

## Open-source builders converged on "the LLM teaches, code decides"

### A reference architecture emerged in 2026

In 2026 a genre of Claude Code plugins appeared that reverses the usual flow: the human predicts, designs or explains, and Claude asks questions and holds back answers. The most complete is **Engram**. Its README says it "is not an agent-memory plugin... it's a learning system for the human." It runs four separate roles. A Curriculum Architect builds a prerequisite concept map that flags threshold concepts. A Tutor runs predict, then productive struggle with hints, then resolution, then explain-back. An Assessor grades blind, against only the rubric and your verbatim answer, and writes a receipt to disk for every grade ("no receipts, no mastery claim"). Deterministic Python fits FSRS-4.5 forgetting curves, and a quiet SessionStart hook reports something like "6 reviews due · ~4 min" ([Engram](https://github.com/nagisanzenin/engram)).

**tutor-mcp** states the principle outright, "Generative teaching. Deterministic pedagogy." It runs Bayesian Knowledge Tracing plus FSRS plus prerequisite rules over MCP, and it separates "estimated knowledge, retained learning and demonstrated skills" ([tutor-mcp](https://github.com/ArnaudGuiovanna/tutor-mcp)). claude-tutor uses PreToolUse hooks so that the learner data's schema cannot be corrupted ([claude-tutor](https://github.com/kirilxd/claude-tutor)). DrCatHicks' learning-opportunities, written by a learning-science researcher, offers an optional 10–15 minute exercise after architectural commits ([learning-opportunities](https://github.com/DrCatHicks/learning-opportunities)). Mathua treats a correct but slow answer as "weak mastery", and it generates problems from parameterised code rather than an LLM so that content cannot be hallucinated ([mathua](https://github.com/chuma-beep/mathua)).

Claude Code itself now ships a **Learning output style**. It leaves `TODO(human)` markers wherever there is a real design decision and asks the learner to write that piece ([Claude Code docs](https://code.claude.com/docs/en/output-styles)).

The insight here is why role separation matters. An LLM grading its own lesson has seen the explanation, the hints and the learner's struggle, and it will generously fill in understanding that isn't there. A grader that sees only the rubric and the answer is the cheapest guard against inflated mastery available. This is the most important architectural idea in the ecosystem, and it fits the student's verification problem exactly.

One more data point argues against over-engineering. Smart-Study-Agent framed scheduling as a reinforcement-learning problem and honestly reports experiments in which "the heuristic won" ([Smart-Study-Agent](https://github.com/HumphreySun98/Smart-Study-Agent)). Sophistication in *what to study next* did not beat simple rules. Faded scaffolding, which learning science strongly supports, shows up in only a few projects. Claude-Code-Quest moves from full commands to hints to the goal alone ([Claude-Code-Quest](https://github.com/wesammustafa/Claude-Code-Quest)). cc-self-train moves through Guide, Collaborator, Peer and Launcher personas ([cc-self-train](https://github.com/zainnab-sparq/cc-self-train)).

### Second brains make the agent smarter, not the human

The most crowded and most star-inflated category is the Obsidian-plus-Claude "second brain" or "life OS". Examples are claude-obsidian following Karpathy's LLM Wiki pattern ([claude-obsidian](https://github.com/AgriciDaniel/claude-obsidian)), LifeOS's current-state-to-ideal-state harness ([LifeOS](https://github.com/danielmiessler/LifeOS)), and agent-memory layers like claude-mem. claude-mem has 119k stars, and its installer now pushes a trial that asks for a payment method ([claude-mem](https://github.com/thedotmack/claude-mem)).

These tools solve capture and retrieval well. Things worth borrowing from them are plain Markdown plus git, Maps of Content, health checks, hooks that enforce structure on every write ([arscontexta](https://github.com/agenticnotetaking/arscontexta)), and read-only verifier agents ([COG](https://github.com/huytieu/COG-second-brain)). But they record what *the agent* knows about you, not what *you* can do. book-to-skill turns a book into a skill the agent can load, which makes the book available to Claude rather than learned by the student ([book-to-skill](https://github.com/virgiliojr94/book-to-skill)). A vault that only accumulates notes and never tests recall is the "collector's fallacy" with a language model attached. Star counts on repos created in 2026 in this category should be treated with suspicion.

### Practitioners independently arrived at two modes, explicit endpoints and reviewed content

Practitioners reached the same conclusions as the trials, apparently independently. Recurse Center alumni described a "learning mode" with no LLM code generation and a "shipping mode" that relies on models. They warned that "smoothing over all the difficulty of learning something probably isn't desirable" ([Recurse Center](https://recurse.com/blog/191-developing-our-position-on-ai)). Stanford's CS336 ships a CLAUDE.md that makes the agent a tutor, with an allowed list (explain, review, ask guiding questions) and a forbidden list (no full functions or classes) ([CS336 guide](https://www.qwe.edu.pl/tutorial/cs336-stanford-agents-md-guide/)). Practitioners warn that tutor mode is "just friction with no payoff" for deadline work, that models sometimes drop CLAUDE.md rules, and that the file should stay lean because it costs context on every run ([claudecodehq](https://claudecodehq.com/playbooks/learning-mode-coding)).

Reviewers of Claude's Learning mode complain that it gives "no clear stopping point for the lesson" ([Yahoo Tech](https://tech.yahoo.com/ai/articles/claude-learning-modes-chatgpt-study-161847670.html)). LLM-generated Anki cards often cram too much into one card and need human review ([smoothbrain](https://smoothbrain.bearblog.dev/my-workflow-for-using-llms-to-create-anki-cards)). Perceived productivity is unreliable too. In METR's study, developers were reported to be 19% slower with AI while believing they were about 20% faster (secondary report, [AgentPatterns.ai](https://agentpatterns.ai/human/skill-atrophy/)).

### What nobody has built yet

The gaps in the ecosystem are where a personal system can add real value. No project unifies one learner model across coding, coursework, business and career; each tool keeps its own silo. Almost none evaluate outcomes. The only study is cc-self-train's self-reported 27-person pilot, and it measured self-efficacy rather than skill. Calibration tracking, comparing confidence with correctness, appears only in learn-codebase's list of "what you confidently know vs. what you're still bluffing" ([learn-codebase](https://github.com/ktaletsk/learn-codebase)). Nothing links mastered concepts to shipped projects. Business-skill learning is nearly absent. Most systems nudge you only when you happen to open Claude Code, so nothing runs on a schedule outside the session.

The job market raises the stakes on exactly these gaps. Entry-level roles were reportedly about 4.5% of US software postings in Q1 2026 (secondary, citing Indeed: [Solvebar](https://solvebar.com/blog/entry-level-software-jobs-2026-junior-developers)). The causal evidence conflicts, and an IZA paper found Copilot-adopting firms *more* likely to hire entry-level engineers ([danilchenko.dev](https://www.danilchenko.dev/posts/junior-developer-jobs-2026/)). What separates candidates in either story is shipped projects, debugging ability and judgment about AI output. Data specific to India, the relevant market for a CSBS student, was not found.

## The earlier design survives, but verification moves to the centre and the agent team shrinks

The design proposed earlier in the conversation holds up better than most of the ecosystem: it already included AI-off assessment and a persistent learner model. The research nonetheless changes its emphasis, cuts its size and adds pieces it lacked.

| Earlier component | Verdict | Evidence | What changes |
|---|---|---|---|
| North Star / skill tree | **Confirmed, refined** | Prerequisite graphs underlie every effective platform; MCII goal-setting ([learning-goal](https://github.com/DrCatHicks/learning-goal)); implementation intentions d ≈ 0.65 | Make it a prerequisite DAG with threshold concepts flagged, mastery set by AI-off evidence, and goals written as if-then plans. "Skill tree" repos that are just curated lists don't count |
| Persistent learner model | **Confirmed, refined** | Engram receipts; tutor-mcp's estimated/retained/demonstrated split; Khan learning history +2.7–3.4% next-item correctness ([Khan blog](https://blog.khanacademy.org/?p=21314)) | Keep it **separate from agent memory**. Every mastery claim needs a receipt; add calibration fields |
| Planner | **Refined** | "Deterministic pedagogy"; "the heuristic won" | Scheduling is code (py-fsrs), not LLM judgment. The LLM proposes weekly priorities; code decides reviews |
| Agent team of 7 (tutor, examiner, reviewer, builder, mentor, challenger, coach) | **Partly contradicted** | Evidence supports *one* separation: teacher vs blind grader. Sprawling 40+-skill systems cost more attention than they return | Collapse to three roles: Tutor, blind Assessor, Coach. Builder/reviewer become **ship mode** of the main session; challenger becomes a bug-hunt drill skill; mentor should be a **human** |
| Practice drills | **Confirmed, sharpened** | Retrieval g ≈ 0.61; interleaving works for confusable types only; FSRS on LeetCode-style problems ([Leetcode-Mastery-Scheduler](https://github.com/search?q=fsrs&type=repositories)) | Interleave confusable problem types; schedule *problems* as well as concepts; add debugging drills, the skill most at risk |
| Project ladder | **Confirmed, refined** | Worked examples for novices, expertise reversal, productive failure for concepts | Each rung records its scaffolding level and AI mode, and support fades rung by rung |
| AI-off assessment | **Strongly confirmed; now the core** | Every study that found harm found it *only* through AI-free tests (Bastani, Anthropic) | Weekly and non-negotiable; the *only* evidence that counts toward mastery |
| Reflection loops | **Refined** | Feedback harms a third of the time when aimed at the person; AI journaling evidence thin; "metacognitive laziness" | Short, structured, task-focused weekly retro tied to receipts; anti-rumination rules; no open-ended emotional chat |
| Second brain | **Demoted** | Vault systems make the agent smarter, not the human; collector's fallacy | Notes exist to feed retrieval cards and public write-ups; anything never tested is just archive |
| Public portfolio | **Confirmed, upgraded** | Junior market rewards shipped proof and debugging ability | Tie portfolio entries to mastered nodes (transfer evidence), which no existing tool does |
| Network | **Confirmed on theory, thin direct evidence** | SDT relatedness; every positive AI trial had humans in the loop | A human mentor or study group stands in for the "mentor agent" |
| CLAUDE.md, subagents, skills, hooks, MCP, scheduled tasks | **Confirmed, re-weighted** | Hooks are the decisive primitive (nudges, schema guards, post-commit offers); CLAUDE.md rules leak | Keep CLAUDE.md under about 40 lines. Hooks and code carry enforcement. MCP is optional (Anki MCP later). Scheduled tasks fill the "outside the session" gap |

The earlier design also missed things the evidence treats as essential. There were no explicit **learn and ship modes**, the most widely discovered practice in the field. There was no **attempt-first gate and hint ladder**. There was no **calibration** tracking to catch illusions of competence. Debugging, the skill the Trio RCT shows eroding fastest, had no special protection. Study material was not **grounded** in course PDFs with page citations and abstention ([universal-examprep-skill](https://github.com/ZeKaiNie/universal-examprep-skill)). Sessions had no **explicit endpoints**. There was no rule against gamifying with streaks, and no attention to sleep. And there was no plan for the system to **evaluate itself**, which matters because no outside study will do it for this student.

## A three-role, file-based growth OS run on a daily loop

### Design principles drawn from the evidence

Seven principles follow from the research, in order of importance.

First, **only unaided, delayed performance counts as evidence of learning**. AI-assisted work is logged as activity, never as mastery.

Second, **the LLM teaches and code decides**: scheduling, mastery thresholds and progression live in scripts and files the student can inspect.

Third, **judgment is moved outside the student until it can move back in**. Tests, a blind grader and a calibration log stand in for the expert eye the student doesn't yet have. A verification skill track then trains that eye on purpose.

Fourth, **mode is explicit**. Learn mode means the human writes the target code and Claude explains, questions and reviews. Ship mode means delegation is allowed, but every diff must be explained back before it is merged.

Fifth, **attempt first, then a hint ladder**: a conceptual nudge, then a targeted hint, then a partial example, then the full solution only after a committed attempt and followed by a required explain-back.

Sixth, **enforcement belongs in structure, not prose**. Prompt guardrails leak about a quarter of the time, so the student's own commit, the test runner and hooks act as the gates.

Seventh, **optimize for adherence and honesty, not for features**. The Khanmigo result says a brilliant tutor that is seldom used produces nothing.

### Architecture: three roles, one learner model, deterministic code

The OS lives in its own folder or repo (`growth/`). The `trading` repo becomes the main *project-ladder* evidence base and is not mixed with learner state.

```
growth/
├── CLAUDE.md                  # ≤40 lines: who I am, modes, hint ladder, "never grade yourself"
├── .claude/
│   ├── settings.json          # outputStyle per mode; hooks; deny-list for private folders
│   ├── agents/assessor.md     # blind grader: sees rubric + verbatim answer only; read-only tools
│   ├── agents/coach.md        # weekly: reads receipts + calibration, proposes next week's plan
│   └── skills/                # /learn  /quiz  /review  /kata  /bughunt  /explain-diff  /retro
├── learner/
│   ├── skills.yaml            # prerequisite DAG: node, prereqs, threshold flag, scaffold level
│   ├── state.json             # per node: FSRS stability/difficulty, last AI-off result, mode history
│   ├── receipts/              # one file per graded attempt: question, verbatim answer, rubric, grade
│   └── calibration.csv        # date, node, predicted %, actual %, AI-off? (y/n)
├── cards/                     # atomic retrieval prompts (student-approved), concept + problem cards
├── scripts/fsrs_due.py        # py-fsrs: computes due items; FIRe-style partial credit later
├── sources/                   # course PDFs/slides for grounded study with page citations
├── log/                       # daily session logs (tried / failed / next), weekly retros
└── public/                    # TIL drafts and project write-ups → portfolio
```

| Role or component | Claude Code primitive | What it does | Evidence basis |
|---|---|---|---|
| **Tutor** (main session, learn mode) | Learning output style + `/learn` skill | Attempt-first, hint ladder, `TODO(human)`, explain-back, exit quiz | Kestin; Bastani GPT Tutor; Anthropic high-scoring patterns |
| **Builder** (main session, ship mode) | Default style + `/explain-diff` skill | Delegation allowed; student must predict behaviour, write or approve tests, explain the diff | Generate-then-comprehend scored 86%; Recurse shipping mode |
| **Assessor** | Subagent, read-only, no lesson context | Grades free recall and katas against a rubric; writes receipts | Engram blind assessor; self-grading inflates mastery |
| **Coach** | Subagent + weekly scheduled task | Reads receipts/calibration, runs MCII planning and a structured retro, proposes plan | Implementation intentions; Hattie feed-forward ([Hattie & Timperley](https://doi.org/10.3102/003465430298487)) |
| **Scheduler** | Python script, not an agent | FSRS due list for concepts *and* problems | FSRS benchmark; "the heuristic won" |
| **Nudges and guards** | SessionStart hook; PreToolUse guard on `learner/`; post-commit hook | Print due reviews and today's node; block edits to state except via scripts; offer a learning exercise after architectural commits | Engram, claude-tutor, learning-opportunities |
| **Outside-session cadence** | Scheduled tasks | Sunday kata and retro reminder; monthly re-plan | Fills the ecosystem's "only when you open Claude" gap |
| **Humans** | Not software | Study group, senior or professor check-ins, PR reviews from strangers | Relatedness; every successful trial kept humans in the loop |

### How a beginner gets around not being able to judge Claude

The verification problem gets its own ladder, and the student climbs it over months. On **rung one**, Claude writes no code for target skills. The student writes everything, Claude reviews by asking questions, and pre-written tests, from course assignments or test files Claude generates and the student reads line by line, decide correctness. On **rung two**, the student must **predict the output** of any code before running it, whether Claude wrote it or not, and record the prediction. Prediction accuracy becomes a tracked metric. On **rung three**, in ship mode, the student writes the tests *before* asking Claude for an implementation. The tests are a specification the student understands, and the test runner, not Claude's confidence, settles the question. On **rung four**, the `/bughunt` skill has Claude plant one or two bugs in otherwise working code, and the student must find them unaided.

This turns the earlier "challenger" agent into deliberate practice of the exact skill the Trio RCT shows eroding. The planted-bug drill is my inference from that evidence; no study has tested it. Whenever study content comes from course material, it carries page citations, and Claude abstains on out-of-scope questions, following the examprep pattern. That lets the student check claims against the source instead of trusting fluent prose.

### What a day and a week look like

| When | Time | Activity | Mode and rules |
|---|---|---|---|
| Morning, after sleep | 10 min | `/review`: FSRS-due concept and problem cards, free recall, graded by Assessor; predict score first | AI-off answers; receipts written |
| Main study block | 45–60 min | `/learn` on the current skill node (e.g. DBMS joins, DSA recursion): attempt, then hint ladder, then explain-back, then a 3-question exit quiz | Learn mode; worked example only for brand-new procedures |
| Project block | 30–60 min | Next rung of the trading project ladder; commit offers a 10-minute learning exercise | Learn mode for target skills, ship mode for the rest with `/explain-diff` |
| Close | 5 min | `/log`: what I tried, what failed, what's next; predicted score for tomorrow's review; session explicitly ends | No open-ended chat; endpoint is the log |
| Sunday | 60–75 min | `/kata` AI-off (one debugging task + one problem, timed), calibration update, `/retro` with Coach, MCII plan for next week, one public TIL | The only mastery-moving evidence of the week |
| Monthly | 60 min | Re-plan `skills.yaml` against courses and the North Star; portfolio milestone; one human review session | Coach proposes, student decides (autonomy) |

These durations follow from the habit and dosage evidence rather than from any trial of this exact schedule. Effective AI programs worked at about 12–13 hours over 6–8 weeks ([World Bank](https://openknowledge.worldbank.org/entities/publication/15e1ff08-15ae-4f7a-b2a8-d146e6c113ee/full); [Google LearnLM](https://cloud.google.com/solutions/learnlm)). Habits need about two months, and a missed day is harmless. The schedule is built to be sustainable, and there is deliberately no streak counter. Reviews belong after sleep, not in late-night cramming.

The dashboard the Coach reads each week shows **AI-off delayed accuracy per node**, the **calibration gap** (predicted minus actual), **unaided debugging time**, **review adherence**, **projects shipped with an explain-the-diff record**, and the **share of learn-mode sessions that drifted into delegation**. It does not count hours, streaks or messages. All of these are proxies that the products above show moving opposite to skill.

### A project ladder that uses the student's interest in finance

The trading interest is an asset for motivation. Under self-determination theory, projects tied to the learner's identity support the motivation that predicts persistence. It also maps neatly onto CSBS coursework. The rungs below are my design, not evidence-tested, and they assume paper data only, with no real money.

| Rung | Project | Course skills exercised | AI mode | Evidence that counts |
|---|---|---|---|---|
| 1 | CLI portfolio tracker reading a CSV of holdings | Python basics, data structures, file I/O | Learn: student writes all code | Passing tests; AI-off kata on same concepts |
| 2 | Price-history store with SQL queries (returns, drawdown) | DBMS: schema design, JOINs, aggregation | Learn with `TODO(human)` on queries and schema | Student-written queries; interleaved JOIN drills |
| 3 | Moving-average backtester with test suite written first | DSA, testing, business statistics | Student writes tests; Claude may suggest implementation hints only | Tests authored by student; bug-hunt on the backtester |
| 4 | Web dashboard over the backtester | Web basics, APIs, systems design | Ship mode allowed; `/explain-diff` mandatory | Diff explanations; human code review |
| 5 | Public write-up evaluating a strategy honestly (costs, overfitting, limits) | Finance, communication, critical evaluation | Ship for prose polish only | Published post; peer or mentor feedback |

### The minimal version to start this week

The biggest risk now is over-building the system instead of learning. The research notes flag this as plausible but undocumented, and a beginner who asks Claude to build complex infrastructure will produce code they can't verify, which is the failure mode the whole design exists to prevent. So the minimal version **borrows before it builds**.

On day one, the student switches Claude Code to the Learning output style for study sessions. They install one existing learner-side plugin: Engram if the focus is concept review, or learning-opportunities if the focus is learning while coding. They write a CLAUDE.md of about 30 lines that defines learn mode, ship mode, the hint ladder and the rule "never grade my answers; send them to the assessor."

During the first week, they create `skills.yaml` with roughly 15 nodes covering one current course plus Python fundamentals. They add a blind `assessor` subagent and a `/quiz` skill that writes receipts, and `calibration.csv`. If Engram isn't used, they add a short py-fsrs script behind a SessionStart hook that prints what is due and stays silent otherwise. The week ends with one Sunday AI-off kata and a structured retro.

Everything else waits until four weeks of data show a specific failure that the component would fix. That includes the Coach subagent, scheduled tasks, bug-hunt drills, an Anki MCP server, FIRe-style partial credit, portfolio automation and a vault. For example, add scheduled tasks if reviews are being skipped, or `/bughunt` if kata debugging times stay flat.

The test of the whole system after a semester is simple. Did AI-off delayed scores and debugging times improve, did the calibration gap shrink, and do shipped projects exist that the student can explain line by line without Claude? If not, the system is producing activity rather than growth, and it should be simplified rather than extended.

## Conclusion

The research turns the usual framing upside down. The scarce ingredient in an AI growth system is not intelligence in the tutor. It is evidence about the learner. Frontier models already explain well enough to help, and the trials that went wrong, went wrong because nobody measured unaided skill until the exam. For a beginner who cannot yet judge Claude's output, the system's most valuable output is honest feedback, not explanations: a blind grade, a failed test, a gap between predicted and actual scores. And the skill it most needs to grow is the one AI erodes fastest and employers value most, which is debugging and verifying code you didn't write.

Three implications follow that neither the products nor the open-source tools have fully absorbed. First, a personal system's real edge over commercial ones is that it can optimize for retained skill instead of engagement, but only if it gives up the comfort of activity metrics. Second, the best use of a "challenger" AI is not debate but deliberately planting flaws for the human to catch, which turns AI's main weakness for learners into a training device. Third, because no study has evaluated a self-directed Claude growth OS over a semester or longer, the student is effectively running an n-of-1 experiment, and the system should be built to settle that experiment with data rather than feelings.
