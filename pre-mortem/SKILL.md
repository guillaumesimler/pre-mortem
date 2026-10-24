---
name: "pre-mortem"
description: "Multi-persona pre-mortem of a plan or decision before commitment, or of an acquisition inside a due diligence: sealed success and failure groups, people's input, blind synthesis, one-page view or deck. Use for /pre-mortem or to stress-test a plan."
---

# Pre-mortem

Before a decision is committed, assume it has already played out, then ask why. Klein's pre-mortem asks "it failed: why?"; the mirror ("it succeeded beyond the plan: why?") tests whether the plan knows what it depends on. This skill runs both frames with a panel of persona agents and, where there are people in the room, with them too, and keeps every writer independent of every other until a separate agent reads the lot.

**Status:** draft v0.7.1, 2026-10-24. Design ruled by the user. Run 1 on a teaching case found the likely, manageable risks and missed what a class of students found: the people at the top falling out, promises the product could not keep, a catastrophic product failure. v0.3 aimed at the extremes and seated the insiders first; run 2 found all three of the class's factors and kept the panel's own. Run 3, a backtest on a real MBO, turned the deal's own terms into the failure mechanism the buyers had missed; v0.4 adds team first, factor titles, a cap on types, a recount from the key and a rule for real people; v0.4.1 marks invented events as well as figures, flags specialist claims for a specialist, and keeps user-given traits at full strength; v0.4.2 asks at the brief checkpoint what the user read and judged secondary, since a backtest's missed factor had been read and left out of the brief; v0.4.3 gives each seat slide of the full presentation a profile panel beside its points, since a seat's points read better next to who wrote them. Runs 4 and 5, a personal decision and then a municipal building project, showed two things: people write outcomes while personas write mechanisms, so the synthesis splits them by format rather than by substance; and on an insider subject the run is bounded by what the brief can know, since most types rested on facts the brief lacked. Run 5c gave the same seats the subject owner's facts: the right bodies were named and a refuted type disappeared, but invented facts per point did not fall, so owner facts change which questions the run asks, and of whom, not how many. Run 6, a panel-only backtest on an acquisition, found the leadership set-up the user had called the deal's original sin without being told; v0.4.4 keeps alternatives out of a run, keeps the side draw from the user, and makes panel-only a mode. Run 7 re-ran run 6 with role-only cards: every core type held, the mechanisms that vanished traced to the user's portraits, and the role-only writers found a skills mechanism the portraits had crowded out; v0.4.5 adds the insider mode, which runs both and renders the difference. v0.5.0 adds DD mode, the run inside `company-dd`'s acquisition lens: a fixed search-fund cast of seven, each card written on both sides by separately spawned agents, the outputs routed to the DD's kill and value hypotheses and its information requests; it replaces Version 2; v0.5.1 renumbers the runs to match the user's record and adds runs 4 to 5c. The lesson across runs 5c and 7: the brief carries the run, not the cards, so effort goes into the brief first. v0.6.0 rules the lessons from runs 4 to 7: every point states an outcome and the mechanism that produced it, and the synthesis groups by mechanism; the brief checkpoint tests that the run holds one decision and comes back to the user when it does not; recordings may feed the brief and the writers, with the checkpoint centred on validating the brief; specialist claims always sit outside the brief and are marked, unless a person writing is that specialist; a larger context gets four seats a side; the thin-brief warning is computed; a personal plan has its own section; the documents that would settle the run are listed after it, never asked for before it; the obvious goes into the brief as known and expected, never as a ban; every checkpoint asks one question at most. Run 8 ran the skill on itself, the first v0.6.0 run: an MBA course adopts it, with the author writing by hand on photographed sheets, which the transcription read with one ambiguity settled at the checkpoint. The types it found sat in the deployment more than in the method: personal outputs filed against the never-filed rule, paid against free accounts, one student holding every sheet. A model round re-ran the panel and the synthesis on three model tiers: those three types held on every tier, while the smallest tier invented named people, drifted off its seats, tagged every line as assumed and read the split between triumph and disaster as contradictions, so its output read as confident and was less checkable. Re-running on the same model moved the lesser types about as much as changing the model did, and the computed thin-brief share moved from 14 to 22 of 23 on identical input, because marks covered invented future events. In every run the person's shorter points formed a type of their own, so the blind form does not hide form. v0.7.0 names the model behind the panel and the synthesis in every output and sets a floor; makes role-only cards the default for real people, with a portrait only on the user's explicit request, marked as such; limits [ASSUMED] to facts about the situation on the decision date; and states in every output that the orchestrator saw every sheet and the key. Run 9 was the first run on v0.7.0. v0.7.1 keeps at least one persona on every side, however many people or teams write: the panel's value is that it says what the room does not, and more human writers do not replace it, so the seats rise rather than the panel disappearing; teams on one side do not compare sheets. Not yet tested: DD mode, the v0.7.1 seating.

## The rules that make it work

These are the design. A run that breaks one says so in its outputs.

0. **Go to the extremes.** The likely, manageable risks are what an ordinary plan review already covers. The pre-mortem earns its place on the outcome nobody would write into the plan: the disaster people still talk about, the triumph nobody planned for. Writers rank by damage, not by likelihood, and nothing is dropped for being far-fetched; an extreme is judged by the kind of failure it belongs to and by whether a warning sign could show it coming.

