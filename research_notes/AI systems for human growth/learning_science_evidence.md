# Learning Science and Learning with Generative AI: Evidence for a Claude-powered "Growth OS"

Notes compiled 2026-11-23. Audience: designer of a personal learning system for a 2nd-year CS & Business Systems student.

**Evidence grades used throughout:**
- **[A]** Meta-analysis of experiments, or a large preregistered RCT.
- **[B]** A single RCT or controlled experiment, peer-reviewed.
- **[C]** Observational, correlational, survey or log-analysis work.
- **[P]** Preprint or company tech report, not peer-reviewed. Treat as provisional.
- **[O]** Opinion or commentary.

**How the figures were checked:**
- **(v):** I confirmed the figure this session from a primary or near-primary page or search snippet.
- **(k):** The figure comes from well-established literature I already knew, with the DOI given. I did not re-fetch it this session, so the writer should spot-check it before quoting exact decimals.

---

## Q1. Learning science: which techniques have the strongest evidence, and which popular ideas are weak or myths?

### Takeaway
The strongest techniques for durable learning are retrieval practice and spacing, both with consistent moderate-to-large effects. Next come interleaving of similar, confusable categories, generation and self-explanation, and worked examples that fade into problem-solving as expertise grows. Mastery-based progression and frequent formative feedback also have solid support. Bloom's "2-sigma" tutoring effect is a stylized overstatement: rigorous tutoring RCTs average about 0.3–0.4 SD. Learning styles, rereading and highlighting are weak or myths. Deliberate practice matters, but it explains far less variance in performance than popular accounts claim.

### Cited Findings

