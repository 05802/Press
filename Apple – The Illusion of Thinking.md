---
source: "https://chatgpt.com/c/6845d920-ccdc-8004-ae2b-d6d0fb90a677"
author:
published:
---
| creation date:  <br>2025-06-08 21:44 | modification date:  <br>2025-06-08 21:44 |
| ------------------------------------------------- | ---------------------------------------------------------- |

---



the-illusion-of-thinking.pdf

PDF

### 1\. Setting the Stage — Why this Piece matters

The Piece tackles a deliciously thorny question: *Can today’s “Large Reasoning Models” (LRMs) really **reason***, or are they just verbose parrots? By pitting state-of-the-art LRMs against a family of classic logic puzzles whose difficulty can be dialed up like a stereo knob, the author tries to pry open the black box and watch the gears turn (or seize). Spoiler: the gears grind to a halt sooner than you might think. But wait, there’s more!

---

### 2\. Quick Glossary — Speak the lingo, join the party

| Term | Plain-English Meaning | Why it matters in the Piece |
| --- | --- | --- |
| **LLM (Large Language Model)** | A giant text autocomplete engine. | Baseline for comparison. |
| **LRM (Large Reasoning Model)** | An LLM given extra training and prompts so it “thinks out loud” (long *Chain-of-Thought*, self-checks, etc.). | Star of our show. |
| **Chain-of-Thought (CoT)** | The step-by-step reasoning a model prints before its answer. | Key to judging *how* it reasons. |
| **pass@k** | Chance that at least one of *k* sampled answers is correct. | Lets the author compare models under equal compute budgets. |
| **Inference-token compute** | How many tokens the model burns during one answer. | A proxy for “effort spent thinking.” |

---

### 3\. First Principles — The author’s starting bets

1. **Complexity matters**: Reasoning skill should degrade smoothly as puzzles get tougher; sudden collapses hint at deeper limits.
2. **Compute is currency**: If LRMs really *reason*, giving them more inference tokens ought to buy more success.
3. **Controlled environments beat messy benchmarks**: Custom puzzles free of training-set contamination reveal truer limitations than well-trodden math datasets.

---

### 4\. Logic of the Argument — How the author builds the case

**Step A:** Swap out contaminated math datasets for four venerable puzzles (Tower of Hanoi, Checker-Jumping, River-Crossing, Blocks World). Because the author can scale each puzzle’s size, they get a clean “difficulty dial.”  
**Step B:** Run matched pairs of models — one “thinking-enabled,” one “plain” — under equal token budgets on hundreds of puzzle instances.  
**Step C:** Chart both *answer accuracy* and *tokens spent thinking* versus puzzle complexity, then peek inside every CoT trace to see when (or if) correct intermediate states appear.  
Essentially, the author’s logic is: *If LRMs possess general reasoning, they should (i) outshine non-thinking twins given equal compute, (ii) scale gracefully with complexity, and (iii) show reliable, self-correcting traces.* When any of those fail, alarms ring.

---

### 5\. Three Complexity Regimes — The headline finding

1. **Low Complexity (easy puzzles)**  
	*Surprise!* Plain LLMs often beat their thinking-heavy siblings, and do it with fewer tokens. Overthinking is real.
2. **Medium Complexity (sweet spot)**  
	LRMs finally justify their extra cogitation: they pull ahead, albeit at a hefty token cost.
3. **High Complexity (uh-oh zone)**  
	Both model types crash to **zero accuracy**. Worse, LRMs begin **thinking less** even while tasks get harder — a counter-intuitive scaling limit. Okay, so what does this mean? Even with plenty of token budget left, the models *choose* (or are forced) to give up.

---

### 6\. Peeking Inside the Thought Cloud — What the traces reveal

- Over easy puzzles, LRMs often hit the right answer early, then wander through wrong alternatives — classic “over-explaining to the teacher” syndrome.
- At medium levels, correct solutions crop up later in the trace, suggesting some genuine search.
- Once past the critical complexity, correct states vanish entirely; the trace shrinks, hinting at a learned “abort early” reflex. Wow. Let’s unpack that: the model seems to *sense* hopelessness and stops thinking, wasting neither tokens nor, unfortunately, further effort.

---

### 7\. Evidence Strength Check — How solid is the proof?

- **Empirical muscle:** Thousands of puzzle runs, token-matched controls, and simulator-based step checking = strong experimental hygiene.
- **Generality caveat:** Puzzles are synthetic; real-world reasoning may draw on knowledge, not just pure planning.
- **Compute fairness:** Equal token budgets are admirable, yet hardware latency/impatience issues in production deployments aren’t modeled.  
	Verdict: The evidence is robust *within* the defined scope but should be read as “planning limits” more than “all-purpose reasoning doom.”

---

### 8\. Open Questions Flagged by the Author

- **Why do LRMs ignore explicit step-by-step algorithms placed in the prompt?**
- **Is collapse due to finite context, RL training artifacts, or something more fundamental?**
- **Can curriculum learning or external search modules postpone the critical threshold?**  
	You get the idea: plenty of fertile ground for the next research sprint.

---

### 9\. Historical Breadcrumbs — Placing the puzzles in context

- **Tower of Hanoi** was invented by French mathematician Édouard Lucas in 1883. [en.wikipedia.org](https://en.wikipedia.org/wiki/Tower_of_Hanoi?utm_source=chatgpt.com)
- The **Missionaries-and-Cannibals** river-crossing puzzle dates back at least to an 1891 description. [blogs.sas.com](https://blogs.sas.com/content/sgf/2022/02/15/missionaries-and-cannibals-problem/?utm_source=chatgpt.com)  
	These century-old brain-teasers are still tripping up billion-parameter models — a delightful irony!

---

### 10\. “This wasn’t in the original text, but…” — A metaphor to remember

Picture LRMs as **marathon runners on a treadmill**. At first they jog leisurely (easy puzzles), then huff and puff through middle miles (medium complexity). But crank the belt just a bit faster and — smack! — they slam the emergency stop, stepping off before collapsing. The takeaway? Current training tricks give them stamina only up to a preset pace.

---

### 11\. Why You Should Care — Persuasion moment

- **Design insight:** If you’re building AI agents, don’t assume more tokens = deeper thought. Past a threshold, you’re burning cash for theatrics.
- **Benchmarking wisdom:** Swap contaminated benchmarks for *dial-a-difficulty* puzzles to spot failure modes early.
- **Research call-to-arms:** The next leap may require *architectural* innovation (symbolic modules, external memory) rather than ever-longer CoTs.

---

### 12\. Lightning Recap

> LRMs shine on mid-level problems but overthink the easy ones and abandon the hard ones. Their current “thinking” is real yet brittle, bound by a mysterious complexity ceiling.

And there we have it. Armed with first principles, fresh data, and a dash of historical spice, the Piece invites us to rethink what “thinking” truly means — and why genuine reasoning in machines might still be an illusion worth chasing.