1. **Every writer is alone.** Each persona is a separate subagent that sees only the plan brief, its own persona card and its frame: never another persona, the other side, the people's input or the conversation. Klein's method works only if every writer, a person or a group, writes before hearing anyone else; groups may talk within themselves, never across. In a small company the boss's view leaks and the room converges. Separate agents give the independence the room cannot.
2. **Split, never mirror.** The + group writes the success frame, the - group the failure frame. No agent and no person writes both. One mind asked for both produces mirror images ("the team worked well" / "the team kept arguing"), which carry no information.
3. **People first, panel hidden.** People write on their drawn side before they see anything from the panel. The panel's output is not shown, summarised or hinted at until the people's input is in and confirmed.
4. **The synthesis is blind.** Before the synthesis, every point is cut to the same form (outcome and mechanism), spelling fixed, shuffled under neutral IDs, so the synthesis agent cannot tell a person's point from a persona's. The full points come back in the deck.
5. **Chance is drawn in code.** Side assignment and the order of points are drawn with a random generator, never chosen by the model.
6. **The brief carries sources.** Every fact in the plan brief names its source; anything without one is labelled HYPOTHESIS, and the panel may treat it as wrong.
7. **Team first.** The people who must carry the plan come before everything else: who decides, who holds which role, what binds them to each other (a mandate, a pact, a tie-break). Until that is settled, every other check is secondary. The first check before committing is always the team's.
8. **The decision is never delegated.** The skill ends with the decisions that are needed, not with a verdict: which risks to accept, which to mitigate, which trigger would stop the plan, and the conversation with the real people involved stay with the user.
9. **Outcome through mechanism.** Every point, from a persona or a person, says what the outcome is at the horizon (a concrete situation, and for whom) and through which mechanism the decision got there. An outcome alone is a scene nobody can act on; a mechanism alone is an argument with no stakes. Without the pair, people write outcomes and personas write mechanisms, and the synthesis splits them by format rather than by substance (runs 4 and 5). The synthesis groups by mechanism and lists the outcomes each mechanism produced, so a person's outcome and a persona's mechanism meet in one type.
10. **Specialist claims sit outside the brief.** Law, regulation, tax, accounting rules and standards that a writer brings from their own knowledge are never findings of the run. Every output marks them as outside the brief, to check with a specialist, unless a person writing by hand is that specialist (step 7, Specialist claims).

## Invocation

`/pre-mortem [plan] [people=N] [horizon=...] [seats=3] [backtest] [insider] [dd]`

- **plan:** pasted text, an attached document, or a description given in conversation.
- **people:** how many people or groups write by hand; ask if not given. `people=0` is the panel-only mode (below).
- **horizon:** when success or failure would be visible. If not given, propose one by decision type and confirm: a hire 12 months, a product launch 12 to 18 months, a reorganisation 12 months, an acquisition 24 to 36 months.
- **seats:** seats per side: 3 for a small decision (a hire, a launch, one site), 4 for a larger context (an acquisition, a reorganisation, several sites or many stakeholders). Propose one at the brief checkpoint; the user confirms. When the people would fill a side, the seats rise so that every side keeps a persona (step 2).
- **backtest:** the plan is a past decision whose outcome is known (see step 1). Propose `people=0`: the user knows the outcome, and anything they write carries it.
- **insider:** the user knows the decision-makers and the house culture and gives portraits of them. The run is made twice (step 3, Insider mode). Offer it when the user describes real people they know; the portrait run is made only on the user's explicit request (step 3, Real people).
- **dd:** the run inside a due diligence (DD mode, below). It sets the frame, the horizon, the cast, `people=0` and the outputs.

**Panel only (`people=0`).** Every seat goes to the panel; every checkpoint stays. Use it for a backtest, or when the user declines to write a side (they were not there, or know they carry prejudices about the people). The outputs say *no hand-written input*, and the People vs panel bucket is dropped. It differs from an unattended run in that the user still confirms the brief, the cast and the outputs.

**DD mode (`dd`).** The run inside a due diligence: `company-dd` calls it at its first gate under the acquisition lens, and `/pre-mortem dd` runs it on its own. It is panel-only and role-only, with a fixed frame, a fixed cast and a full table.

- **Frame.** The decision is "we buy the company on the terms in the brief". The decision date is the day the DD's first gate is confirmed; closing follows six months later; the outcome date is 60 months after closing, the end of a normal holding period, so triumph and disaster are judged at the exit. The six months between the DD and closing are inside the story: what happened at announcement, signing and before closing (a customer using a change-of-control clause, a key person leaving, the staff consultation, the financing) is fair material. The horizon is the mode's; it is not proposed.
- **Brief.** Written before the first filing is read, so the reading cannot shape it. It holds the deal thesis, the indicative terms (price range or multiple, acquisition debt, vendor loan, earn-out, rollover, who runs the company from closing) and what the inventory and the registers show (legal form, owners, sites, headcount band). No figure from the statements. A term the user has not fixed is marked HYPOTHESIS. The brief is thin by design, so every output opens with *DD mode: every type is a hypothesis for the DD to test*, in place of the thin-brief warning. The checkpoint question stays: what did you read (a teaser, a CIM, a call with the owner) and judge secondary?
- **Cast.** Seven cards, role-only: the buyer does not know the target's people, so no traits and no rivalries. If the user knows them and supplies portraits, propose insider mode on top. Team first: the first four carry the deal.
  1. **The investor on the board:** a search-fund investor holding a board seat for the investor group. Wins on the exit multiple and on the searcher proving the model; loses capital and standing with the co-investors.
  2. **The CEO:** the searcher who runs the company from closing. When the searcher is the user, the card stays role-only; how the user says he reads the situation goes on as *self-description* (Self-portraits).
  3. **The seller:** the outgoing owner-manager, staying through a transition, paid partly through a vendor loan or an earn-out where the terms say so. Wins if the company he built survives and he is paid; loses if he is sidelined or his vendor loan is subordinated in a crisis.
  4. **The key manager:** the second-line manager the business depends on, such as the sales head who holds the largest accounts or the technical lead who holds the process. The role is named from the brief, or asked at the checkpoint. Decides whether to stay.
  5. **The acquisition lender:** the bank or debt fund financing the purchase, not the target's house bank. Wins on repayment; reads the covenants.
  6. **The employee representative:** a member of the CSE, the Betriebsrat or the Swiss Personalkommission; where none exists, the longest-serving employee speaking for the floor.
  7. **The largest customer's buyer:** the account that would hurt most to lose.

  The checkpoint can adapt a card (which key manager, which lender, which customer) or kick it for another persona in the same role; it does not drop a role. The outputs name roles, never the target's people.
