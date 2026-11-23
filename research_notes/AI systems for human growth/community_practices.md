# Community Practices: How Real People Use Claude and Other LLMs to Learn and Grow (2025–2026)

Research method note: about 16 tool calls (web search plus a few fetches). Search did not return Reddit threads directly; Reddit and HN sentiment appears here mostly second-hand through blogs and news coverage, so treat "Reddit says..." claims accordingly. Fetches of `newsletter.pragmaticengineer.com` and `addyo.substack.com` were blocked by this session's network allowlist, so Pragmatic Engineer and Osmani content is from search snippets only.

## Q1. Concrete setups people share for learning with Claude

### Takeaway
The setups that recur follow the same idea. Claude gets set up as a tutor that will not hand over answers: Claude.ai Learning style, the Claude Code "Learning"/"Explanatory" output styles, or a tutor CLAUDE.md like Stanford CS336's. Claude Code is also pointed at a plain-markdown Obsidian vault with a CLAUDE.md, which turns it into a "second brain / life OS". LLM-generated Anki cards are popular too, but users consistently say they need human review and editing.

### Cited Findings
**Tutor / learning modes (official)**
- Claude's Learning mode launched in April 2025 as part of Claude for Education. It guides students' reasoning (Socratic) rather than giving answers. It was later rolled out to all users via the style dropdown — [Anthropic: Introducing Claude for Education](https://www.anthropic.com/news/introducing-claude-for-education?); [AlternativeTo, Aug 2025](https://alternativeto.net/news/2025/8/claude-s-learning-mode-is-now-available-to-all-users-with-new-coding-styles)
- Claude Code has a separate "Learning" output style that leaves `#TODO` markers and asks the user to write short code segments themselves. It also has an "Explanatory" style — [AlternativeTo](https://alternativeto.net/news/2025/8/claude-s-learning-mode-is-now-available-to-all-users-with-new-coding-styles); Anthropic's own skill-formation paper recommends these modes — [Anthropic research](https://www.anthropic.com/research/AI-assistance-coding-skills)
- Universities publish student guides for it, e.g. Northeastern's "Using Claude Learning Mode to Study" — [Northeastern](https://learning.northeastern.edu/ai-student-guides-using-claude-learning-mode-to-study)
- Reviews are mixed. One tester found it good for active learning. Another found it frustrating because "the bot doesn't provide you a clear stopping point for the lesson" — [Yahoo Tech comparison](https://tech.yahoo.com/ai/articles/claude-learning-modes-chatgpt-study-161847670.html); [Yahoo Tech hands-on](https://tech.yahoo.com/ai/claude/articles/tried-learning-anthropics-ai-tutor-090000210.html). (Anecdote.)

**CLAUDE.md "tutor mode"**
- Stanford CS336 (Language Modeling from Scratch) ships a CLAUDE.md/AGENTS.md that makes the agent a tutor, not an implementer. It has a Role section, an allowed list (explain concepts, review your code, ask guiding questions) and a forbidden list (do not write full functions/classes). A related tip is to log each prompt to a history file — [qwe.edu.pl CS336 guide](https://www.qwe.edu.pl/tutorial/cs336-stanford-agents-md-guide/); [DEV Community](https://dev.to/tyson_cung/stanford-just-published-rules-for-ai-coding-agents-what-devs-should-know-1d2m)
- The "Learning Mode Coding Coach" CLAUDE.md template has the agent stop and ask the human to write code at meaningful trade-off points. Where there is one obviously correct answer, it just writes the code — [claudecodehq playbook](https://claudecodehq.com/playbooks/learning-mode-coding)
- Other templates: "Turn Claude Code into Claude Teacher" — [weihaoqu wiki](https://weihaoqu.github.io/learnAIDoc/wiki/claude-teacher-setup/); a tutor SKILL.md — [kevinnio/tutor](https://raw.githubusercontent.com/kevinnio/tutor/master/SKILL.md)
- Caveats from practitioners: tutor mode is the wrong default for deadline work ("just friction with no payoff"). Models sometimes drop hard rules in these files. Keep CLAUDE.md lean because it costs context on every run — [claudecodehq](https://claudecodehq.com/playbooks/learning-mode-coding); [DataCamp](https://www.datacamp.com/de/tutorial/claude-code-best-practices)
- A widely reported practitioner pattern is to run two explicit modes. Recurse Center alumni described a "learning mode" (no LLM code generation) and a "shipping mode" (rely on models) — [Recurse Center, "Developing our position on AI", Jul 2025](https://recurse.com/blog/191-developing-our-position-on-ai)

**Obsidian + Claude Code "second brain / life OS"**
- The pattern is to open Claude Code in an Obsidian vault (plain markdown) and add a CLAUDE.md describing folder structure and conventions. Many say no plugin is needed — [Viable Edge guide](https://www.viableedge.com/blog/claude-code-obsidian-second-brain)
- atomicpapa/claude-obsidian-setup frames this as turning Claude Code into a "personalized life OS". Its vault structure borrows from Steph Ango, and it credits huytieu's COG repo for the CLAUDE.md + MCP + skills approach — [GitHub](https://github.com/atomicpapa/claude-obsidian-setup)
- AgriciDaniel/claude-obsidian is an MIT-licensed plugin based on Karpathy's "LLM Wiki" pattern. You drop in sources and Claude writes linked notes and maintains an index — [GitHub](https://github.com/AgriciDaniel/claude-obsidian)
- eugeniughelbur/obsidian-second-brain stores persistent agent memory as markdown in the vault and offers about 48 commands, including scheduled agents — [GitHub](https://github.com/eugeniughelbur/obsidian-second-brain)
- Privacy practice: lock sensitive folders (personal, manuscripts) out of Claude's read/write via Claude Code settings — [Viktorie Sladkova](https://viktoriesladkova.cz/en/clanky/second-brain-claude-code-obsidian/)
- There are free "LIFE OS" vault templates with a CLAUDE.md and note templates — [Noah's Substack](https://noahvnct.substack.com/p/how-to-build-your-ai-second-brain); first-person build log — [Medium, Evgeni Rusev](https://medium.com/@evgeni.n.rusev/how-i-built-my-second-brain-with-obsidian-claude-code-9fb54b7665ca)

**Anki / spaced repetition**
- One blogger's workflow is to have Claude turn PDFs into cards, then review and edit them. The main complaint is that the LLM "often stuffs too much information into a single card" (violating the minimum-information principle) — [smoothbrain blog: workflow](https://smoothbrain.bearblog.dev/my-workflow-for-using-llms-to-create-anki-cards); [smoothbrain: Creating Anki cards with AI?](https://smoothbrain.bearblog.dev/creating-anki-cards-with-ai)
- Tooling: Obsidian plugins (Ankinator, Auto Anki) push LLM cards via AnkiConnect — [Ankinator](https://community.obsidian.md/plugins/ankinator), [Auto Anki](https://community.obsidian.md/plugins/auto-anki). Claude + Anki MCP server review systems also exist — [nitropia Substack](https://nitropia.substack.com/p/the-lazy-nerds-guide-to-superhuman). Note→Anki converters advise "Always review Claude-generated content before studying" — [notes-2-anki](https://awesome.ecosyste.ms/projects/github.com%2Fdrewbuiltit%2Fnotes-2-anki); [Rizzo blog](https://rizzonicola-blog.pages.dev/posts/anki-with-ai)
- AnkiWeb forum users point newcomers to r/AnkiAi for LLM deck automation — [AnkiWeb forum](https://forums.ankiweb.net/t/automating-decks-creation/70294)

**Institutional AI tutors**
- CS50's Duck (Harvard) uses "pedagogical guardrails" to guide rather than give solutions, and students described it as like a personal tutor — [Liu, Malan et al. paper](https://cs.harvard.edu/malan/publications/V1fp0567-liu.pdf). Malan said in 2026 that it still produces blocks of code up to about a quarter of the time despite instructions — [Harvard Gazette, 2026](https://news.harvard.edu/gazette/story/2026/09/taming-the-duck-for-starters/). Slides report about 317K users and about 21K prompts/day. Questions to human staff fell from 0.89 to 0.28 per student (self-reported, preliminary) — [Malan slides](https://docs.google.com/presentation/d/1xQPkTsw5E9ytBKq0WDpwgESLYyDMkZ5nMkddbIHWipI/htmlpresent)

### Inferences
- The setup with the best evidence behind it is "tutor rules + attempt first + explain-back". Anthropic's RCT (Q2) supports it, and CS50, CS336 and Recurse each landed on it independently. A growth OS should make tutor mode a switchable mode (learning vs. shipping), not a global default.
- Prompt-level "don't give me the answer" rules leak (CS50 reports about 25% leakage; practitioners report CLAUDE.md rules being dropped). Structural enforcement is more reliable than rules alone. Examples are Claude Code's Learning style TODOs, or a workflow where the student's own attempt must be committed before Claude reviews it.
- A plain-markdown vault + CLAUDE.md is the dominant low-friction "life OS" substrate. Plugin-heavy setups exist, but the no-plugin approach is repeatedly recommended.
- LLM-generated Anki cards work if the system enforces atomic cards and human review. A good default is to ask Claude to split cards to one fact each and have the student edit or approve before import.

### Gaps
- Could not retrieve primary r/ClaudeAI, r/learnprogramming or r/ObsidianMD threads (search returned none directly). Community sentiment here is second-hand.
- Found no strong primary sources on journaling/coaching with Claude (reflection prompts, weekly reviews) in this pass.
- The claim that Learning mode is "underrated" according to Redditors comes from an undated Medium-style post ([ai.plainenglish.io](https://ai.plainenglish.io/claudes-learning-mode-actually-works-i-tested-it-as-a-personal-tutor-276a05067c49?gi=557c1ec623b7)) and is unverified.

## Q2. Failure modes people report

### Takeaway
The best-evidenced failure is "comprehension debt": AI-assisted learners produce working code but understand less, and debugging suffers most. The strongest evidence is Anthropic's Jan 2026 RCT (50% vs. 67% quiz score). How AI is used matters more than whether it is used. Delegation and AI-driven debugging score worst; conceptual questioning and generate-then-interrogate score best. Self-reported productivity is also unreliable (METR).

### Cited Findings
- **Anthropic RCT (Jan 2026):** 52 mostly junior engineers learned the unfamiliar Trio async library. AI users were about 2 min faster, which was not significant (p=0.391). They scored 50% vs. 67% on the follow-up quiz (Cohen's d=0.738, p=0.01), "nearly two letter grades". The biggest gap was on **debugging** questions — [Anthropic research](https://www.anthropic.com/research/AI-assistance-coding-skills); [arXiv 2601.20245](https://www.arxiv.org/pdf/2601.20245); [InfoQ](https://www.infoq.com/news/2026/02/ai-coding-skill-formation)
- Interaction patterns from the same study (small n, associational):
  - Low scorers (<40%): **AI delegation** (fastest, learned least), **progressive AI reliance** (starts asking, ends up handing everything over), **iterative AI debugging** (using AI to fix rather than understand; also slowest).
  - High scorers (≥65%): **conceptual inquiry** (only conceptual questions, resolve own errors; largest group and second-fastest), **hybrid code+explanation**, **generation-then-comprehension** (generate, then quiz the AI to check understanding) — [Anthropic research](https://www.anthropic.com/research/AI-assistance-coding-skills)
  - Quote: "Cognitive effort—and even getting painfully stuck—is likely important for fostering mastery." Caveat: it measured immediate comprehension, not long-term retention — [Anthropic](https://www.anthropic.com/research/AI-assistance-coding-skills); [InfoQ](https://www.infoq.com/news/2026/02/ai-coding-skill-formation)
- **Illusion of competence / productivity:** In METR's study of 16 experienced developers, AI made them 19% slower while they believed they were about 20% faster — reported via [AgentPatterns.ai](https://agentpatterns.ai/human/skill-atrophy/) (secondary; METR primary not fetched)
- **Vibe coding without understanding:** Karpathy coined "vibe coding" ("I just see things, say things, run things, and copy-paste things, and it mostly works"). Commentators warn beginners hit walls when code "looked right but didn't work", and that "if you don't understand what your code is doing, you'll run into bugs you can't debug" — [itch.io](https://itch.io/blog/926424/vibing); [Yahoo Tech](https://tech.yahoo.com/apps/articles/why-im-learning-code-age-110115011.html)
- **Tutorial hell 2.0 / dependence:** "If you can't answer [what your code should do] yourself, you're not ready for AI yet, you're ready for a tutorial" — [DEV Community](https://dev.to/dhruvjoshi9/ai-coding-assistants-for-beginners-how-to-use-chatgpt-copilot-without-cheating-544). Warnings about dependence on one's "AI of choice" — [DEV](https://dev.to/zrm9901/responsible-use-of-ai-in-coding-5061)
- **Skill atrophy in experienced devs:** Osmani describes an engineer who stopped reading docs and debugged by pasting errors into AI — [Osmani, "Avoiding Skill Atrophy in the Age of AI"](https://addyo.substack.com/p/avoiding-skill-atrophy-in-the-age). An "I'm Done Using AI" post (2026) reports becoming "lazier" and having stopped learning, while commenters countered that their skills grew faster than ever — [kottke.org](https://kottke.org/26/08/0049486-im-done-using-ai). A Product Hunt thread is titled "tried to fix a small bug without AI just to see if I still could — it wasn't pretty" — [Product Hunt](https://www.producthunt.com/p/vibecoding/tried-to-fix-a-small-bug-without-ai-just-to-see-if-i-still-could-it-wasn-t-pretty)
- **Counter-view:** Flavio Copes, "AI is eroding my coding skills, and I don't care" (Nov 2026). He lets syntax-level skills rust while keeping the ones he considers essential — [flaviocopes.com](https://flaviocopes.com/ai-eroding-coding-skills/). Sean Goedecke argues that using AI for a task means learning less about *that task*, but disputes that this generalizes into lasting decline — [seangoedecke.com](https://seangoedecke.com/software-engineering-may-no-longer-be-a-lifetime-career/)
- **Friction is a feature:** A Recurse alum: "smoothing over all the difficulty of learning something probably isn't desirable". An alum who helped launch ChatGPT warned that reliance means "your learning will atrophy" — [Recurse Center](https://recurse.com/blog/191-developing-our-position-on-ai)
- **AI tutor quirks:** Learning-mode sessions have no clear stopping point — [Yahoo Tech](https://tech.yahoo.com/ai/articles/claude-learning-modes-chatgpt-study-161847670.html). The CS50 Duck spoils solutions up to a quarter of the time — [Harvard Gazette](https://news.harvard.edu/gazette/story/2026/09/taming-the-duck-for-starters/)
- **Over-trusting generated study material:** LLM Anki cards that are overloaded or unreviewed — [smoothbrain](https://smoothbrain.bearblog.dev/my-workflow-for-using-llms-to-create-anki-cards)

### Inferences
- A growth OS should detect and nudge against the three low-scoring patterns. Signals include: the student asking for full code before attempting; a drift from questions to delegation within a session; and pasting errors without a hypothesis. It should steer toward conceptual inquiry and generate-then-interrogate.
- Periodic "no-AI checks" (fix a bug or solve a problem unaided) are a recurring practitioner tactic for measuring real skill rather than perceived skill. They directly address the METR-style perception gap.
- Sessions need explicit endpoints (goal, then a retrieval quiz, then done). Otherwise learning modes sprawl.

### Gaps
- Could not find quality first-hand accounts of "burnout from productivity systems" or "over-engineering the system instead of learning" specific to Claude life-OS builds. This is a plausible risk but undocumented in what I found. A growth OS designer should treat it as a hypothesis.
- No long-term (semester-plus) retention studies of AI-tutored CS students were found.
- Osmani's specific tactic list could not be fetched (network block).

## Q3. Respected voices and the "should juniors use AI early?" debate

### Takeaway
There is broad consensus that AI is a multiplier on fundamentals, not a substitute for them. The disagreement is about timing. Some (Willison per secondary reports, CS50, Recurse "learning mode") favor guarded or no AI for absolute beginners. Others stress that friction removal makes this the best time ever to learn. Nobody credible says "don't learn to program".

### Cited Findings
- **Simon Willison:** "there has never been a better time to learn to program" because LLMs shave down the learning curve. He notes classrooms will lag "since we don't know how to use these things in classrooms yet" — [Real Python podcast ep. 236](https://realpython.com/podcasts/rpp/236/). He calls advice not to learn programming because AI will automate it some of the worst career advice — [Willison, "Here's how I use LLMs to help me write code", Mar 2025](https://simonwillison.net/2025/Mar/11/using-llms-for-code/). The Register reports he encourages beginners to stay away from AI and teaches advanced students to use it for productivity (secondary, 2024) — [The Register](https://www.theregister.com/2024/01/27/ai_coding_automatic/). He amplified Recurse's AI position — [simonwillison.net](https://www.simonwillison.net/2025/Jul/24/recurse-center)
- **Andrej Karpathy:** He moved from about 80% manual to about 80% agent-driven coding and now "mostly programs in English". He also warns models make wrong assumptions and errors "like sloppy junior developers" — quoted in [Osmani, "The 80% Problem in Agentic Coding"](https://addyo.substack.com/p/the-80-problem-in-agentic-coding). Forbes reports his view is that technical depth becomes a bigger multiplier, not irrelevant — [Forbes, Mar 2026](https://www.forbes.com/sites/josipamajic/2026/03/22/ai-agents-wrote-80-of-karpathys-code-junior-developers-are-paying-the-price/). His education work stresses building from scratch (Zero to Hero → GPT from scratch; Eureka Labs/LLM101n; nanochat, which reportedly was not vibe-coded) — [Willison on Eureka Labs](https://simonwillison.net/2024/Jul/16/introducing-eureka-labs/); [Slashdot on nanochat](https://developers.slashdot.org/story/25/10/19/0022237/openai-cofounder-builds-new-open-source-llm-nanochat---and-doesnt-use-vibe-coding)
- **Addy Osmani:** Juniors who lean on AI before building fundamentals risk skill atrophy. Experienced engineers gain because they can review output — [Osmani, Agentic Engineering](https://addyosmani.com/blog/agentic-engineering/); [Avoiding Skill Atrophy](https://addyo.substack.com/p/avoiding-skill-atrophy-in-the-age)
- **David Malan / CS50:** Embraces AI but only behind pedagogical guardrails (the Duck), and disallows general tools like ChatGPT for coursework — [Liu, Malan et al.](https://cs.harvard.edu/malan/publications/V1fp0567-liu.pdf); [The Register](https://www.theregister.com/2024/01/27/ai_coding_automatic/)
- **Anthropic (company position via research):** "AI assistance should enable humans to work more efficiently *and* develop new skills at the same time." It recommends learning modes and managers building systems that keep engineers learning — [Anthropic](https://www.anthropic.com/research/AI-assistance-coding-skills)
- **Recurse Center (Jul 2025):** Alumni were split, but most saw LLMs as useful "tutors or rubber ducks" and warned against outsourcing the work — [Recurse Center](https://recurse.com/blog/191-developing-our-position-on-ai)
- **University courses:** Cornell CS2110 (Fall 2026) publishes "Thoughts on Generative AI in Programming Courses" — [Cornell](https://www.cs.cornell.edu/courses/cs2110/2026fa/resources/genai/). MIT's Daniel Jackson has written on AI in CS education — [MIT CSAIL PDF](https://groups.csail.mit.edu/sdg/pubs/2025/jackson-ai-education.pdf) (not read in detail)
- **Industry pipeline worry:** Commentators warn of a "dwindling talent pipeline" if juniors don't develop debugging/judgment — [drlongnecker, May 2026](https://drlongnecker.com/blog/2026/05/junior-talent-pipeline-ai-development-skills-atrophy/); [LeadDev](https://leaddev.com/hiring/what-happens-when-learn-code-fails-generation); [JFSI: "The AI Era Punishes Passive Learning"](https://jfsi.io/articles/junior-engineers-intentional-learning)

### Inferences
- The defensible position for a 2nd-year student is staged AI use. Fundamentals courses get tutor or guarded mode (conceptual Q&A, review of their attempts). Projects get full agentic use plus mandatory "explain/defend the diff" and occasional unaided reps. This maps onto Recurse's learning/shipping split and Anthropic's high-scoring patterns.
- "Agentic engineering" skills (specifying, reviewing and verifying AI output) are emerging as the senior differentiator. Learning to review code critically is itself a skill to train.

### Gaps
- Could not verify current (2025–2026) primary statements from Kent Beck, Thorsten Ball, Steve Yegge, Hamel Husain or Boris Cherny on how students should learn. They were not covered in this pass, so do not attribute specific views to them without checking.
- Karpathy's 2025 Dwarkesh Patel podcast likely contains direct learning advice but was not retrieved.

## Q4. Junior developer job market 2025–2026 and skills that matter

### Takeaway
Entry-level software hiring is sharply constrained (one widely cited figure: about 4.5% of US software postings were entry-level in Q1 2026, per Indeed data via secondary sources). The evidence on AI causation conflicts. There are signs of selective rebound at scaleups and of firms redefining junior roles. Candidates who can show real projects, debugging and judgment over AI output fare better.

### Cited Findings
- Entry-level was reportedly 4.5% of US software dev postings in Q1 2026, the lowest of any occupation Indeed tracks. Hiring recovery is about 71% senior roles — [Solvebar, citing Indeed](https://solvebar.com/blog/entry-level-software-jobs-2026-junior-developers); [danilchenko.dev](https://www.danilchenko.dev/posts/junior-developer-jobs-2026/) (secondary; estimates of decline range from about 20% to 67% depending on metric)
- Stanford research: employment of 22–25-year-olds in AI-exposed jobs is about 19% below trend, mostly through fewer hires. The authors call it descriptive, not causal. Indeed notes declines began before ChatGPT — via [Medium summary](https://medium.com/@syamkumar0418/junior-developer-jobs-and-ai-in-2026-what-the-hiring-data-really-says-and-how-to-get-hired-021389af4f40) (secondary)
- Harvard study: junior employment falls about 9–10% in the six quarters after firm genAI adoption, with seniors flat — via [smarthireus](https://smarthireus.com/blog/ai-entry-level-it-jobs-2026) (secondary)
- Contradicting evidence: a June 2026 IZA paper found Copilot-adopting firms had a 3–5% higher monthly probability of hiring software engineers, driven by entry-level hires. The conclusion was "a hiring squeeze, not a collapse" — via [danilchenko.dev](https://www.danilchenko.dev/posts/junior-developer-jobs-2026/) (secondary)
- IBM reportedly tripled junior intake by redefining entry-level roles — [danilchenko.dev](https://www.danilchenko.dev/posts/junior-developer-jobs-2026/) (secondary)
- Gergely Orosz (Pragmatic Engineer, Nov 2025, "Tech jobs market 2025, part 3"): more scaleups and public tech companies are "doubling down on hiring new grads and early-career engineers". Times are tougher for career-breakers, self-taught and native-mobile candidates — [Pragmatic Engineer](https://newsletter.pragmaticengineer.com/p/tech-jobs-market-2025-part-3) (snippet only; full text blocked)
- HackerRank cites Orosz reporting that growing startups are "quietly bringing juniors back". It also says Anthropic was scaling headcount while still largely avoiding new grads — [HackerRank](https://www.hackerrank.com/blog/the-engineering-hiring-dilemma/)
- IEEE Spectrum guidance for early-career engineers on staying ahead of AI — [IEEE Spectrum](https://spectrum.ieee.org/ai-effect-entry-level-jobs); CIO on pipeline collapse — [CIO](https://www.cio.com/article/4188578/how-to-keep-your-it-talent-pipeline-from-collapsing.html)

### Inferences
- For a CS & Business Systems student, the hiring signals point to the same profile. Valued: proof of shipped projects; the ability to debug and review AI output (exactly the skill the RCT shows erodes); domain/business understanding; and evidence of learning velocity. Being a formal degree student is an advantage relative to self-taught candidates in Orosz's data.
- A growth OS should track portfolio evidence (projects, write-ups, PRs) and debugging competence, not just study hours.

### Gaps
- Primary Indeed Hiring Lab, Stanford ("Canaries in the Coal Mine") and IZA papers were not fetched. Figures here are from secondary blogs and should be verified before quoting.
- Little non-US data (e.g. India, relevant for a CSBS student) was found.
- No direct hiring-manager survey of "skills that matter now" was retrieved.

## Q5. Learning-in-public and self-directed growth frameworks adapted with AI

### Takeaway
Recurse Center is the clearest documented case of a self-directed learning community adapting to AI. Its answer was to treat LLMs as tutors and rubber ducks, keep friction and separate learning mode from shipping mode. I found little 2025–2026 material on how swyx's "learn in public", build-in-public or #100DaysOfCode have been adapted for AI.

### Cited Findings
- Recurse Center's July 2025 position (Nick Bergson-Shilcock) came from consulting alumni. Its themes are the tutor/rubber-duck use, learning vs. shipping modes, and the warning against smoothing over difficulty — [Recurse Center](https://recurse.com/blog/191-developing-our-position-on-ai); commentary — [Christian Tietze](https://christiantietze.de/posts/2025/07/put-blinders-on-adverse-effects/); [Simon Willison](https://www.simonwillison.net/2025/Jul/24/recurse-center)
- Practitioner "coding by hand" counter-movement posts — [Miguel Conner, "I'm Coding by Hand"](https://miguelconner.substack.com/p/im-coding-by-hand); "Learn to code with LLMs: I read a..." — [Max Mynter](https://maxmynter.substack.com/p/learn-to-code-with-llms-i-read-a); "Thinking About Thinking With LLMs" (Oct 2025) — [davish](https://deploy-preview-43--davish-site.netlify.app/blog/2025/10/thinking-with-llms)
- Beginner "how I'm learning to code in the AI age (2025–2026 edition)" posts on DEV recommend building with AI as a helper while avoiding passive tutorials — [DEV Community](https://dev.to/the_mj_super/how-im-learning-to-code-in-the-ai-age-2025-2026-edition-3b8l)
- CS336's tutor CLAUDE.md suggests logging every prompt to a history file. This is effectively an auditable learning log that could double as learning-in-public material — [qwe.edu.pl](https://www.qwe.edu.pl/tutorial/cs336-stanford-agents-md-guide/)

### Inferences
- Learning in public fits naturally with an AI growth OS. Claude can turn session logs, prompt histories and vault notes into weekly public write-ups (TILs, blog posts). Those write-ups are also portfolio evidence for the tight junior market in Q4.
- Recurse's "learning mode / shipping mode" is the most transferable framework for a student's personal system.

### Gaps
- No verified 2025–2026 sources on swyx's "Learn in Public" being adapted with AI, or on #100DaysOfCode/build-in-public with Claude. Swyx's original essay (swyx.io/learn-in-public) predates the period and was not fetched.
- No data on whether AI-assisted learning-in-public artifacts are valued by hiring managers.
