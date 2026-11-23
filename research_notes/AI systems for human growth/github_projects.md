# Open-source GitHub projects that use LLMs (esp. Claude / Claude Code) to grow human skill

Method: GitHub search API (~40 queries, sorted by stars), plus repository metadata pulled 2026-11-23 and README reads for about 40 repos. Star counts and last-push dates are a snapshot from 2026-11-23. "Active" means pushed in the last ~30 days, "maintained" means pushed in the last ~4 months, "stale" means no push for more than 6 months. Base URL for every repo: https://github.com/OWNER/REPO.

Caveat: many repos below were created in 2026 and have large star counts after only a few months. Star counts alone do not show quality. Where a README is mostly marketing, or the stars look out of line with the substance, I say so.

---

## Q1. Repos that turn Claude Code / Claude into a tutor or coach

### Takeaway
A new genre of Claude Code plugins and skills appeared in 2026 that reverses the usual flow. The human predicts, designs or explains, and Claude asks questions, holds back answers and checks understanding. The strongest ones (Engram, learning-opportunities, VibeWise, cc-self-train, learn-codebase) pair a strict tutoring prompt with durable state on disk (a learner journal, mastery receipts, an FSRS schedule) and hooks (a SessionStart nudge for due reviews, post-commit exercise offers). Claude Code itself now ships a built-in "Learning" output style.

### Cited findings