- **Full table, no side draw.** Every card writes on both sides, through two subagents spawned separately, each in a fresh context that has never held the other side, its own earlier output or any other card. Fourteen writers, seven a side. The side draw exists to stop the casting from stacking a side; a full table cannot stack one, so there is no draw, and the log says so. Seat labels S1 to S14 are shuffled as usual, so the synthesis cannot pair the two seats of a card.
- **Counting by card.** The key records each seat's card, and the recount counts distinct cards as well as seats: a convergent type needs three cards, the two seats of one card counting once. A swing factor named only by the two seats of one card is labelled *same card*: the card's own knowledge steered both, so it is weaker evidence than one named by two cards.
- **People.** `people=0` by default. A person may write only before reading the filings, and takes a seat on top of the full table.
- **Outputs.** `premortem.md` in the DD's working folder, with the key beside it as `premortem_key.json`; `company-dd` reads them:
  - failure types → **kill hypotheses** (K1, K2 ...), each with its most extreme disaster and its leading indicator;
  - success types → **value hypotheses** (V1, V2 ...), each the condition that had to be true for its most extreme triumph;
  - assumptions to verify, and every [ASSUMED] fact a type rests on → **information requests**;
  - unwatchable types → **protections to discuss with counsel** (warranty, indemnity, escrow, earn-out, warranty and indemnity insurance): a risk nobody can watch is priced or insured, not monitored;
  - swing factors → **valuation sensitivities**;
  - specialist claims → **counsel questions**;
  - the checks before committing, team first, as in 8a.

  The one-page view and the deck are made on request. A run whose brief and cast were not confirmed at the gate (an unattended run) marks every output *unreviewed*.

**Personal plans.** A decision about one person's life (health, sport, a move, a career step, a family choice) rather than an organisation's. There is no flag: name it at the brief checkpoint. Four changes:

- **Cast from the person's circle.** Library: the GP, a specialist or physio, a parent, a close friend, a coach or teacher, the partner, the children. The three axes of diversity still apply.
- **Team first, adapted.** The person the plan is about takes the first seat, writing by hand where they agree to, otherwise as a persona built from what the user gives. If they do not write, the headline says so. The team's check asks who decides with this person and who carries the plan with them.
- **Not going ahead counts.** The + frame admits stopping in time, or choosing not to go on, as a triumph when it was the right call. In a personal decision that is often the best outcome, and a frame that only lets the plan succeed hides it.
- **Health and private life.** When the body or health is the subject, health facts are used only as the brief states them, with their source; no writer invents a diagnosis, an injury or a treatment, and nothing about private or family life beyond the brief. The outputs stay private and are never filed to a vault or to memory.

## What the surface must offer

- **Subagents** (a tool that runs an agent in its own context). Without one, the panel cannot be independent. Say so before starting and offer two choices: run on a surface that has subagents, or run anyway with every output marked *panel not independent*.
- **Code execution** for the draws. Without it, ask the user to toss a coin for each draw and record that the draw was manual.
- **Image reading** for photographed sheets. Without it, the people type their points.
- **A capable model.** The panel and the synthesis run on the middle model tier or above. Every output names the model that ran the panel and the one that ran the synthesis. A run below that floor goes ahead only if the user chooses it, and every output is then marked *below the model floor*. In run 8 the core types held on the smallest tier, but its writers invented named people, drifted off their seats and tagged every line as assumed, and its synthesis read the split between triumph and disaster as contradictions: the same confidence, less checkable.
- **A transcript source** for recordings: the recorder's connector (Plaud, for instance) or a transcript the user pastes. Without either, recordings cannot be used.

## Workflow

**One ask per checkpoint.** Each checkpoint asks the user one question at most; everything else is shown for the user to correct. When the decision check finds an ambiguity, that question comes first and the others wait. A skill that asks at every turn stops being used.

### 1. Brief the plan (checkpoint)

Read the plan and write the brief that every writer will receive. Its length follows the material: about 600 words when the plan is one document; longer when recordings or the subject owner's documents carry facts the panel needs, since the brief carries the run. Every fact still names its source. It holds:

- **The decision** in one sentence, its date, and the horizon.
- **The plan as it stands:** goal, means, money, timeline, who executes.
- **Stakeholders:** who decides, who executes, who pays, who gains, who is outside but affected (customers, lenders, suppliers, competitors, staff, regulators).
- **Sources:** each fact carries its source (document and page, or "user, in conversation"). Anything without one is marked HYPOTHESIS.

