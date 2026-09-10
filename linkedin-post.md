# LinkedIn post (draft)

**Hook options (pick one):**

A) OpenAI's Navier–Stokes result is 220 pages of analysis. The agent design behind it fits on one diagram.

B) 10,000 agents, 88 hours, one checked proof. Here is how the swarm was actually organised, with no equations.

---

**Body:**

Last week OpenAI said a swarm of AI agents resolved the Navier–Stokes problem, one of the seven Millennium Prize questions.

Most coverage stopped at "10,000 agents". I wanted to know how they were set up. So I read OpenAI's description and the public Lean repository and mapped the system.

What the swarm actually looked like:

1. Groups, not one chat. Agents were split into groups. Each group got a different framing of the same problem: some told to prove smoothness, others to build a counter-example. Agents only talked inside their own group.

2. Same recipe per agent. An internal model beyond GPT-6 Astra, a cached copy of the internet, and a code runner. That is it.

3. Warm-up first. ~100 agents spent ~50 hours on the easier Euler problem. Their result was handed to the main groups as a starting point.

4. Humans steered, they did not solve. They chose framings, moved compute, swapped in a newer model mid-run, and used Codex to merge the best ideas across groups and re-prompt them.

5. A machine had the last word. GPT-6 Astra rewrote the argument in Lean 4 (17 hours). 2,659 files, zero unproven gaps, three standard axioms. Anyone can re-run the check.

The pattern that transfers to ordinary agent systems: diversity by framing, isolated groups with a deliberate merge step, warm up on the easier cousin, and a mechanical gate at the end instead of a human review.

I published the interactive architecture map, the timeline, and the source-linked diagram (pinned to the exact commit) here:
https://nikhilmane.com/nse-agent-swarm-architecture/

Figures are as reported by OpenAI. Repo and diagram sources on GitHub in the first comment.

#AI #Agents #MultiAgent #OpenAI #Engineering

---

**First comment:**
Repo with the Archify diagram sources and validation receipts: https://github.com/n1khilmane/nse-agent-swarm-architecture
OpenAI's write-up: https://openai.com/index/navier-stokes-solution/
Lean formalization: https://github.com/openai/NavierStokesAndEuler

**Image to attach:** `assets/share-card.png` (1200×630) or `assets/architecture.png`.