**Built into Claude Code / from Anthropic**
- Claude Code has built-in output styles: Default, Proactive, Concise, Explanatory and Learning. **Explanatory** adds `Insight` blocks that explain design choices. **Learning** adds the same blocks and also leaves a `TODO(human)` marker in the file wherever there is a real design decision (error handling, data structures, business logic), then asks the user to write that code. You enable it with `"outputStyle": "Learning"` (case-sensitive) or `/output-style`. Custom styles are also supported. — [Claude Code docs: output styles](https://code.claude.com/docs/en/output-styles)
- **anthropics/skills** (199k stars, active, pushed 2026-11-16): the reference repo for Agent Skills (folders of `SKILL.md` instructions plus scripts). It has creative, dev, enterprise and document skills, installable as a plugin marketplace. It has no tutoring-specific skill; its value is as the format and authoring reference (it includes skill-creator). — [anthropics/skills](https://github.com/anthropics/skills)
- **anthropics/courses** (23.2k stars, last push 2026-08-28): five Jupyter courses (API fundamentals, interactive prompt-engineering tutorial, real-world prompting, prompt evals, tool use). They teach how to build with Claude, not how to learn with Claude. The README notes the courses default to Claude 3 Haiku for cost, so the material is somewhat dated. — [anthropics/courses](https://github.com/anthropics/courses)

**Learning-science plugins for learning while coding with an agent ("anti-vibe-coding")**
- **DrCatHicks/learning-opportunities** (2.6k stars, created 2026-02, pushed 2026-08-19). Written by a learning-science researcher. After architectural work (new files, schema changes, refactors), Claude offers an optional 10-15 minute exercise using prediction, generation, retrieval practice and spaced repetition, which the author calls a "dynamic textbook". It ships an optional `learning-opportunities-auto` post-commit hook and an `orient` skill that writes `orientation.md` lessons for a new repo, based on program-comprehension research. Distributed as a Claude Code, Codex and Copilot plugin marketplace. — [learning-opportunities](https://github.com/DrCatHicks/learning-opportunities)
- **DrCatHicks/learning-goal** (283 stars): a goal-setting skill using Mental Contrasting with Implementation Intentions (MCII, an evidence-based self-regulation exercise). The README argues that learning goals fail because they are underspecified, not for lack of motivation. — [learning-goal](https://github.com/DrCatHicks/learning-goal)
- **nykooi1/vibe-wise** (4.4k stars, created 2026-09-29, pushed 2026-10-09). "You build. AI writes." The AI asks for your approach first, helps you examine tradeoffs and explains concepts. You own the design decisions and decide when to implement. It uses Python to restore learning context and reset learning notes between sessions. Listed in the official Anthropic plugin directory (`/plugin install vibe-wise@anthropic-plugin-directory`). Note: 4.4k stars in about 8 weeks. — [vibe-wise](https://github.com/nykooi1/vibe-wise)
- **ktaletsk/learn-codebase** (116 stars, pushed 2026-10). A Socratic tutor for unfamiliar codebases. It makes you predict before it reveals anything, answers questions with clarifying questions, and keeps `.claude/learning-journal.md` to track "what you confidently know vs. what you're still bluffing." — [learn-codebase](https://github.com/ktaletsk/learn-codebase)
- **mohi-devhub/antivibe** (1.1k stars, pushed 2026-07). Turns AI-written or legacy code into "deep dives" (what, why, when, alternatives) or senior-level audits. It has junior, mid and senior depth levels, a "known concepts" skip list, prerequisite mapping to CS principles, and optional auto-trigger hooks. It explains rather than tests, so it is more passive than the others. — [antivibe](https://github.com/mohi-devhub/antivibe)
- **Tasihi89/build-to-learn** (84 stars): "learning is the goal, and the thing you build is the evidence." Claude writes the code but leads you through the concepts. Notes go to a configurable folder (an Obsidian vault works), with Mermaid diagrams. — [build-to-learn](https://github.com/Tasihi89/build-to-learn)
- **AGI-is-going-to-arrive/ahadiff** (248 stars). Turns each git diff, AI-generated change, pair of file versions or Markdown document into an explanation shown next to its evidence, plus questions and later review. Stores history locally. — [ahadiff](https://github.com/AGI-is-going-to-arrive/ahadiff)
- Smaller repos in the same pattern: gkaria/vibe-learn (56 stars), Hassaan146/forge-mentor (22 stars, "decide-then-code," records your choice for every load-bearing decision), sshah03/teach-me (a lesson plus quiz per PR), rebeloper/okay (explain / teach-me / quiz-me / now-i-do-it), Pontinn/mentor-skill (never writes code for you). — [GitHub search "claude code teach me"](https://github.com/search?q=claude+code+teach+me&type=repositories)

**Full tutor engines delivered as Claude Code plugins**
- **nagisanzenin/engram** (1.5k stars, created 2026-07, pushed 2026-08-27). The most architecturally complete one. The README says explicitly: "Engram is not an agent-memory plugin... it's a learning system for the human." Commands are `/learn <topic>`, `/review` and `/coach`. It runs a four-role pipeline:
  - **Curriculum Architect**: builds a first-principles concept map in prerequisite order, not chapter order, and flags "threshold concepts."
  - **Tutor**: Claude under strict rules, running predict → productive struggle with hints → resolve → explain-back. Threshold concepts get a generated interactive HTML explorable.
  - **Assessor**: a separate agent that grades "blind" against the rubric and your verbatim answers only. It never sees the lesson. Every grade is written to disk as a receipt ("no receipts, no mastery claim").
  - **Scheduler**: `engram.py`, deterministic code that fits personal forgetting curves with FSRS-4.5.
  A quiet SessionStart nudge reports reviews due ("6 reviews due · ~4 min"). `/coach` gives weekly stats, a dashboard and tuning. There is one state folder shared across 9 agent platforms, and only Python stdlib is required. — [engram](https://github.com/nagisanzenin/engram)
- **kirilxd/claude-tutor** (161 stars, pushed 2026-07). Runs a plan → study → quiz → review loop. Features: SM-2 spaced repetition (1d → 6d → 15d), adaptive difficulty, weak-area targeting, a diagnostic assessment, cross-topic learner profiles (hands-on, visual, theory-first), session-start reminders for overdue reviews, **PreToolUse hooks that enforce the JSON schema of learner data** so it cannot be corrupted, and a local web dashboard on :3847. — [claude-tutor](https://github.com/kirilxd/claude-tutor)
- **hluaguo/learn-faster-kit** (411 stars, pushed 2026-08). The "FASTER" framework (Forget, Act, State, Teach, Enter, Review). Installs `.claude/agents/practice-creator.md`, `/learn`, `/review` and `/progress` commands, and `.learning/config.json` state. It launches Claude Code with a replaced system prompt; the README notes that Codex cannot do this, so the Codex version is weaker. — [learn-faster-kit](https://github.com/hluaguo/learn-faster-kit)
- **Li-Evan/BloomTutor** (328 stars, active). Named for Bloom's 2-sigma problem. Flow: syllabus → lesson → you annotate the Markdown lesson → feedback → next lesson tailored to your annotations → evaluation → summary. Available as a Claude Code skill (CLI, no backend) or a self-hosted Next.js + FastAPI web app. — [BloomTutor](https://github.com/Li-Evan/BloomTutor)
- **ArnaudGuiovanna/tutor-mcp** (111 stars, Go, active). Its design principle is "Generative teaching. Deterministic pedagogy." The LLM creates and explains, while a persistent, auditable engine decides progression using **Bayesian Knowledge Tracing + FSRS + prerequisite rules + assessment evidence**. The AI maps a subject into a versioned skill graph (concepts, prerequisites, goals). The engine tracks knowledge estimates, misconceptions and session memory, and separates "estimated knowledge, retained learning and demonstrated skills." Runs over MCP, so it works in Claude Code, Claude Desktop, ChatGPT and others. — [tutor-mcp](https://github.com/ArnaudGuiovanna/tutor-mcp)
- **bevibing/tutor-skills** (1.4k stars, stale since 2026-02-28). Two skills. `/tutor setup` turns PDFs, docs or codebases into an interlinked Obsidian "StudyVault" with a Map of Content. `/tutor` then quizzes you in graded 4-question rounds with concept tracking that writes progress back into the vault. — [tutor-skills](https://github.com/bevibing/tutor-skills)
- **ZeKaiNie/universal-examprep-skill** (401 stars, pushed 2026-10). An exam-cram coach that works from your slides, homework and past papers. Every taught concept cites `file p.N`. Out-of-scope questions exit with non-zero status, and provenance tags (🟢/🟡/⚠️) mark what was invented. State lives in `study_state.json` plus a mistake log, with no vector DB. — [universal-examprep-skill](https://github.com/ZeKaiNie/universal-examprep-skill)
- **itsAalaa7/adhd-study-coach** (100 stars): spaced repetition with small-chunk teaching for ADHD learners, as a Claude Code agent. — [adhd-study-coach](https://github.com/itsAalaa7/adhd-study-coach)
- Other Socratic / Feynman skills, all small (under 50 stars): cskwork/supertutor-skill, smashburger-dev/socratic-workshop, deniz-miro/claude-learn-skill, koukekoukej-glitch/feynman-tutor (you teach the AI so it can expose your gaps), guicortei/feynman-technique, HYH926/smart-learn, wanikhawar/claude-tutor (an Obsidian plugin). — [GitHub search "socratic tutor"](https://github.com/search?q=socratic+tutor&type=repositories); [GitHub search "feynman technique claude"](https://github.com/search?q=feynman+technique+claude&type=repositories)
- cdmorozov/claude-tutors (161 stars) and ShawhinT/ai-tutor-skill (82 stars, stale since 2025-12) are simple tutoring-skill examples. — [GitHub search "claude tutor"](https://github.com/search?q=claude+tutor&type=repositories)

**Learning Claude Code by building (the meta-skill)**
- **zainnab-sparq/cc-self-train** (only 15 stars, pushed 2026-05; research-backed). Learn Claude Code by building one of 5 project types across 10 modules (10-15 hours), started with `/start`. Progress lives in `CLAUDE.local.md`. The README lists 5 research contributions:
  1. A persona progression from Guide → Collaborator → Peer → Launcher.
  2. Adaptive scaffolding at two timescales, driven by hook-based heuristics on engagement quality.
  3. One feature sequence shared across all five project domains.
  4. Explicit pause primitives for step pacing.
  5. A curriculum that updates itself when the agent detects upstream tool changes.
  A pilot with 27 participants reported significant self-efficacy gains in all 10 skill areas (p < 0.001), per arXiv 2604.17460. — [cc-self-train](https://github.com/zainnab-sparq/cc-self-train)
- **wesammustafa/Claude-Code-Quest** (3.7k stars, active). A browser app that sits beside your terminal, checks each step you do in a practice repo, and has a mascot, "Pip," who cheers when a step passes. **Help fades as you progress:** full commands → hints → goal only. It "has no AI in it": checks are deterministic, and progress is tracked through a GitHub Actions workflow. — [Claude-Code-Quest](https://github.com/wesammustafa/Claude-Code-Quest)
- **shareAI-lab/learn-claude-code** (80.8k stars, active). Teaches agent "harness engineering" by building a nano Claude Code-like agent from scratch ("Bash is all you need"). It is a build-to-understand curriculum on agent internals, not a tutor for the learner. — [learn-claude-code](https://github.com/shareAI-lab/learn-claude-code)
- Similar: itsdecodingai/building-a-coding-agent-from-scratch-course (1.2k stars). — [GitHub search](https://github.com/search?q=learn+by+building+claude+code&type=repositories)

**Turning sources into agent-loadable knowledge**
- **virgiliojr94/book-to-skill** (38.8k stars, created 2026-05-01, pushed 2026-11-22). Distills a book or PDF into an Agent Skill: `SKILL.md` with mental models and a chapter index (~4k tokens), per-chapter files loaded on demand (~1k tokens each), plus `glossary.md`, `patterns.md` and `cheatsheet.md`. Works across Claude Code, Codex, Copilot CLI and others. The README claims 1,100+ tests. It makes the book available to the agent; it does not make the human learn it, so it is a retrieval tool, not a learning tool. 38.8k stars in about 7 months is unusually high for what it does; treat the popularity with caution. — [book-to-skill](https://github.com/virgiliojr94/book-to-skill)
- **Egonex-AI/Understand-Anything** (93.7k stars, active). A Claude Code plugin that runs a multi-agent pipeline to build a knowledge graph of a codebase (files, functions, dependencies, a business-domain view) with plain-English summaries and guided tours. Its tagline is "Graphs that teach > graphs that impress." The README header includes a product promo ("Let Ego sell it"); the star count looks out of proportion. — [Understand-Anything](https://github.com/Egonex-AI/Understand-Anything)
- **SYuan03/Skill-Anything** (354 stars): turns any source (PDF, video, web, audio) into a learning package with quizzes and flashcards. — [GitHub search "llm flashcards"](https://github.com/search?q=llm+flashcards&type=repositories)

### Inferences
- The best design pattern is to split roles across separate contexts: tutor, independent blind assessor, and deterministic scheduler code. Engram and tutor-mcp both refuse to let the LLM "vibe" mastery or schedules. That matters because an LLM grading its own lesson inflates mastery.
- Hooks are the key Claude Code primitive for growth systems. They provide SessionStart review nudges (Engram, claude-tutor), post-commit exercise offers (learning-opportunities), schema guards (claude-tutor) and engagement heuristics (cc-self-train).
- The built-in Learning output style is a zero-install baseline. A student could start with it plus learning-opportunities and Engram before building anything custom.
- Faded scaffolding (Claude-Code-Quest's commands → hints → goal; cc-self-train's Guide → Launcher) appears in only a few projects, yet it is well grounded in learning research.

### Gaps
- I found no independent evaluation (RCT or user study) for any Claude Code tutor plugin except cc-self-train's self-reported 27-person pilot. I did not read the arXiv paper itself.
- I could not confirm whether VibeWise is Anthropic-affiliated or just listed in the directory.
- I could not reach `wesammustafa/Claude-Code-Quest`'s claude-code-practice repo internals, or anthropics/skills subfolders (the GitHub repos API was blocked in this session; only search and raw READMEs worked).

---

## Q2. Open-source AI tutor projects (general, not Claude Code-specific)

### Takeaway
The field has split into (a) large "AI learning workspace" platforms (DeepTutor, OpenMAIC) with many modes and agents, (b) research-grade intelligent tutoring systems (ITS) that combine LLMs with knowledge tracing (GenMentor, Mathua, SmartStudy), and (c) older prompt-only tutors (Mr. Ranedeer, now discontinued). True Khanmigo clones barely exist in open source, and I found no LearnLM-based project with traction.

### Cited findings
- **HKUDS/DeepTutor** (61.8k stars, created 2025-12, very active; v1.7.4 released 2026-11-20). An "agent-native learning workspace" with modes for Chat, Quiz, Research, Visualize, Solve, **Mastery Path** (a knowledge-point map with topic conversations and mastery evidence), Immersive Reading, Books (chapters compiled into typed blocks: quizzes, flashcards, concept graphs, interactive HTML) and Video Lessons.
  - Memory has three inspectable layers: **L1 traces, L2 facts, L3 synthesis**, shown as an auditable Memory Graph with evidence links.
  - "Partners" are persistent companions with a `SOUL.md`, their own memory and IM channels (Telegram, Slack, Discord and others). It can consult Claude Code, Codex or Grok CLI as subagents.
  - Also: Anki and calendar (.ics) export, a learning journal, and "bounded tutoring memory." It is very broad, which makes it heavy for one student. — [DeepTutor](https://github.com/HKUDS/DeepTutor)
- **THU-MAIC/OpenMAIC** (44.2k stars, created 2026-03, very active; Tsinghua; JCST'26 paper). The "Open Multi-Agent Interactive Classroom." It turns a topic or document into a lesson with slides, quizzes, interactive HTML simulations and project-based learning. AI teacher and peer agents lecture and discuss, draw on a whiteboard, speak via TTS, and can operate the UI to direct attention. Model slots are configurable per task (e.g. Claude Sonnet for course outlines). Requires Node 22, pnpm and PostgreSQL. Its main goal is content generation and presentation, not a long-term learner model. — [OpenMAIC](https://github.com/THU-MAIC/OpenMAIC)
- **JushBJJ/Mr.-Ranedeer-AI-Tutor** (29.5k stars). A 2023 GPT-4 mega-prompt with personalization knobs (depth, learning style, tone, reasoning framework) and commands. **The README now says "DISCONTINUED"**; last push 2025-09-30. It is historically influential, but it has no persistence and no assessment. — [Mr. Ranedeer](https://github.com/JushBJJ/Mr.-Ranedeer-AI-Tutor)
- **plastic-labs/tutor-gpt** (935 stars, pushed 2026-02). A "theory-of-mind" tutor that reasons about the learner's needs and **rewrites its own prompts**. It is powered by Honcho, Plastic Labs' user-representation and memory service. The hosted version is "Bloom." It is a Next.js + Supabase app. — [tutor-gpt](https://github.com/plastic-labs/tutor-gpt)
- **GeminiLight/gen-mentor** (137 stars, pushed 2026-10). The official code for "LLM-powered Multi-agent Framework for Goal-oriented Learning in Intelligent Tutoring System" (WWW 2025 Industry oral). Its agents form a pipeline: Goal Refiner → skill-gap identification against your background → session path scheduler → per-session reading and quiz writer → **learner-profile rebuild from what you actually did**. No server DB; the learner archive is a single exportable JSON in the browser. Supports the Anthropic API. — [gen-mentor](https://github.com/GeminiLight/gen-mentor)
- **chuma-beep/mathua** (439 stars, Go, active). Math Academy-style mastery gating over a checked prerequisite DAG of 3,015 atomic concepts and 29 courses. **Speed thresholds count**: a correct but slow answer is "weak mastery." Uses FSRS-6 plus "FIRe" implicit repetition credit (practising an advanced skill credits its prerequisites). Problems come from parameterised Go generators rather than an LLM, which avoids hallucinated content. — [mathua](https://github.com/chuma-beep/mathua)
- **HumphreySun98/Smart-Study-Agent** (59 stars, pushed 2026-08). Frames learning as a POMDP: an RL policy chooses *what* to study, FSRS chooses *when*, and an LLM writes the quizzes. Runs as a web app (HF Spaces), a Chrome extension calling the Anthropic API directly, or inside Claude. Its deep-dive doc honestly reports experiments in which "the heuristic won." — [Smart-Study-Agent](https://github.com/HumphreySun98/Smart-Study-Agent)
- **zijinz456/OpenTutor** (189 stars, active). A local-first, block-based workspace. Upload a PDF and get notes, flashcards, quizzes and a tutor in about 30 seconds. Uses FSRS, knowledge graphs and "cognitive load detection," and runs local LLMs. — [OpenTutor](https://github.com/zijinz456/OpenTutor)
- **Nutlope/llamatutor** (2.1k stars): a simple search-grounded tutor demo on Llama 3.1. **HugeCatLab/ChatTutor** (1.3k stars, pushed 2026-01): a visual, interactive tutor. **molly554/whiteboard-ai-tutor** (553 stars, active): animated whiteboard lessons that compare Claude, Gemini and others. **luumlabs/aula** (72 stars): notes, slides and past exams turned into lessons, quizzes and flashcards. **helixnow/deep-student** (329 stars): a local-first AI learning workbench. — [GitHub search "ai tutor"](https://github.com/search?q=ai+tutor&type=repositories); [GitHub search "claude tutor"](https://github.com/search?q=claude+tutor&type=repositories)
- Khanmigo clones: a search for "khanmigo" returned only 0-2 star student clones (plus uBlock filters that block Khanmigo). The open-source equivalent does not really exist. — [GitHub search "khanmigo"](https://github.com/search?q=khanmigo&type=repositories)
- LearnLM: a search for "learnlm" returned nothing notable; "learnlm tutor" found only jsalsman/EduChat (16 stars, "A Constrained LearnLM Tutor"). — [GitHub search "learnlm tutor"](https://github.com/search?q=learnlm+tutor&type=repositories)
- **GarethManning/education-agent-skills** (1k stars, active): 165 "evidence-grounded" pedagogy skills, written for teachers and EdTech builders rather than self-learners. It is a useful library of teaching moves to borrow. — [education-agent-skills](https://github.com/GarethManning/education-agent-skills)

### Inferences
- Mathua and tutor-mcp show the mature pattern: deterministic content and progression, with the LLM used for explanation. Pure-LLM tutors (Ranedeer) were abandoned.
- The big platforms (DeepTutor, OpenMAIC) are impressive but are web apps with databases. For a personal growth OS built on Claude Code, borrowing their *concepts* (layered inspectable memory, Mastery Path, typed learning blocks) is more practical than adopting the platforms.
- Theory-of-mind user modelling (tutor-gpt/Honcho) and learner-profile rebuilds (GenMentor) are worth borrowing, but they should be grounded in evidence such as quiz receipts.

### Gaps
- I found no rigorous open-source Khanmigo equivalent and no LearnLM-based project of note.
- I did not verify DeepTutor or OpenMAIC learning-outcome claims; their READMEs focus on features.

---

## Q3. LLMs combined with spaced repetition, knowledge graphs, skill trees or mastery tracking

### Takeaway
FSRS (from open-spaced-repetition) is the standard scheduler, and several Claude-era tools embed it (Engram FSRS-4.5, Mathua FSRS-6, true-recall FSRS v6, tutor-mcp, SmartStudy). Anki now connects to Claude via MCP servers. Knowledge tracing (BKT/DKT) exists as academic libraries but is rarely wired to LLMs; tutor-mcp is the notable exception. "Skill tree" repos tend to be curated content more than adaptive engines.

### Cited findings
**Spaced repetition infrastructure**
- **open-spaced-repetition/fsrs4anki** (4.1k stars, pushed 2026-08): the FSRS scheduler for Anki. **ts-fsrs** (889 stars, active) and **py-fsrs** (534 stars, active, pushed 2026-11-13) are drop-in libraries, and **free-spaced-repetition-scheduler** (739 stars) documents the DSR (difficulty, stability, retrievability) model. — [fsrs4anki](https://github.com/open-spaced-repetition/fsrs4anki); [py-fsrs](https://github.com/open-spaced-repetition/py-fsrs); [GitHub search "fsrs"](https://github.com/search?q=fsrs&type=repositories)

**Anki connected to Claude**
- **ankimcp/anki-mcp-server** (576 stars, active) and its add-on version **ankimcp/anki-mcp-server-addon** (109 stars), **nailuoGG/anki-mcp-server** (255 stars, via AnkiConnect) and **jasperket/clanki** (45 stars). These let Claude read, create and review Anki cards. — [anki-mcp-server](https://github.com/ankimcp/anki-mcp-server); [GitHub search "anki llm"](https://github.com/search?q=anki+llm&type=repositories)

**LLM card generation and enrichment**
- **raine/anki-llm** (311 stars, Rust, pushed 2026-10): a CLI/TUI for bulk-generating and processing Anki cards with LLMs. **thiswillbeyourgithub/AnkiAIUtils** (896 stars, pushed 2026-06): adds explanations, mnemonics and illustrations to existing cards. **nilsreichardt/AnkiGPT** (184 stars): slides to cards. **PromtEngineer/Anki_FlashCard_Generator** (188 stars) is stale (2023). — [GitHub search "anki llm"](https://github.com/search?q=anki+llm&type=repositories); [GitHub search "anki ai"](https://github.com/search?q=anki+ai&type=repositories)

**Spaced repetition inside Obsidian**
- **pieralukasz/true-recall** (68 stars, active): AI-generated flashcards with FSRS v6 scheduling. **ctrlaltwill/LearnKit** (187 stars): a native study system for an Obsidian vault. **ECuiDev/obsidian-quiz-generator** (175 stars) is stale since 2024-11. — [true-recall](https://github.com/pieralukasz/true-recall); [LearnKit](https://github.com/ctrlaltwill/LearnKit)

**Spaced repetition applied to practice problems**
- **xiaohajiayou/Leetcode-Mastery-Scheduler** (543 stars): schedules LeetCode re-practice with FSRS, which is relevant to a CS student. — [GitHub search "fsrs"](https://github.com/search?q=fsrs&type=repositories)
- **shigella520/MindTrain** (129 stars): pluggable schedulers with Codex skill integration. — [GitHub search "anki ai"](https://github.com/search?q=anki+ai&type=repositories)

**Knowledge tracing libraries (not LLM-integrated)**
- **CAHLR/pyBKT** (294 stars, active), **pykt-team/pykt-toolkit** (463 stars) and chrispiech/DeepKnowledgeTracing (315 stars, from 2015). These are academic models of whether a student has mastered a skill. — [GitHub search "knowledge tracing"](https://github.com/search?q=knowledge+tracing&type=repositories)
- The only LLM-agent integration of knowledge tracing with real traction I found is tutor-mcp (BKT + FSRS). — [tutor-mcp](https://github.com/ArnaudGuiovanna/tutor-mcp)

**Skill trees**
- **24kchengYe/human-skill-tree** (602 stars, stale since 2026-03-25). Frames itself as "The Operating System for Human Learning in the Age of AI" and offers 30+ skills from K-12 to career level as AI skills. Its README cites Bastani et al. (2025, PNAS) as showing that GPT-4 tutoring improved math performance by 48-127%. That study also found that *unguarded* GPT-4 access hurt later exam performance; the README alludes to this only as "without structured pedagogical design..." — [human-skill-tree](https://github.com/24kchengYe/human-skill-tree); [Bastani et al. PNAS](https://www.pnas.org/doi/10.1073/pnas.2422633122)
- **zeroa234/cs-math-skill-tree** (84 stars): a CS/CE/EE skill map. **ankurrera/SoloLeveling** (107 stars): a Notion-like life OS that turns skills into RPG stats. — [GitHub search "skill tree learning"](https://github.com/search?q=skill+tree+learning&type=repositories); [GitHub search "life os"](https://github.com/search?q=life+os&type=repositories)
- Mastery-gated prerequisite DAGs: Mathua (3,015 concepts) and Engram (a first-principles concept map with threshold concepts). — [mathua](https://github.com/chuma-beep/mathua); [engram](https://github.com/nagisanzenin/engram)

### Inferences
- Use FSRS through py-fsrs or ts-fsrs rather than SM-2. claude-tutor still uses SM-2, the older and weaker baseline.
- Recall should ideally be free recall graded by a separate assessor (Engram), not multiple choice.
- For a CS student, two cheap high-value additions are FSRS on concepts and FSRS on problems (the LeetCode scheduler pattern).

### Gaps
- I found no project that unifies one learner model across coding practice, coursework concepts and business skills. Each tool keeps its own silo.
- I found no evaluation data comparing LLM-generated cards to hand-written ones in these repos.

---

## Q4. "Second brain" / personal OS / life OS projects that integrate Claude

### Takeaway
This is the most crowded and most star-inflated category. Most projects are Obsidian + Claude Code vaults that capture, link and retrieve information, following Karpathy's "LLM Wiki" pattern, or agent-memory layers (claude-mem, basic-memory). They make the *agent* smarter about you, but almost none measure whether *you* grew. Goal and reflection loops exist (LifeOS's current state → ideal state, Lotti's journal agents) but are rarely tied to skill evidence.

### Cited findings
**Life OS / personal AI harness**
- **danielmiessler/LifeOS** (20k stars, active, pushed 2026-11-18). A "General Purpose AI Harness" that "captures who you are, what you care about, and where you're trying to go." Its central concept is moving from Current State to Ideal State. It installs by having the AI read an install page (`curl | bash` for Claude Code). The README warns that it is "one person's personal AI harness, published as-is... constantly in flux" and that security is the user's responsibility. — [LifeOS](https://github.com/danielmiessler/LifeOS)
- Unconfirmed: danielmiessler/Personal_AI_Infrastructure did not appear in search. LifeOS may be its successor; I could not confirm this. — [GitHub search](https://github.com/search?q=repo%3Adanielmiessler%2FPersonal_AI_Infrastructure&type=repositories)

**Obsidian + Claude Code vault systems**
- **AgriciDaniel/claude-obsidian** (16.7k stars, pushed 2026-10). Follows Karpathy's LLM Wiki pattern with a capture (`inbox/`) → connect → ask → save → health-check loop: 15 skills and 3 agents produce linked, cited notes, Maps of Content and a check for dead links and orphans. Plain Markdown, no telemetry. — [claude-obsidian](https://github.com/AgriciDaniel/claude-obsidian)
- **agenticnotetaking/arscontexta** (3.5k stars, stale since 2026-02-24). Generates a whole knowledge system from a ~20-minute interview: folder structure, context files, a processing pipeline, **hooks that enforce structure on every write**, MOCs and templates with `_schema` blocks. It claims to be "backed by 249 research claims" and offers "derivation, not templating." — [arscontexta](https://github.com/agenticnotetaking/arscontexta)
- **huytieu/COG-second-brain** (1.5k stars, pushed 2026-10). Cognition + Obsidian + Git with 43 skills, 6 workers, **4 read-only verifiers**, a people CRM, and sync with GitHub, Linear and Slack. Inspired by Garry Tan's gstack/gbrain. — [COG](https://github.com/huytieu/COG-second-brain)
- Others:
  - ballred/obsidian-claude-pkm (1.9k stars, stale since 2026-02)
  - eugeniughelbur/obsidian-second-brain (5.4k stars, active; persistent memory for 8 agents in Markdown)
  - coleam00/second-brain-starter (912 stars) and coleam00/second-brain-skills (849 stars)
  - ArtemXTech/personal-os-skills (555 stars)
  - carlvellotti/carls-product-os (230 stars)
  - vmarcondes-nilo/personal-os (47 stars)
  - SamurAIGPT/llm-wiki-agent (3.7k stars)
  - YishenTu/claudian (16k stars, Claude Code embedded in Obsidian)
  - obsidianmd/obsidian-skills (53.5k stars; official skills that teach agents Obsidian formats)
  — [GitHub search "second brain claude"](https://github.com/search?q=second+brain+claude&type=repositories); [GitHub search "obsidian claude"](https://github.com/search?q=obsidian+claude&type=repositories); [GitHub search "personal os claude"](https://github.com/search?q=personal+os+claude&type=repositories)
- **khoj-ai/khoj** (38.2k stars, pushed 2026-08): a self-hostable AI second brain that answers from the web and your docs and runs custom agents. It is model-agnostic. — [khoj](https://github.com/khoj-ai/khoj)

**Agent memory (the agent remembers, the human does not learn)**
- **thedotmack/claude-mem** (119k stars, active). Runs a second "observer" agent next to Claude Code that takes notes. The next session starts with a short index and pulls details on demand. Supports 15 agents. Caution: the installer now pushes a browser sign-in and a "claude-mem observer" 30-day free trial that asks for a payment method; the README says you can opt out with `--provider` or `CLAUDE_MEM_ONLINE_OPTIN=false`. It is drifting from open-source tool toward commercial funnel. — [claude-mem](https://github.com/thedotmack/claude-mem)
- **basicmachines-co/basic-memory** (4.7k stars, active): Markdown-based AI memory over MCP. **rohitg00/agentmemory** (30.5k stars). **coleam00/claude-memory-compiler** (1.3k stars): hooks capture sessions and compile memory. **rohitg00/pro-workflow** (3k stars): self-correcting memory built from your corrections. **supermemoryai/claude-supermemory** (2.8k stars). — [GitHub search "claude memory"](https://github.com/search?q=claude+memory&type=repositories); [GitHub search "claude-mem"](https://github.com/search?q=claude-mem&type=repositories)

**Journaling, reflection and goals**
- **matthiasn/lotti** (1.2k stars, active, in development since 2016). Tasks, time tracking and journal on your own devices with end-to-end encrypted sync. AI agents keep living summaries of tasks and "propose while you decide." The author has tracked about 11,000 hours of his own work in it since 2022. — [lotti](https://github.com/matthiasn/lotti)
- **memex-lab/memex** (849 stars): a local-first AI journal app. **Lethe044/hermes-life-os** (247 stars): mood, sleep, habits and day planning. **edrisranjbar/lifeos** (126 stars): habits, goals, Kanban and finance with an MCP server. — [GitHub search "journaling ai agent"](https://github.com/search?q=journaling+ai+agent&type=repositories); [GitHub search "life os"](https://github.com/search?q=life+os&type=repositories)
- Coaching personas: artemnovitckii/notebooklm-coach (72 stars; turns an expert's YouTube library into a source-cited coach) and hancengiz/claude-code-prompt-coach-skill (147 stars). — [GitHub search "claude code coach"](https://github.com/search?q=claude+code+coach&type=repositories)

### Inferences
- Vault systems solve capture and retrieval well. Things to borrow: plain Markdown plus git, MOCs, health checks, hooks enforcing schema, and read-only verifier agents (COG).
- These systems do not separate what the agent knows about you from what you can actually do. A growth OS should keep a separate, evidence-backed learner model (a receipts and mastery file) rather than letting a memory plugin's summaries stand in for skill.
- Treat star counts above about 10k on 2026-created repos in this category (claude-mem, Understand-Anything, ECC at 309k, ruflo, book-to-skill) with scepticism. The READMEs carry star-history charts, star appeals ("Stars help more people find the project," as LifeOS puts it) or commercial upsells.

### Gaps
- I found no Claude-integrated project that closes the loop from goals → skill gaps → practice → evidence → reflection across life domains (career, coursework, business). LifeOS comes closest on goals; Engram and tutor-mcp come closest on evidence.

---

## Q5. Recurring architectures, and what is missing or poorly done

### Takeaway
A clear reference architecture recurs:
1. Plain-file learner state (Markdown or JSON in the repo or vault).
2. Slash-command entry points (`/learn`, `/review`, `/quiz`, `/coach`, `/progress`).
3. Hooks for nudges and integrity.
4. Role-separated agents (curriculum, tutor, assessor, practice creator).
5. A deterministic scheduler (FSRS).
6. Optional dashboards.

The common weaknesses: mastery claimed without evidence, learner state siloed per tool, no faded scaffolding, almost no outcome evaluation, and LLM-generated content that is not grounded in sources.

### Cited findings (recurring patterns, with examples)
- **Learner model files.** Examples:
  - `.claude/learning-journal.md` tracking "know vs. bluffing" ([learn-codebase](https://github.com/ktaletsk/learn-codebase))
  - `CLAUDE.local.md` progress ([cc-self-train](https://github.com/zainnab-sparq/cc-self-train))
  - `.learning/config.json` ([learn-faster-kit](https://github.com/hluaguo/learn-faster-kit))
  - `study_state.json` plus a mistake log ([examprep](https://github.com/ZeKaiNie/universal-examprep-skill))
  - a single exportable learner-profile JSON ([gen-mentor](https://github.com/GeminiLight/gen-mentor))
  - one state folder shared across 9 platforms ([engram](https://github.com/nagisanzenin/engram))
  - L1/L2/L3 inspectable memory ([DeepTutor](https://github.com/HKUDS/DeepTutor))
- **Hooks.**
  - SessionStart "reviews due" nudges ([engram](https://github.com/nagisanzenin/engram), [claude-tutor](https://github.com/kirilxd/claude-tutor))
  - post-commit learning offers ([learning-opportunities](https://github.com/DrCatHicks/learning-opportunities))
  - PreToolUse schema enforcement ([claude-tutor](https://github.com/kirilxd/claude-tutor))
  - engagement-quality heuristics driving scaffolding ([cc-self-train](https://github.com/zainnab-sparq/cc-self-train))
  - structure enforced on every write ([arscontexta](https://github.com/agenticnotetaking/arscontexta))
- **Role separation.**
  - Curriculum Architect / Tutor / blind Assessor / Scheduler ([engram](https://github.com/nagisanzenin/engram))
  - Goal Refiner → gap → path → content → profile rebuild ([gen-mentor](https://github.com/GeminiLight/gen-mentor))
  - a practice-creator subagent ([learn-faster-kit](https://github.com/hluaguo/learn-faster-kit))
  - read-only verifiers ([COG](https://github.com/huytieu/COG-second-brain))
- **LLM generates, code governs.** "Generative teaching. Deterministic pedagogy." ([tutor-mcp](https://github.com/ArnaudGuiovanna/tutor-mcp)); "deterministic code, not vibes" ([engram](https://github.com/nagisanzenin/engram)); parameterised problem generators ([mathua](https://github.com/chuma-beep/mathua)); RL picks what to study and FSRS picks when ([Smart-Study-Agent](https://github.com/HumphreySun98/Smart-Study-Agent)).
- **Inverted agency** (the human designs, predicts or writes the key piece): the TODO(human) in the Learning output style ([docs](https://code.claude.com/docs/en/output-styles)); approach-first ([vibe-wise](https://github.com/nykooi1/vibe-wise)); predict-first ([learn-codebase](https://github.com/ktaletsk/learn-codebase)).
- **Faded scaffolding and persona progression:** commands → hints → goal ([Claude-Code-Quest](https://github.com/wesammustafa/Claude-Code-Quest)); Guide → Collaborator → Peer → Launcher ([cc-self-train](https://github.com/zainnab-sparq/cc-self-train)).
- **Grounding and anti-hallucination:** page citations, out-of-scope abstention and provenance tags ([examprep](https://github.com/ZeKaiNie/universal-examprep-skill)); per-chapter on-demand loading ([book-to-skill](https://github.com/virgiliojr94/book-to-skill)).
- **Motivation and self-regulation:** MCII goal setting ([learning-goal](https://github.com/DrCatHicks/learning-goal)); current state → ideal state ([LifeOS](https://github.com/danielmiessler/LifeOS)).

### Inferences: design ideas for a 2nd-year CSBS student's Claude growth OS

**Borrow:**
1. Separate files for the learner model and for agent memory, with every mastery claim backed by an on-disk receipt (Engram).
2. py-fsrs as the scheduler, run by a SessionStart hook that prints what is due and stays silent otherwise (Engram).
3. A blind assessor subagent that sees only the rubric and your answer.
4. The Learning output style, or a custom output style, for coding work, plus post-commit "learning opportunity" offers.
5. A prerequisite concept DAG per course (DSA, DBMS, OS, accounting/finance, operations research) with threshold concepts flagged.
6. Faded scaffolding levels recorded per skill.
7. MCII-style goal setting each semester and a weekly `/coach` review.
8. Source-grounded study of course PDFs with citations and abstention (examprep pattern).
9. Plain Markdown plus git in an Obsidian vault, so the system stays useful without AI.
10. PreToolUse hooks that guard the learner-state schema.

**Avoid:**
1. Pure mega-prompt tutors with no persistence (Ranedeer, discontinued).
2. Letting the tutor grade itself.
3. SM-2 when FSRS is available.
4. Sprawling 40+ skill systems (COG, DeepTutor) that cost more tokens and attention than they return for one student.
5. Memory plugins with commercial onboarding funnels (claude-mem's trial).
6. Vault systems that only accumulate notes and never test recall ("collector's fallacy").
7. Trusting star counts on 2026-created repos.

**What's missing across the ecosystem:**
1. A unified cross-domain learner model (coding, coursework, business, career) that several tools could share. An MCP-served learner model like tutor-mcp is the closest.
2. Outcome evaluation. Only cc-self-train reports a study, and it measured self-efficacy, not skill.
3. Transfer and portfolio evidence: linking mastered concepts to shipped projects or PRs.
4. Calibration tracking (confidence vs. correctness), touched only by learn-codebase's "bluffing" list and Mathua's speed thresholds.
5. Business and soft-skill learning, which is nearly absent apart from PM coaching skills.
6. Scheduled reviews outside the coding session (e.g. a cron-scheduled weekly reflection). Most systems only nudge when you happen to open Claude Code.

### Gaps
- I could not inspect plugin source (hooks and agent files) for most repos, because the per-repo GitHub API was blocked in this session; the mechanics above come from READMEs and may overstate what is implemented.
- I did not use web search, so projects outside GitHub search ranking (blog-only setups, gists, Anthropic's "Claude for Education" learning mode) are not covered.