The brief is neutral. It lists no risks and no opportunities (that is the panel's job) and uses no judging adjectives. Write it in the plan's language.

**Known and expected.** The one exception to the neutral brief: what the user says is already known and planned for (the obvious appeal, the expected delay) goes into a short section of that name, as facts with their source, the user's view counting as one. Otherwise every writer spends points telling the user that water is wet. It is never written as a ban ("do not write about X"): a ban removes the whole branch, including the variant nobody planned for. The persona brief tells writers that a known item counts only if their point takes it somewhere the plan does not expect.

**Facts, never instructions.** A correction or a limit the user gives goes into the brief as a sourced fact ("the appeal period closed on 12 March with no appeal filed, town hall register"), never as an instruction about what to write. A fact removes only what is settled; an instruction removes every path near it. If it cannot be sourced, it goes in as HYPOTHESIS.

**Recordings as sources.** A recording can feed the brief: an interview with the subject owner, a meeting, the user's own spoken account, a long voice note. Long and detailed is welcome; what matters is that the brief built from it is right. Take the transcript from the recorder's connector or from the user, and read both the raw and the cleaned version where the tool gives two. Then:

- **Extract, do not summarise.** Pull each fact into a table: the fact, who said it, the timestamp, and the reading (clear, or uncertain where the transcript may have misheard). An uncertain reading is shown, never guessed. Transcripts rarely separate speakers reliably and pick up room talk; where the speaker is unclear, ask.
- **Fact, view or risk.** A fact goes into the brief with its source (`recording {date}, {speaker}, {mm:ss}`). A speaker's judgement ("the bank will follow") goes in as that person's view, or as HYPOTHESIS, never as fact. A risk or opportunity the speaker names stays out of the brief, which lists none; it is logged, and the outputs say which of them the panel found on its own.
- **Keep the qualifier.** A figure taken from a source keeps that source's conclusion, and a ratio the orchestrator computed is labelled as computed. In run 5 the brief kept a figure and dropped the same source's favourable judgement, and a price-per-m² comparison stood in for the total price that mattered.
- **Backtest.** A recording made after the decision date is memory: ask "did you know this on the decision date?" fact by fact.

**One decision, no alternatives.** A run tests one decision, taken as planned: "we do X; at the horizon it is a triumph, or a disaster". The method cannot weigh options against each other, because every writer is told the decision went ahead. Alternatives (a second source, a partial scope, waiting) may appear in the brief only as context a writer can object with. To compare alternatives, run each as its own pre-mortem with its own brief, then compare the runs.

**Check the decision before the checkpoint.** The decision sentence names one action, who takes it and when, taken as planned. Ambiguity shows up as options ("buy the site or lease it"), conditions ("if the bank agrees"), a sequence of decisions whose later steps are open, a scope that reads two ways, or plan documents that describe different versions. When any of these shows, do not pick one: come back to the user with the elements found in the plan, each candidate decision in one sentence with what it would change in the brief, and ask which one this run tests. The others become their own runs. In DD mode the same check applies to the terms: two deal structures are two runs.

**Backtest.** The brief is built only from documents dated on or before the decision date. List those documents with their dates. Nothing learned afterwards enters, including the user's later reading of events; if the user supplies context from memory, ask "did you know this on the decision date?" and drop it if not. The outcome is never mentioned.

**Checkpoint:** show the brief, the horizon, the proposed seats per side (3 or 4) and the result of the decision check. When recordings fed the brief, show the extraction table beside it, with what was left out and why: the orchestrator's cuts are a filter too. Ask one question: "What did you read and judge secondary? Put it in." The panel can only weigh what the brief contains, and the brief-writer's own judgement is the filter a pre-mortem exists to get past. The user confirms or edits, fact by fact where the brief came from a recording. Nothing else starts before this.

### 2. Seat the table (draw in code)

Each side has `seats` seats. People take theirs first; the panel fills what is left. A group writing one sheet counts as one seat.

**At least one persona a side.** Every side keeps at least one panel seat, however many people or teams write. Personas have no career at stake and say what the room does not; more human writers, sharing one culture and one boss, do not replace that. When the people on the larger side would fill it, the seats per side rise to that side's people plus one, on both sides, so the sides stay equal and their counts comparable.

Run this, with the people's labels (names or "Group A"):

```python
import secrets

def seat(people: list[str], seats_per_side: int = 3) -> dict:
    """Assign people to + or - at random; with two or more, never all on one side.

    Every side keeps at least one persona: seats per side rise when people would fill a side.
    """
    rng = secrets.SystemRandom()
    pool = list(people)
    rng.shuffle(pool)
    big, small = rng.sample(["+", "-"], 2)       # which side takes the odd one out
    cut = len(pool) - len(pool) // 2
    sides = {big: pool[:cut], small: pool[cut:]}
    seats_per_side = max(seats_per_side, len(sides[big]) + 1)
    panel = {s: seats_per_side - len(sides[s]) for s in ("+", "-")}
    return {"people": sides, "panel_seats": panel, "seats_per_side": seats_per_side}
```

| Mode | People or teams | The draw | Panel agents (3 seats a side unless raised) |
|---|---|---|---|
| Solo | 1 | You land on + or - | 5 |
| Small team | 2 | One on each side | 4 |
| Small team | 3 | Two on one side, one on the other | 3 |
| Teams | 4 | Two a side | 2: one a side |
| Teams | 5 | Three on one side, two on the other | 3: seats rise to 4 a side |
| Full team | 6 | Three a side | 2: seats rise to 4 a side |
| Large team | 7+ | Split evenly, the odd one out by draw | Seats rise to the larger side plus one; at least one a side |
| Panel only | 0 | No seating draw | 6: all seats; side draw in step 3 |
| DD mode | 0 | No draw: every card writes on both sides | 14: seven cards, twice each |

**Keep the draw from the user.** Log the result; do not show it. Each person learns only their own side, from their own card in step 4c. The user sees who sat where first in the outputs. A user who knows the sides reads the cast checkpoint, and their own writing, through them. The draw is final; a redraw is allowed only if the user says the input was wrong (a miscounted group), and the log records it.

### 3. Cast the personas (checkpoint)

Cast one pool of personas, as many as the panel seats on both sides together, **without deciding their sides**. Once the cast is approved at the checkpoint below, assign sides with a second draw in code, so the casting cannot stack one side. Log the result and keep it from the user, as in step 2:

```python
import secrets

def assign(cards: list[str], panel_seats: dict) -> dict:
    """Assign cast personas to + or - at random, filling the panel seats per side."""
    rng = secrets.SystemRandom()
    pool = list(cards)
    rng.shuffle(pool)
    n = panel_seats["+"]
    return {"+": pool[:n], "-": pool[n:]}
```

**Where personas come from.** Insiders first: whoever decides (the CEO or founder before the board) and whoever executes (the person who must build or deliver what is being sold, and the person who sells it) each get a seat before any outsider. Then the rest of the brief's stakeholders. Then, if seats remain, the library below. Ask the user what role each person writing by hand holds (role only, never what they think), and whether any of them is a specialist in law, tax, regulation, accounting or standards (rule 10). Cast the panel to cover the roles the people do not.

**Diversity is required on three axes, not adjectives:**
- **Stakes:** what the persona wins or loses. No two personas share the same stakes position.
- **Information:** what they know that others do not, and what they do not know.
- **Horizon:** how far ahead they look (next quarter, the year, the decade).

And on the user's three: psyche, experience level, corporate profile (a family SME, a listed group, a start-up, a bank, a public body).

**No caricatures.** No persona is defined by one trait. Each card gives a reason the persona wants the plan to work and a reason to fear it. No villains, no cheerleaders. The temperament line describes behaviour ("has seen two failed integrations and asks for the cash bridge first"), not a label ("cautious").

**Persona card:**

```
Name and role:     first name, role, organisation
Relation:          how they touch this decision
Stakes:            wins if ... / loses if ...
Knows:             what they know that others may not
Does not know:     what is outside their view
Horizon:           how far ahead they look
Temperament:       one line of behaviour
Experience:        level and track record, one line
Corporate profile: the kind of organisation that shaped them
Relationships:     who they depend on, who they compete with, whom they do not trust
```

Relationships are drawn from the roles, not invented as facts of the case: a CTO competes with marketing for budget in any start-up; whether this CTO dislikes this CMO is not on the card. When the user supplies the relationships, they come from the user and are sourced as such.

**Real people.** When the cast uses real people (a backtest, a live deal), the cards are role-only by default: the role, the relation, the stakes typical of the role and what the brief says that role knows. Run 7 showed the core types hold without portraits, and the value of a portrait grows with the exposure it creates. A portrait (traits, rivalries, facts about the person) goes on a card only on the user's explicit request, and that card, the cast table and every output mark it *portrait on request*. When a portrait is requested, the user's descriptions are rewritten as behaviour, never as labels or insults, and the persona brief carries the real-people line (Templates). The outputs are private; anything meant for others is anonymised. The traits the user gives, and what the run says about those people, never go to a vault or to memory.

**Keep the user's traits at full strength.** "No villains" forbids one-trait cartoons, not hard edges. A trait the user gives is rewritten as behaviour and kept whole, and the card says where it shows: "signs off on figures he has not checked when the founder is in the room; in a failure story he names the meeting where he did". A rewrite that sands off the trait that matters gives a persona softer than the person it stands for, and the run loses the very behaviour it was cast for.

**Insider mode (`insider`).** Someone inside, a CEO, a chair, a senior manager, knows two things a role cannot carry: how the decision-makers behave, and what the house does not say aloud (in run 6, a culture that does not pass unflattering detail upward). Sealed writers who carry that knowledge say what would not be said in the board room. The cost: a portrait is the insider's judgement of people as much as their knowledge, and the panel amplifies whatever a card says, fair or not. So an insider run is two runs on the same brief, the same seats and one side draw, made once and reused so the comparison is controlled:

1. **Role-only.** Each card holds the role, the relation, the stakes typical of the role, and what the brief says that role knows. No traits, no rivalries, no facts the user supplied about the person.
2. **Portrait.** The same cards with the user's portraits, at full strength, made only on the user's explicit request and marked *portrait on request*.

Each run goes through steps 4 to 7 on its own, with its own key, shuffle and blind synthesis, and the outputs add the insider difference (step 8c).

**Self-portraits.** An insider cannot see himself from outside, but he can say how he reads the situation and how he sees his people. That goes on his own card as stated and is labelled *self-description*. Traits others would see in him are written by someone else, or left out, and the outputs say which.

**Library (fallback and seed).** House bank credit officer · largest customer's buyer · key supplier's owner · the operations manager who executes · the CFO · a board member or investor · a competitor's sales head · the newest front-line hire · works council or staff representative · auditor or regulator · the longest-serving employee · an outside industry analyst.

**Checkpoint:** show the cast as a table (name, role, the three axes in a few words; no side, which is drawn after this checkpoint), and ask one question with it: who here would think about how the product or deal is classified, licensed or certified? Personas cast by role rarely do, and that question can hold both the worst disaster and the best triumph (in run 2, only the human found health-product status). The user can approve, **kick** a persona (cast a replacement for the same seat) or **adapt** one (edit the card as told). Log each kick and edit with the user's reason if given.

### 4. Write, sealed

**4a and 4b, the panel.** Spawn one subagent per persona, all at once, each with the persona brief (Templates, below) filled from its card, the brief and its frame. Nothing else goes into its context. Check each return: 3 to 5 points, ranked without ties, every field present. A return that fails is sent back once to the same subagent with the defect named; a second failure is kept as is and logged.

**4c, the people.** Give each person (or group) the people's card (Templates): their side, the frame, the rules. They write alone, without discussion, 5 to 8 minutes. A team writing one sheet talks only within itself; teams on the same side do not compare sheets until step 5 is confirmed. On paper or a whiteboard, photographed afterwards; recorded (below); a solo user may type. Until step 5 is confirmed, say nothing about the panel's output. If the user asks to see it early, say once why it is held back; if they insist, show it and mark every output *people not independent*.

**Recorded input.** A person may speak their points instead of writing them. One recording per person, made alone, with the side given privately beforehand. They open with their name, their side and "point 1", and mark each new point (the recorder's highlight button, or "point 2" aloud). People who speak in front of each other are no longer writing alone: record them one after another, out of earshot. Whoever holds the recorder may ask one neutral follow-up per point, "how did it come about?", when a point gives an outcome with no mechanism; the question is on the recording and logged.

### 5. Read the input (checkpoint)

For each photo or recording: transcribe each point verbatim, one row per point, with the photo or the timestamp, the side (from the draw, or as written on the sheet), the author if visible and the rank if written. A word that cannot be read is written `[illegible]`, never guessed. Typed input is taken as is. If the people did not rank, keep the order as written and mark the points *unranked*. For a recording, split points at the markers and show the raw reading beside the cleaned one where they differ.

**Outcome without mechanism.** If a person's point gives an outcome and no mechanism, ask that person, before anything from the panel is shown, how it came about. Their answer joins the point, marked *given at the checkpoint*. If they do not know, the point stays outcome only.

**Checkpoint:** show the transcription table. The user corrects it. Nothing goes further until it is confirmed.

### 6. Strip the source

The orchestrator holds the key; the synthesis agent never sees it.

- **Blind form.** Every point, from the panel or a person, becomes: side, plus one or two sentences stating the outcome and the mechanism that produced it, 15 to 40 words, plain register, spelling corrected. Remove anything that marks the writer: names, "as the CFO I", ranks, indicators, horizons, typos, fragments. Cut the panel's points down; never pad a person's point up.
- **No invention.** If a person's point still states no mechanism after step 5, the blind form carries the outcome alone. That point is then recognisable as human; record it in the run log as a known leak rather than invent a mechanism.
- **Shuffle and label in code.** Shuffle all blind points with `secrets.SystemRandom().shuffle`, then label them P01, P02 ... in the shuffled order. Give each seat a neutral label S1, S2 ... in a separate shuffled order and attach it to its points, so the synthesis can tell three seats agreeing from one seat repeating itself without learning which seats are people.
- **[ASSUMED] and [SPECIALIST] marks.** Personas mark facts they supplied themselves and the specialist knowledge they relied on; people do not. Drop the marks from the blind form, since they would give the panel away, and keep them in the key. The synthesis brief has the synthesis check every point against the plan brief instead.
- **The key** (kept by the orchestrator): ID, seat (persona or person), people or panel, side, rank, the full original point with its [ASSUMED] and [SPECIALIST] marks, the transcription where there is one, and for a person their declared role.

### 7. Blind synthesis

Spawn one new subagent, which has taken no part in the run, with the synthesis brief (Templates), the plan brief and the blind points. It returns types (points grouped by mechanism, the factor that produced the outcome, not by story), the outcomes each type led to on each side, and buckets:

- **Convergent:** the same type found by three or more seats. One seat repeating itself counts once.
- **Lone extremes:** one seat, severity or upside 4-5.
- **Unwatchable:** types with no warning sign anyone could watch. They call for insurance or design, not monitoring.
- **Contradictions:** points that assume different facts about the situation on the decision date (not different outcomes, which the split produces by design), and what would settle it.
- **Assumptions to verify:** from the + side, what has to be true that is not verified on the decision date, and how it could be checked now.
- **Swing factors:** one factor named on both sides independently, as a cause of success and as a cause of failure. Inside one mind a mirror is laziness; arising separately in two sealed groups it marks what the plan hinges on.
- **Cross-side agreement:** a fact both sides imply in common that the plan does not assume. When the success story and the failure story agree, for instance that the money is made in a channel the plan treats as secondary, the plan may be betting on the wrong one.

It also returns, for each type, its most extreme point on each side; the types grouped into 3 to 5 families; and one check before committing per family, with that family's most extreme triumph and disaster. These drive the one-page view (8a).

**Recount from the key.** The synthesis counts seats from neutral labels and can miscount (run 3 credited one type with four writers where the key showed three). Before rendering, the orchestrator recounts writers and points per type from the key, and the outputs use the recount. In DD mode it counts cards as well (DD mode, Counting by card).

Then the orchestrator adds a last bucket from the key, mechanically and without judgement:

- **People vs panel:** types found only by people, only by the panel, or by both. Shown only when people took part.

**Late points.** A point that arrives after the synthesis (for example the user's own point from an earlier session) never enters the blind synthesis. It is added to the right type in the outputs, labelled with where it came from.

**Specialist claims.** Law, regulation, tax, accounting rules and standards always sit outside the brief's elements. A fact the brief sources (a ruling, a permit, a signed clause) is a fact; what a writer says the law makes of it is a specialist claim. After the synthesis, the orchestrator labels every type that rests on such a claim, from the synthesis's flag or a [SPECIALIST] mark in the key, *outside the brief: to check with a specialist*, in every output. The one exception is a person writing by hand whose declared role (step 3) is that specialism: a type that person supports is labelled *from a specialist in the room ({role})*, and points the panel added to it keep the outside-the-brief label. A persona cast as counsel is still the panel. The panel brings knowledge nobody in the room had, and cannot vouch for it: in run 3 the counsel persona's legal mechanisms were the most expert-sounding points of the run and none of them came from the brief.

**A thin brief, computed.** After the recount, from the key: a panel point rests on an assumption when its mechanism carries an [ASSUMED] mark, and a type rests on assumptions when most of its panel points do. When half or more of the types do, every output opens with the warning and the share ("6 of 9 types rest on facts the brief does not contain"): the run has measured the writers' imagination, and its types are questions to check before committing, not findings. The fix is a fuller brief, not a bigger panel. Count the marks on mechanisms, not marks per point: in run 5c a richer brief sharpened the types while marks per point did not fall. The mark covers facts about the decision date only; while it also covered invented future events, the share moved from 14 to 22 of 23 points on identical input in run 8, and the warning fired on every forward run. A brief thin by design (a teaching case, a deliberately sparse test) still gets the warning, reading *thin by design*, with the share. In DD mode the warning is replaced by the mode's own line.

**Documents that would settle it.** After the run, never before it: the orchestrator lists the documents or facts that would settle the run's open questions, taken from the contradictions, the assumptions to verify and the types that rest on [ASSUMED] facts. At most five, ranked by how many types depend on each, each with who holds it. In run 5c this list, made by hand, was a request to six holders. When the thin-brief warning fires, the outputs add that a second run with those documents, on the same seats and draw, is the way to firm the types up; whether to run it is the user's call. In DD mode this list is the information requests.

### 8. Render

Ask which the user wants, or both:

- **8a. One-page view, an artifact page.** No charts: in run 2 the grids were the hardest part to read. In this order:
  1. **Headline** stating what the plan hinges on, as a claim; a one-paragraph lede on who wrote (seats, sides, people and panel).
  2. **The thin-brief warning**, when it applies.
  3. **A key of the families**, each with a solid colour box.
  4. **3 to 5 checks before committing**, one per family, **the team's check first** (rule 7). Each check: a title that **names the success or risk factor itself**, two to six words ("A signed buyers' pact", "Financing secured before the settlement figure", "A written CMO mandate"), not an instruction; the types it covers (with the family's colour box), two or three sentences on what to check, then **one triumph and one disaster** for that family, the most extreme each side wrote, each on its own line and highlighted: a green rule with an up triangle for the triumph, a red rule with a down triangle for the disaster, followed by who wrote it. Colour is never the only signal: the triangle and the words Triumph and Disaster carry it too.
  5. **Documents that would settle it**, the list from step 7, one line each with its holder.
  6. **The detail: worst and best, by type.** One ruled table, one row per type (a mechanism), **most cited first** (by number of writers, then number of points): the family's colour box and type ID, the worst outcome (disaster), the best outcome (triumph), each with its writers, the citation count, and the specialist label where it applies. A type with no story on one side says so and names its flip side if another type holds it.
  7. **A source line**: run number, skill version, the models that ran the panel and the synthesis, who orchestrated (and so saw every sheet, every card and the key: the sealing keeps writers apart from each other and from the synthesis, not from the orchestrator), how seats and sides were drawn, the personas and their sides, and what was added after the synthesis or grouped by the orchestrator rather than by the synthesis.

  Draw the triangles and colour boxes as inline SVG or CSS, never as typed characters. Apply the user's style guide if one is loaded.
- **8b. Full presentation, a deck.** Use the Slides artifact type if this surface has it; otherwise follow the user's deck skill. In order: the checks before committing, one slide each, with its triumph and disaster; the decision, horizon and method (seats, draw result, who wrote by hand); one slide per seat (see below); one slide per synthesis bucket; one slide for the documents that would settle it; last, **decisions needed**: for each check, the three options the user must choose between (mitigate with an owner, set a stop trigger, or accept), left blank.

  **The seat slide, two columns.** On the left three quarters, the seat's points **restored from the key** (for a person: the transcription, then the cleaned point): in full where they fit, otherwise each point's outcome with its leading indicator (- side) or what had to be true (+ side), the full text staying in the run's panel file and the slide's footer saying so. On the right quarter, **the writer's profile**, four or five short lines taken from the persona card: who they are, what they stand to win or lose, what they know, what lies outside their view, how they work. For a person: their role, and how they wrote (alone, side drawn beforehand, on paper or recorded). For a persona of a real person, the profile keeps to the role and the working style the user gave, with nothing on politics, health or private life (the real-people rule). Keep the slide title to one line so both columns fit.
- **8c. The insider difference** (insider mode only). After both syntheses, the orchestrator compares the two runs from their keys, mechanically, type by type and writer by writer, and adds the result to the one-page view as a table and to the deck as one slide:
  - **Held in both:** types and cross-side agreements present in both runs. They come from the situation and the brief, not from the portraits.
  - **Portrait only:** mechanisms that appear only with the portraits, each traced to the card line that seeded it. This is the unsayable layer; the insider owns it as his judgement of people.
  - **Role only:** mechanisms that appear only without the portraits, usually functional ones the portraits crowded out.

  In runs 6 and 7 the leadership set-up held in both; three mechanisms appeared only with the portraits, each traced to a trait the user gave; two functional mechanisms appeared only without them. In a backtest, the role-only run also measures how much hindsight the portraits carry.

Neither output says whether to go ahead.

### Run log

Keep a short log and offer it with the outputs; it documents the process. The models that ran the panel and the synthesis, as each agent reports them; brief versions and edits; portraits made on request, and whose; the two draw results (in insider mode, the one side draw reused by both runs; in DD mode, *full table, no side draw*, and each seat's card); kicks and edits at the cast checkpoint, with reasons; subagent returns sent back; the decision check and how any ambiguity was settled; for a brief built from recordings, the extraction table with its cuts and the risks the speakers named; transcription corrections and follow-ups asked at step 5; leaks recorded in step 6; any rule broken (panel shown early, no subagents, manual draw).

## Templates

### Persona brief

Fill the braces. Use the + or - block for the frame and the matching point format. Write in the plan's language.

```
Work only from this text. Do not search or use tools.

You are {name}, {role} at {organisation}. {relation}.

What you stand to gain or lose: {stakes}
What you know that others may not: {knows}
What lies outside your view: {does_not_know}
How far ahead you look: {horizon_persona}
How you work: {temperament} {experience}. {corporate_profile}

Below is the plan as it stood on {decision_date}. Facts carry their source.
Anything marked HYPOTHESIS was not verified; you may treat it as wrong.

<plan>
{brief}
</plan>

It is now {outcome_date}. The decision was taken as planned.
[DD, in place of the line above] It is now {outcome_date}. The due diligence closed on {decision_date}; the company was bought on {closing_date} on the terms above and has been run for 60 months since. What happened between the due diligence and closing is part of the story.
[-] It was an unmitigated disaster, the kind people in the industry still talk about.
[+] It was a triumph beyond anything anyone planned for, the kind people in the industry still talk about.
[Personal plan, +] A triumph may also be stopping in time, or choosing not to go on, when that was the right call.

You are certain of this. Explain, from your own position, what the outcome is and how it came about.

- Give 3 to 5 points, ranked by how much [-] damage / [+] upside each one did. 1 is the biggest. No ties.
- Do not stop at what was likely. Go to what actually happened in this extreme outcome, however far it goes.
- At least one point is about people: who decided what, who clashed with whom, who left or took over.
- Write from your position: what you saw, what you were part of, whom you dealt with.
- Every point gives both: the outcome (what the situation is at {outcome_date}, and for whom) and the mechanism (how the decision led there). An outcome without its mechanism, or a mechanism without its outcome, is half a point.
- Items the plan lists under "Known and expected" are already planned for. Use one only if your point takes it somewhere the plan does not expect: a different cause, a different outcome, a consequence nobody budgeted.
- Be specific enough that a person could own the point. "Execution slipped", "the market softened" or "the team worked well" are not points unless you say what, who and when.
- When a point rests on a fact about the situation on {decision_date} that the plan does not give (a figure, a rate from your experience, a clause, who holds which role, what someone had already decided), write it as you believe it to be and put [ASSUMED] after it. What happens after {decision_date} is your story and takes no mark.
- When a point rests on specialist knowledge (law, regulation, tax, accounting rules, standards), name the rule or article you rely on and put [SPECIALIST] after it, so a specialist can check it.
- [Real people only] The people named here are real. Do not invent anything about their health, private or family life, or anything that would read as an accusation; keep to what they decide and do in their roles.
- [Personal plan, health the subject] Use the person's health only as the plan states it. Invent no diagnosis, injury or treatment.
- Do not hedge with the opposite scenario.

[-] Format for each point:
RANK:
OUTCOME: the situation at {outcome_date}, concretely, and for whom, one sentence
MECHANISM: how the decision led to this outcome, two or three sentences
LEADING INDICATOR: what was visible early, and when
HORIZON: when the failure became visible

[+] Format for each point:
RANK:
OUTCOME: the situation at {outcome_date}, concretely, and for whom, one sentence
MECHANISM: how the decision led to this outcome, two or three sentences
WHAT HAD TO BE TRUE: a condition that was not verified on {decision_date}
LEADING INDICATOR: what was visible early, and when
HORIZON: when the success became visible

Return only the points.
```

Each point must carry an outcome, a mechanism (how the plan got from the decision date to this outcome) and a leading indicator. A point without a leading indicator is kept; the synthesis marks its type unwatchable.

### People's card

Read aloud or hand out. One per person or group.

```
Side: {+ or -}
It is {outcome_date}. The decision "{decision}" was taken as planned.
[-] An unmitigated disaster.   [+] A triumph beyond anything planned.

Write alone. No talking until everyone has finished. {5 to 8} minutes.
Give 3 to 5 outcomes, the biggest first. Do not hold back on the
extreme ones. One per line or per sticky note: what the situation is,
for whom, and how it came about. Write legibly; the sheet will be
photographed.
[Recorded] Say your name, your side and "point 1", then mark each new
point.
```

### Synthesis brief

```
You are reading the output of a pre-mortem. Writers were split into a +
group (told the plan was a triumph beyond anything planned) and a - group
(told it was an unmitigated disaster). Writers were asked for extremes, not
for likely outcomes: do not discount a point for being far-fetched. Each
wrote alone. Each point carries a neutral seat label (S1, S2 ...): points
with the same label come from the same writer. You do
not know who the writers are, and you must not guess: weigh every point on
its content alone. A short point is not a weak point; rate the cause, not
the writing.

<plan>
{brief}
</plan>

<points>
{blind points: ID, seat, side, text}
</points>

1. Group the points by TYPE: the mechanism that produced the outcome,
   not the story. A supplier who stops delivering and a key engineer who
   quits are one type if both came about through "a single dependence
   nobody owned". A type can hold points from both sides. Give each type
   an ID, a one-line label naming the mechanism, its point IDs, its number
   of distinct seats, and the outcomes its points reached on each side. A
   point that states an outcome without a mechanism joins the type whose
   mechanism fits it best, marked OUTCOME ONLY; do not invent its
   mechanism. A point that only restates an item the plan lists under
   "Known and expected" is not a type: put it on one line, KNOWN, AS
   EXPECTED, with its point IDs. Keep to about ten types: merge before
   you split.
2. Rate each type. Failure: severity 1-5, and how early a warning sign
   would show (early: months ahead / late: weeks ahead / none: no sign
   anyone could watch), naming the sign. Success: upside 1-5, and whether
   the company could absorb it (yes, partly, no), with why.
3. Sort into buckets, one line per entry:
   CONVERGENT - types found by three or more seats. Points from one seat
     repeating itself count once.
   LONE EXTREMES - single-seat types with severity or upside 4-5; say why.
   UNWATCHABLE - types with no warning sign anyone could watch; these call
     for insurance or design, not monitoring.
   CONTRADICTIONS - points that assume different facts about the situation
     on the decision date (not different outcomes, which the split
     produces by design); state the fact and what would settle it.
   ASSUMPTIONS TO VERIFY - from the + side, conditions not verified on the
     decision date, grouped by type; say how each could be checked now.
   SWING FACTORS - one factor named on both sides as a cause of success and
     of failure.
   CROSS-SIDE AGREEMENT - a fact that points on both sides imply in common
     AND that the plan does not assume (for example, both stories make their
     money through a channel the plan treats as secondary). Leave out
     agreements the plan already takes for granted.
   A type may sit in more than one bucket.
4. For every type, name its most extreme point on each side: the worst
   (- side, highest severity) and the best (+ side, highest upside), by
   point ID. Write NONE where a side is empty.
5. Group the types into 3 to 5 FAMILIES of related types (for example
   regulators and trust; people and power; product and supply; money and
   channel). Give each family a short name.
6. For each family, write one CHECK BEFORE COMMITTING: a title that names
   the success or risk factor itself in two to six words ("A signed
   buyers' pact", not "Fix the buyers' pact"), the types it covers, and
   two or three sentences on what to check and why. Then name the
   family's most extreme triumph point and most extreme disaster point,
   by ID. The first check is always the team's: who decides, who holds
   which role, what binds them. Order the rest by what most deserves
   attention before committing. Say why each one is there.
7. Flag every type whose support rests on a fact the plan marks
   HYPOTHESIS, or on a specific fact the plan does not contain at all.
   Agreement among writers measures agreement, not truth. Flag separately
   every type that rests on law, regulation, tax, accounting rules or
   standards a writer supplied: SPECIALIST CLAIM.

Do not recommend whether to go ahead. Do not add causes nobody wrote;
if you see an important gap, list it separately under GAPS, labelled as
yours.
```

## Version 2, folded into DD mode

Version 2 was a fully autonomous run inside a due diligence. DD mode is that run with one checkpoint kept, the DD's own first gate, because the brief-writer's judgement is the filter a pre-mortem exists to get past (step 1). Run unattended, it takes the brief and cast unconfirmed and marks every output *unreviewed*. A run with no checkpoint outside a DD is not built.