**Umbrella review**
- Dunlosky et al. 2013 (Psychological Science in the Public Interest) rated 10 techniques [A-narrative review] (k):
  - **High utility:** practice testing and distributed practice.
  - **Moderate utility:** interleaved practice, elaborative interrogation and self-explanation.
  - **Low utility:** highlighting, rereading, summarization, the keyword mnemonic and imagery for text.
  - [doi:10.1177/1529100612453266](https://doi.org/10.1177/1529100612453266)

**Retrieval practice (testing effect)**
- Adesope, Trevisan & Sundararajan 2017 (Review of Educational Research) [A] (k):
  - Overall g ≈ 0.61 across 272 effect sizes.
  - Testing beat restudy by g ≈ 0.51.
  - The effect held across formats, ages and delays.
  - [doi:10.3102/0034654316689306](https://doi.org/10.3102/0034654316689306)
- Rowland 2014 (Psychological Bulletin) [A] (k):
  - Testing effect g ≈ 0.50.
  - Larger when feedback is given and when retrieval is effortful (recall rather than recognition).
  - [doi:10.1037/a0037559](https://doi.org/10.1037/a0037559)

**Spacing (distributed practice)**
- Cepeda et al. 2006 (Psychological Bulletin) [A] (k): meta-analysis of 317 experiments (839 assessments) showing a robust benefit of spaced over massed practice. [doi:10.1037/0033-2909.132.3.354](https://doi.org/10.1037/0033-2909.132.3.354)
- Cepeda et al. 2008 (Psychological Science) [B, n≈1,350] (k):
  - The optimal gap between study sessions grows with the target retention interval.
  - It is about 10–20% of the retention interval for about a week, falling to about 5–10% for about a year.
  - [doi:10.1111/j.1467-9280.2008.02209.x](https://doi.org/10.1111/j.1467-9280.2008.02209.x)

**FSRS vs SM-2 spaced-repetition algorithms**
- FSRS (Free Spaced Repetition Scheduler, by Jarrett Ye) grew out of a KDD 2022 paper on scheduling reviews with stochastic dynamic programming. It is now built into Anki. [P/C] (v) — [LessWrong history of FSRS](https://www.lesswrong.com/posts/G7fpGCi8r7nCKXsQk/the-history-of-fsrs-for-anki)
- In the open-spaced-repetition community benchmark, FSRS-6 with per-user optimization reaches a mean log loss of about 0.344 and beats SM-2 in about 99.6% of collections [C, community benchmark] (v). — [Benchmark](https://expertium.github.io/Benchmark.html); [secondary summary](https://www.mindomax.com/fsrs-vs-sm2-spaced-repetition-algorithm)
  - **Caveat:** SM-2 was never designed to predict recall probability, so the comparison is somewhat unfair.
- Anki's documentation claims FSRS needs fewer reviews for the same retention (v). — [Anki FAQ](https://docs.ankiweb.net/faqs/what-spaced-repetition-algorithm)
  - This is vendor documentation, not an RCT.
  - SuperMemo's author disputes log loss as the right metric. — [SuperMemo](https://www.supermemo.com/en/wp-json/wp/v2/posts/147652)
- **Bottom line:** FSRS predicts memory better than SM-2. Its effect on learning outcomes in humans has not been tested in RCTs. Neither the spacing effect itself nor the use of a modern scheduler is in doubt.

**Interleaving**
- Brunmair & Richter 2019 (Psychological Bulletin) [A] (v): 59 studies, 238 effect sizes. — [PubMed](https://pubmed.ncbi.nlm.nih.gov/31556629/)
  - Overall interleaving effect g = 0.42.
  - Mathematical tasks: g = 0.34.
  - Paintings and visual categories: larger effects.
  - Word lists: g = −0.39, meaning blocking was better.
  - Interleaving helps most when categories are similar to each other, items within a category are dissimilar, and the material is complex.
- **Implication:** interleave confusable problem types, such as recursion vs iteration, SQL JOIN types, or choosing between sorting algorithms. Do not interleave unrelated topics just for its own sake.

**Generation effect**
- Bertsch et al. 2007 (Memory & Cognition) [A] (k): items learners generate themselves are remembered better than items they read, mean d ≈ 0.40. [doi:10.3758/BF03193441](https://doi.org/10.3758/BF03193441)

**Desirable difficulties and the learning-vs-performance distinction**
- Soderstrom & Bjork 2015 (Perspectives on Psychological Science) [A-review] (k): performance during training is an unreliable index of learning. Conditions that slow acquisition, such as spacing, interleaving and testing, often improve long-term retention and transfer. [doi:10.1177/1745691615569000](https://doi.org/10.1177/1745691615569000)
- Deslauriers et al. 2019 (PNAS) [B, Harvard physics] (k): students in active-learning classes learned more but *felt* they learned less than students in polished lectures. Feelings of fluency mislead learners. [doi:10.1073/pnas.1821936116](https://doi.org/10.1073/pnas.1821936116)
- Freeman et al. 2014 (PNAS) [A] (k): active learning in STEM, 225 studies. [doi:10.1073/pnas.1319030111](https://doi.org/10.1073/pnas.1319030111)
  - Exam scores were about 0.47 SD higher.
  - Failure rates were 21.8% with active learning vs 33.8% with lectures.

**Worked examples, productive failure and the expertise reversal effect**
- **Worked-example effect:** for novices, studying worked examples beats unguided problem-solving. Kirschner, Sweller & Clark 2006 (Educational Psychologist) [A-review] (k) argue against minimal guidance for novices. [doi:10.1207/s15326985ep4102_1](https://doi.org/10.1207/s15326985ep4102_1)
- **Expertise reversal effect:** Kalyuga et al. 2003 (Educational Psychologist) [A-review] (k). Guidance that helps novices becomes redundant and even harmful as expertise grows, so guidance should fade (completion problems, then full problems). [doi:10.1207/S15326985EP3801_4](https://doi.org/10.1207/S15326985EP3801_4)
- **Productive failure:** Sinha & Kapur 2021 (Review of Educational Research) [A] (k). Problem-solving *before* instruction beat instruction-first for conceptual knowledge, g ≈ 0.36, and more when the design was implemented with high fidelity. It did not help procedural knowledge. [doi:10.3102/00346543211019105](https://doi.org/10.3102/00346543211019105)
- **Reconciling these:** let the learner attempt first ("struggle, then teach") when building concepts. Use worked examples for brand-new procedures. Fade support with demonstrated competence.

**Cognitive load theory**
- Sweller's cognitive load theory is the theoretical basis for the worked-example, split-attention, redundancy and expertise-reversal effects (k).
  - **Critique:** "germane load" is poorly operationalized, and load measures are mostly self-report [O/C].
  - **Practical use:** for novices, minimize extraneous load, meaning one new concept at a time and integrated code-plus-explanation.

**Deliberate practice**
- Macnamara, Hambrick & Oswald 2014 (Psychological Science) [A] (v). — [PubMed](https://pubmed.ncbi.nlm.nih.gov/24986855/)
  - Deliberate practice explained about 12% of variance in performance (r ≈ .35).
  - By domain: games 26%, music 21%, sports 18%, education 4%, professions under 1%.
- Critics argue the 2014 inclusion criteria were too broad. A reanalysis estimated 29–61% after attenuation correction (v). — [Frontiers 2019](https://frontiersin.org/article/10.3389/fpsyg.2019.02396/full)
- **Consensus:** deliberate practice is necessary but not sufficient. Its core ingredients are still the best-supported design for skill building: a specific goal at the edge of current ability, immediate feedback, and repetition with refinement.

**Mastery learning**
- Kulik, Kulik & Bangert-Drowns 1990 (Review of Educational Research) [A] (k): mastery learning programs averaged an effect size of about 0.52. Effects were larger for weaker students and on teacher-made tests. [doi:10.3102/00346543060002265](https://doi.org/10.3102/00346543060002265)

**Bloom's 2-sigma problem**
- Bloom (1984) claimed one-to-one mastery tutoring produces +2 SD.
- Von Hippel (Education Next, 2024) [O, well-sourced] (v): the 2-sigma curve was hand-drawn and stylized, not fit to data. — [Education Next](https://www.educationnext.org/two-sigma-tutoring-separating-science-fiction-from-science-fact/)
  - In Cohen, Kulik & Kulik 1982, only 1 of 65 tutoring studies found about 2 SD, and that one tutored 32 students.
- Nickow, Oreopoulos & Quan (NBER 2020) [A] (v): 96 tutoring RCTs pooled to about 0.37 SD, and none reached 2 SD. — [NBER](https://www.nber.org/papers/w27476.pdf)
- Kraft, Schueler & Falken 2024 [A, 265+ RCTs] (v): effects shrink substantially at scale. — [EdWorkingPaper 24-1031](https://edworkingpapers.com/sites/default/files/ai24-1031.pdf)
- **Use for AI claims:** a realistic upper bound for a very good tutor is about 0.3–0.4 SD. Claims that AI "solves the 2-sigma problem" should be read sceptically.

**Metacognition and illusions of competence**
- Fluency from rereading, or from seeing a solution, creates overconfidence. Testing yourself corrects it [A, Dunlosky 2013; Deslauriers 2019 above].
- Novices are systematically miscalibrated. This becomes central once AI enters (see Q2/Q3).

**Sleep**
- Newbury et al. 2021 (Psychological Bulletin) [A] (k, verify decimals): [doi:10.1037/bul0000348](https://doi.org/10.1037/bul0000348)
  - Sleep deprivation *before* learning impairs memory encoding, g ≈ 0.62.
  - Deprivation *after* learning impairs consolidation, g ≈ 0.28.
- **Design use:** avoid late-night cramming, place reviews after sleep, and protect sleep before hard learning days.

**Weak ideas and myths**
- **Learning styles (meshing hypothesis):** Pashler et al. 2008 (PSPI) [A-review] (k) found virtually no well-designed studies supporting matching instruction to a learner's style. [doi:10.1111/j.1539-6053.2009.01038.x](https://doi.org/10.1111/j.1539-6053.2009.01038.x)
- **Rereading and highlighting:** low utility [Dunlosky 2013].
- **"10,000 hours rule":** overstated [Macnamara 2014].
- **Growth-mindset interventions:** effects are small. Sisk et al. 2018 (Psychological Science) [A] (k) found mean d ≈ 0.08 on achievement. [doi:10.1177/0956797617739704](https://doi.org/10.1177/0956797617739704)
  - Larger only for at-risk subgroups, e.g. Yeager et al. 2019 (Nature).
- **"Google effect" / digital amnesia (Sparrow et al. 2011):** the key result failed to replicate in Camerer et al. 2018 (Nature Human Behaviour) (k). [doi:10.1038/s41562-018-0399-z](https://doi.org/10.1038/s41562-018-0399-z)

### Inferences
- **Core loop of the Growth OS:** attempt first, then get feedback, then do spaced retrieval of key concepts (FSRS-scheduled), with interleaved mixed practice across confusable problem types.
- **Scaffolding:** support should fade with demonstrated mastery, driven by a learner model of mastery, not by time spent.
- **Show learning, not fluency:** the OS should show delayed retrieval and transfer performance rather than in-session performance, because learners and AI-assisted sessions both mistake fluency for learning.

### Gaps
- I found no RCT comparing FSRS with SM-2 on learning outcomes in humans; evidence is predictive accuracy only.
- I found no robust meta-analysis specific to retrieval practice or interleaving *for programming skill*. The evidence comes mostly from general STEM and verbal learning.
- Decimals marked (k) were not re-fetched this session.

---

## Q2. What happens when people learn with generative AI or AI tutors, and what conditions make AI help or harm?

### Takeaway
AI reliably raises *performance while the AI is present*. Whether it raises *learning*, meaning unaided performance later, depends on design and use:
- **Pedagogically constrained tutors** (hints, Socratic prompting, no full answers, built on curriculum, often with human oversight) produce real gains of about 0.3–0.6 SD in RCTs.
- **Unconstrained answer engines**, and use that substitutes AI output for the learner's own work, produce null or negative learning effects (−17% in Bastani; −17 points and d ≈ 0.74 in Anthropic's coding RCT). They also inflate how competent learners feel.
- **The gap widens:** students with more prior knowledge and stronger metacognition benefit; weaker novices are more at risk.

### Cited Findings

**Bastani et al. 2025 (PNAS 122(26), e2422633122) [B, field RCT, ~1,000 Turkish high-school students]** (v) — [PNAS via IDEAS](https://ideas.repec.org/a/nas/journl/v122y2025pe2422633122.html); [SSRN](https://papers.ssrn.com/abstract=4895486); [Wharton](https://knowledge.wharton.upenn.edu/article/without-guardrails-generative-ai-can-harm-education/)
- **Conditions:**
  - "GPT Base": a ChatGPT-like interface.
  - "GPT Tutor": teacher-designed prompts that give hints and do not reveal answers.
- **Results:**
  - During practice, GPT Base students scored 48% higher than controls.
  - On the AI-free exam, GPT Base students scored 17% *worse* than controls.
  - GPT Tutor greatly improved practice performance; the commonly reported figure is about +127%, which I did not re-verify. Its negative effect on the exam was "largely mitigated" (no significant harm vs control).
- **Mechanism:** students used GPT Base as a crutch, asking for answers. Students also overestimated how much they had learned.

**Kestin et al. 2025 (Scientific Reports 15:17458) [B, RCT crossover, n=194, Harvard physical sciences course]** (v) — [PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC12179260/); [Harvard Gazette](https://news.harvard.edu/gazette/story/2024/09/professor-tailored-ai-tutor-to-physics-course-engagement-doubled/)
- **Comparison:** an AI tutor (GPT-4 with carefully engineered prompts encoding pedagogical best practices) vs an in-class *active learning* lesson.
- **Results:**
  - Median learning gains in the AI group were more than double.
  - Linear-regression effect size was 0.63 SD, which the authors call an underestimate due to a ceiling effect.
  - Students reported more engagement and motivation, and took less time.
- **Key design features:**
  - The tutor scaffolded step by step and did not hand over full solutions.
  - It was grounded in instructor-written answers to reduce errors.
  - It managed cognitive load and promoted a growth mindset.
- **Caveats:** single lesson units, immediate post-test, and an elite sample.

**World Bank, Edo State, Nigeria: De Simone et al. 2025 (Policy Research Working Paper 11125) [B, RCT, working paper]** (v) — [World Bank OKR](https://openknowledge.worldbank.org/entities/publication/15e1ff08-15ae-4f7a-b2a8-d146e6c113ee/full); [WB blog](https://blogs.worldbank.org/en/education/From-chalkboards-to-chatbots-Transforming-learning-in-Nigeria)
- **Design:** 6-week after-school program; secondary students used Microsoft Copilot (GPT-4) with teacher facilitation; about 13 hours total on average.
- **Results:**
  - +0.31 SD overall; +0.23 SD in English, the main outcome.
  - Framed as about 1.5–2 years of typical learning.
  - The full-year projection of 1.2–2.2 SD is *model-based*, not measured.
- **Caveat:** teacher mediation was integral to the program.

**LearnLM / Eedi, UK (Google DeepMind) [P, exploratory RCT, n=165, 5 schools, May–June 2025]** (v) — [arXiv 2512.23633](https://arxiv.org/abs/2512.23633v1)
- Supervised LearnLM tutoring raised the probability of solving a *novel* problem correctly by 5.5 percentage points over human tutors.
- Supervising tutors approved 76.4% of AI messages with little or no edits.
- A 2026 follow-up of about 1,179 students in 10 schools [P] (v) found AI or human tutoring led to correct follow-up answers 56–58% of the time vs 43% after standard remediation. Adding personal-history context did not clearly help. — [The 74](https://www.the74million.org/article/five-things-you-should-know-about-new-ai-tutor-study/); [Google LearnLM report](https://services.google.com/fh/files/misc/learnlm_oct26.pdf)

**Tutor CoPilot (Stanford): Wang et al. [B/P, RCT, ~900 tutors, ~1,800 students]** (v; sample figures vary by source) — [Stanford NSSA](https://nssa.stanford.edu/studies/tutor-copilot-human-ai-approach-scaling-real-time-expertise)
- The AI helped human tutors, rather than tutoring students directly.
- Students were +4 percentage points more likely to master topics, and +9 points with lower-rated tutors.
- Cost was about $20 per tutor per year.

**Anthropic, "How AI Impacts Skill Formation": Shen & Tamkin, Jan 2026 [P, RCT, n=52 junior software engineers]** (v) — [Anthropic research](https://www.anthropic.com/research/AI-assistance-coding-skills); [arXiv 2601.20245](https://www.arxiv.org/pdf/2601.20245)
- **Task:** learn the unfamiliar Trio async Python library in a 35-minute coding task, with or without a sidebar AI assistant.
- **Results:**
  - AI-free quiz afterwards: AI group 50% vs hand-coders 67% (p=0.01, Cohen's d=0.738).
  - The biggest gap was on debugging questions.
  - Speed gain was about 2 minutes and not significant (p=0.39).
- **Use patterns (qualitative, not causal):**

  | Pattern | n | Mean quiz score |
  |---|---|---|
  | Full AI delegation | 4 | 39% |
  | Progressive reliance | 4 | 35% |
  | AI-as-debugger | 4 | 24% |
  | Generate-then-ask-comprehension-questions | 2 | 86% |
  | Code plus explanation | 3 | 68% |
  | Conceptual questions only, fix errors yourself | 7 | 65% |

- The authors note that cognitive effort, "even getting painfully stuck," is likely important for mastery.
- They recommend learning modes such as Claude Code's Learning/Explanatory output styles.
- **Limitations:** small n, immediate test only.

**Lehmann, Cornelius & Sting, "AI Meets the Classroom: When Do LLMs Harm Learning?" (arXiv 2409.09047 v2, Mar 2025) [P + field data; two preregistered, incentivized lab experiments on programming]** (v) — [arXiv](https://arxiv.org/abs/2409.09047)
- There was no net effect on learning overall.
- **Substitution** (generating solutions to exercises) covered more topics but gave less understanding per topic.
- **Complementing** (asking for explanations) raised understanding.
- LLMs widened the gap between students with low and high prior knowledge.
- Students' self-perceived benefits exceeded the actual benefits.

**Prather et al. 2024, "The Widening Gap" (ICER 2024) [C, qualitative lab study, n=21 novices, eye-tracking and interviews]** (v) — [arXiv 2405.17739](https://arxiv.org/abs/2405.17739)
- Students who already had a plan used AI to speed up and ignored bad suggestions.
- Struggling students had their existing metacognitive difficulties *compounded* and gained new ones. Several finished with an "illusion of competence."

**Kazemitabaar et al. 2023 (CHI) [B, n=69 novices aged 10–17, Codex]** (k) — [doi:10.1145/3544548.3580919](https://doi.org/10.1145/3544548.3580919)
- AI access raised code-authoring completion and scores.
- It did *not* reduce performance on later manual tasks.
- Learners with more prior knowledge benefited more.
- This is a counter-example to uniform harm: structured tasks plus some later manual work kept learning intact.

**CS50 Duck (Harvard): Liu et al., SIGCSE 2024 / SIGCSE TS 2025 [C, deployment reports]** (v) — [SIGCSE 2024 paper](https://cs.harvard.edu/malan/publications/V1fp0567-liu.pdf); [Harvard Gazette 2026](https://news.harvard.edu/gazette/story/2026/09/taming-the-duck-for-starters/)
- **Design:** "pedagogical guardrails," meaning guide rather than give solutions. Deployed to about 70, then thousands online, then about 500 on-campus students.
- **Uptake:** high (later paper reports about 75% frequent use and 94% finding it helpful). These are satisfaction measures, not learning outcomes.
- **Guardrail leakage:** Malan reported in 2026 that the Duck still returns code blocks up to about a quarter of the time despite instructions not to.

**Fan et al., "Beware of Metacognitive Laziness" (BJET, online Dec 2024/2025) [B, n=117, 4-arm randomized]** (v) — [arXiv 2412.09315](https://arxiv.org/abs/2412.09315v1); [Hechinger](https://hechingerreport.org/proof-points-offload-critical-thinking-ai)
- **Arms:** ChatGPT, human coach, checklist, or no support.
- The ChatGPT group improved essay scores most.
- It showed no greater knowledge gain or transfer and no motivation gain.
- It spent less time on self-evaluation and planning, which the authors call "metacognitive laziness."

**MIT Media Lab, "Your Brain on ChatGPT": Kosmyna et al., June 2025 [P, n=54, only 18 in the crossover session; EEG]** (v) — [arXiv 2506.08872](https://arxiv.org/abs/2506.08872); [Scientific American critique](https://www.scientificamerican.com/article/does-using-chatgpt-really-change-your-brain-activity/)
- **Groups:** LLM, search engine, or brain-only, writing essays.
- **Results:**
  - The LLM group showed the weakest neural connectivity.
  - It reported the least ownership of the essays.
  - It had poor ability to quote its own essays.
  - LLM-to-brain switchers showed under-engagement.
  - Brain-to-LLM switchers showed *higher* recall and activation.
- **How to read it:** small, not peer-reviewed, task-specific. "Cognitive debt" is an interpretation; the author herself rejects "brain rot" readings.
- **Suggestive design point:** think first, then use AI (the brain-to-LLM order) looked better than starting with AI.

**Anthropic Education Report: How university students use Claude (Apr 2025) [C, log analysis of 574,740 academic conversations]** (v) — [Anthropic](https://www.anthropic.com/news/anthropic-education-report-how-university-students-use-claude)
- About 47% of student conversations were "Direct" (seeking answers with minimal engagement) vs "Collaborative."
- Computer Science accounted for 38.6% of conversations, the largest share.
- Students mostly delegated higher-order Bloom's-taxonomy tasks (Creating about 40%, Analyzing about 30%), which raises offloading concerns.
- A companion report covers educators (Aug 2025). — [Anthropic educators report](https://www.anthropic.com/research/anthropic-education-report-how-educators-use-claude)

**Meta-analyses of ChatGPT and learning (2025–2026)**
- Wang & Fan 2025 (Humanities & Social Sciences Communications, Palgrave) [A, but low-quality primary studies] (v): 51 studies, Nov 2022–Feb 2025. — [IDEAS](https://ideas.repec.org/a/pal/palcom/v12y2025i1d10.1057_s41599-025-04787-y.html)
  - Learning performance g = 0.867.
  - Learning perception g = 0.456.
  - Higher-order thinking g = 0.457.
- Doo & Park 2026 (IRRODL) [A] (v): 22 studies, achievement g = 0.573. — [IRRODL](https://www.irrodl.org/index.php/irrodl/article/view/8775)
- Deng et al. 2025 (Computers & Education) [A] (v): 69 studies, 2022–2024, with acknowledged methodological shortcomings in the primary studies. — via [Research Square preprint critique](https://assets-eu.researchsquare.com/files/rs-7577394/v1/15335396298c3f818f0fbef8.html)
- **Critical caveat for these meta-analyses:** most primary studies measure performance *with* AI or immediately after, use short durations and non-blinded designs, and are prone to publication bias. These pooled effect sizes are far larger than the best tutoring RCTs (about 0.3–0.4 SD), which strongly suggests inflation. Weight the individual RCTs above much more heavily.

**Product moves (context, not evidence) [O]**
- Anthropic: Claude for Education "Learning mode" (2025) and Claude Code Learning/Explanatory output styles.
- OpenAI: ChatGPT Study Mode (July 2025).
- Google: LearnLM.
- All encode Socratic, attempt-first behaviour. Evidence on these products themselves is limited to the studies above.

### Inferences
- **Conditions under which AI helps:**
  - It is tutor-constrained: hints before answers, Socratic questioning, and the learner must attempt first.
  - Content is grounded in vetted solutions.
  - The learner uses it to *explain and question*, not to *produce* the work.
  - Some human or structural accountability exists (teacher, AI-off assessments).
  - The learner already has a plan or prior knowledge.
- **Conditions under which AI harms:**
  - Unconstrained answer generation.
  - Using AI as a debugger in place of reasoning.
  - Progressive delegation over a session.
  - Novices with weak metacognition.
  - Only in-session performance is measured.
- **For a CS student specifically:** the Anthropic Trio and Lehmann programming results are the most directly relevant. Debugging skill is most at risk, and the "conceptual inquiry" and "generate-then-interrogate" patterns are the ones to encourage.

### Gaps
- There are almost no long-term (semester-plus) RCTs measuring durable, AI-free skill after generative-AI tutoring.
- I found no peer-reviewed RCT of a Claude-based tutor specifically.
- I did not re-verify the Bastani GPT Tutor practice gain figure (+127%).
- Primary-source effect sizes for the Tutor CoPilot sample vary between sources.

---

## Q3. Cognitive offloading, illusions of competence, skill atrophy and over-reliance: what is the evidence, and which mitigations work?

### Takeaway
Correlational and lab evidence consistently links heavy, unreflective AI use to less critical engagement, metacognitive laziness and overconfidence. Causal evidence of *learning* loss exists in short RCTs (Bastani; Anthropic). Evidence of long-term *deskilling* is emerging but mostly observational. Mitigations with experimental support:
- Constrain the AI to hints and Socratic dialogue (Bastani GPT Tutor, Kestin).
- Require an attempt before help, and keep the learner generating.
- Prompt comprehension questions after any generated code.
- Assess regularly with AI switched off.
- Keep the learner's self-confidence and verification habits high.

### Cited Findings
- Lee et al. 2025 (CHI; Microsoft Research and CMU) [C, survey of 319 knowledge workers, 936 real task examples] (v): — [Microsoft Research](https://www.microsoft.com/en-us/research/?p=1135061); [PDF](https://advait.org/files/lee_2025_ai_critical_thinking_survey.pdf)
  - Higher confidence in GenAI went with *less* self-reported critical thinking.
  - Higher self-confidence went with *more* critical thinking.
  - Critical thinking shifts toward verifying, integrating and stewarding AI output.
  - Correlational only, as the authors stress.
- Gerlich 2025 (Societies 15(1):6) [C, n=666 survey plus 50 interviews] (v): — [IDEAS](https://ideas.repec.org/a/gam/jsoctx/v15y2025i1p6-d1559787.html)
  - Frequent AI use correlated negatively with critical-thinking scores, mediated by cognitive offloading.
  - Younger participants were more dependent.
  - A correction was issued in Sept 2025.
  - Correlational, self-report.
- **Illusion of competence:**
  - Bastani: students overestimated their learning.
  - Lehmann et al.: perceived benefits exceed actual benefits.
  - Prather et al.: struggling novices left with false confidence.
  - Fan et al.: reduced self-evaluation.
  - (All v, see Q2.)
- **Deskilling outside education:** Budzyń et al. 2025 (Lancet Gastroenterology & Hepatology) [C, observational, multicentre Poland] (k, verify). Endoscopists' adenoma detection rate in *non-AI* colonoscopies fell from about 28% to about 22% after routine exposure to AI assistance. This is the first clinical signal of AI-induced deskilling. [doi:10.1016/S2468-1253(25)00133-5](https://doi.org/10.1016/S2468-1253(25)00133-5)
- **Classic automation-complacency literature:** Parasuraman & Manzey 2010 (Human Factors) [A-review] (k). Reliable automation breeds complacency and loss of the skills needed for manual takeover. [doi:10.1177/0018720810376055](https://doi.org/10.1177/0018720810376055)
- **Offloading is not inherently bad:** Risko & Gilbert 2016 (Trends in Cognitive Sciences) [A-review] (k). Offloading frees capacity, but what is offloaded is not stored, and people offload based on miscalibrated confidence. [doi:10.1016/j.tics.2016.07.002](https://doi.org/10.1016/j.tics.2016.07.002)

**Mitigation evidence**
- **Guardrailed tutor prompts:** Bastani GPT Tutor "largely mitigated" harm [B] (v). The Kestin scaffolded tutor beat active learning [B] (v).
- **Attempt or think first:** MIT crossover found brain-to-LLM better than LLM-to-brain [P] (v). Productive-failure meta-analysis [A] (k).
- **Ask for explanations, not solutions:** Lehmann et al. [P] (v). Anthropic conceptual-inquiry and generate-then-comprehend patterns [P, qualitative] (v).
- **Guardrail leakage is real:** the CS50 Duck leaked code up to about 25% of the time (v). Prompt-only guardrails need enforcement in the interface, such as output filters, hint ladders and locked solutions.
- **AI-off assessment:** every study showing harm discovered it *only* through AI-free tests. Without them, harm is invisible [inference from Bastani and Anthropic].
- **Human or structural oversight:** the Nigeria program (teacher-facilitated) [B] (v), LearnLM (tutor-supervised) [P] (v) and Tutor CoPilot [B/P] (v) all paired AI with humans.

### Inferences
- **Build in by default:**
  1. Attempt-first gating: submit an attempt or plan before hints.
  2. A hint ladder: conceptual nudge, then targeted hint, then partial example, then full solution, the last only after an attempt and followed by a mandatory explain-back.
  3. A "comprehension check" after any AI-generated code.
  4. Weekly AI-off retrieval quizzes and coding katas, especially debugging, tracked as the true mastery metric.
  5. A calibration display: predicted vs actual score, to counter illusions of competence.
  6. Separate "learn mode" (Socratic) from "do mode" (productivity), with the student choosing explicitly.
- **Debugging deserves extra protection:** have the learner form a hypothesis before AI suggests fixes.

### Gaps
- I found no longitudinal RCTs on skill atrophy among programmers using AI.
- The endoscopy deskilling numbers were not re-fetched this session.
- No direct experimental evidence compares individual mitigation components, such as hint ladders vs Socratic-only.

---

## Q4. What does research say about motivation, habit formation, self-determination theory and feedback for sustained self-directed learning?

### Takeaway
Sustained self-directed learning is best supported by:
- **Autonomy-supportive design** (self-determination theory: autonomy, competence, relatedness).
- **Specific implementation intentions** ("if-then" plans).
- **Stable context cues** for habits, which take weeks to months to form.
- **Task-focused, actionable feedback** rather than praise or ego-focused feedback.

Feedback is powerful but variable: about a third of feedback interventions *reduce* performance. Mindset interventions have small effects.

### Cited Findings
- **Feedback:**
  - Kluger & DeNisi 1996 (Psychological Bulletin) [A] (k): mean d ≈ 0.41, but about one-third of feedback interventions *decreased* performance, especially feedback that directed attention to the self rather than the task. [doi:10.1037/0033-2909.119.2.254](https://doi.org/10.1037/0033-2909.119.2.254)
  - Wisniewski, Zierer & Hattie 2020 (Frontiers in Psychology) [A] (k): 435 studies, d ≈ 0.48. High-information feedback (task, process and self-regulation levels) was most effective. [doi:10.3389/fpsyg.2019.03087](https://doi.org/10.3389/fpsyg.2019.03087)
  - Hattie & Timperley 2007 (Review of Educational Research) [A-review] (k): the model of feed-up ("where am I going?"), feed-back ("how am I going?") and feed-forward ("where to next?"). [doi:10.3102/003465430298487](https://doi.org/10.3102/003465430298487)
- **Habit formation:** Lally et al. 2010 (European Journal of Social Psychology) [C, n=96, 12 weeks] (k). Automaticity took a median of 66 days (range 18–254). Missing a single day did not derail habit formation. [doi:10.1002/ejsp.674](https://doi.org/10.1002/ejsp.674)
- **Implementation intentions:** Gollwitzer & Sheeran 2006 (Advances in Experimental Social Psychology) [A, 94 studies] (k). Goal attainment improved with d ≈ 0.65. [doi:10.1016/S0065-2601(06)38002-1](https://doi.org/10.1016/S0065-2601(06)38002-1)
- **Self-determination theory:**
  - Ryan & Deci 2000 (American Psychologist) [theory, A-supported] (k): autonomy, competence and relatedness predict intrinsic and autonomous motivation. [doi:10.1037/0003-066X.55.1.68](https://doi.org/10.1037/0003-066X.55.1.68)
  - Howard et al. 2021 (Perspectives on Psychological Science) [A, 344 samples] (k): intrinsic and identified motivation predicted persistence, performance and well-being; external regulation did not. [doi:10.1177/1745691620966789](https://doi.org/10.1177/1745691620966789)
  - Gamification with points or badges as controlling rewards risks undermining intrinsic motivation. Deci, Koestner & Ryan 1999 (Psychological Bulletin) [A] (k) found expected tangible rewards undermined intrinsic motivation, d ≈ −0.34. [doi:10.1037/0033-2909.125.6.627](https://doi.org/10.1037/0033-2909.125.6.627)
- **Mindset:** small average effects (Sisk 2018, see Q1).
- **AI and motivation:**
  - Kestin et al. found higher engagement and motivation with the scaffolded AI tutor [B] (v).
  - Fan et al. found no motivation gain from ChatGPT [B] (v).
  - Lee et al.: self-confidence (a competence belief) predicts critical engagement with AI [C] (v).

### Inferences
- **Autonomy:** let the student set goals and choose projects, linked to career identity (CS plus business systems), which builds identified motivation.
- **Competence:** show visible mastery progress based on AI-off evidence.
- **Relatedness:** connect the learner to peers, mentors or study groups. AI alone may not satisfy relatedness.
- **Habits:** prompt if-then plans ("after dinner at my desk, 25-minute review"). Expect about 2 months to automaticity. Design streaks to be forgiving, since a missed day is harmless.
- **Feedback from Claude:** keep it task-, process- and self-regulation-focused ("your loop invariant breaks at i=n; how would you check that?"), never person-focused ("you're smart"). Always include a feed-forward next step.

### Gaps
- I found no RCTs on long-term persistence (months) with AI study companions specifically.
- Decimals marked (k) in this section were not re-fetched this session.
