---
name: pre-mortem
description: Multi-persona pre-mortem of a plan or decision before it is committed. A sealed success group and a sealed failure group of persona agents, plus any people in the room writing on paper, a blind synthesis, and a one-page view or a full deck. Use for /pre-mortem, "pre-mortem this", or when a plan should be stress-tested before commitment.
---

# Pre-mortem

Before a decision is committed, assume it has already played out, then ask why. Klein's pre-mortem asks "it failed: why?"; the mirror ("it succeeded beyond the plan: why?") tests whether the plan knows what it depends on. This skill runs both frames with a panel of persona agents and, where there are people in the room, with them too, and keeps every writer independent of every other until a separate agent reads the lot.

**Status:** draft v0.4.1, 2026-10-20. Design ruled by the user. Run 1 on a teaching case found the likely, manageable risks and missed what a class of students found: the people at the top falling out, promises the product could not keep, a catastrophic product failure. v0.3 aimed at the extremes and seated the insiders first; run 2 found all three of the class's factors and kept the panel's own. Run 3, a backtest on a real MBO, turned the deal's own terms into the failure mechanism the buyers had missed; v0.4 adds team first, factor titles, a cap on types, a recount from the key and a rule for real people; v0.4.1 marks invented events as well as figures, flags specialist claims for a specialist, and keeps user-given traits at full strength. Not yet tested: photo transcription, the full deck.

## The rules that make it work

These are the design. A run that breaks one says so in its outputs.

0. **Go to the extremes.** The likely, manageable risks are what an ordinary plan review already covers. The pre-mortem earns its place on the outcome nobody would write into the plan: the disaster people still talk about, the triumph nobody planned for. Writers rank by damage, not by likelihood, and nothing is dropped for being far-fetched; an extreme is judged by the kind of failure it belongs to and by whether a warning sign could show it coming.

1. **Every writer is alone.** Each persona is a separate subagent that sees only the plan brief, its own persona card and its frame: never another persona, the other side, the people's input or the conversation. Klein's method works only if everyone writes before anyone speaks; in a small company the boss's view leaks and the room converges. Separate agents give the independence the room cannot.
2. **Split, never mirror.** The + group writes the success frame, the - group the failure frame. No agent and no person writes both. One mind asked for both produces mirror images ("the team worked well" / "the team kept arguing"), which carry no information.
3. **People first, panel hidden.** People write on their drawn side before they see anything from the panel. The panel's output is not shown, summarised or hinted at until the people's input is in and confirmed.
4. **The synthesis is blind.** Before the synthesis, every point is cut to the same form (claim and mechanism), spelling fixed, shuffled under neutral IDs, so the synthesis agent cannot tell a person's point from a persona's. The full points come back in the deck.
5. **Chance is drawn in code.** Side assignment and the order of points are drawn with a random generator, never chosen by the model.
6. **The brief carries sources.** Every fact in the plan brief names its source; anything without one is labelled HYPOTHESIS, and the panel may treat it as wrong.
7. **Team first.** The people who must carry the plan come before everything else: who decides, who holds which role, what binds them to each other (a mandate, a pact, a tie-break). Until that is settled, every other check is secondary. The first check before committing is always the team's.
8. **The decision is never delegated.** The skill ends with the decisions that are needed, not with a verdict: which risks to accept, which to mitigate, which trigger would stop the plan, and the conversation with the real people involved stay with the user.

## Invocation

`/pre-mortem [plan] [people=N] [horizon=...] [seats=3] [backtest]`

- **plan:** pasted text, an attached document, or a description given in conversation.
- **people:** how many people or groups write by hand. 0 is not a v1 mode (see Version 2); ask if not given.
- **horizon:** when success or failure would be visible. If not given, propose one by decision type and confirm: a hire 12 months, a product launch 12 to 18 months, a reorganisation 12 months, an acquisition 24 to 36 months.
- **seats:** seats per side, default 3.
- **backtest:** the plan is a past decision whose outcome is known (see step 1).

## What the surface must offer

- **Subagents** (a tool that runs an agent in its own context). Without one, the panel cannot be independent. Say so before starting and offer two choices: run on a surface that has subagents, or run anyway with every output marked *panel not independent*.
- **Code execution** for the draws. Without it, ask the user to toss a coin for each draw and record that the draw was manual.
- **Image reading** for photographed sheets. Without it, the people type their points.

## Workflow

### 1. Brief the plan (checkpoint)

Read the plan and write the brief that every writer will receive. At most about 600 words:

- **The decision** in one sentence, its date, and the horizon.
- **The plan as it stands:** goal, means, money, timeline, who executes.
- **Stakeholders:** who decides, who executes, who pays, who gains, who is outside but affected (customers, lenders, suppliers, competitors, staff, regulators).
- **Sources:** each fact carries its source (document and page, or "user, in conversation"). Anything without one is marked HYPOTHESIS.

The brief is neutral. It lists no risks and no opportunities (that is the panel's job) and uses no judging adjectives. Write it in the plan's language.

**Backtest.** The brief is built only from documents dated on or before the decision date. List those documents with their dates. Nothing learned afterwards enters, including the user's later reading of events; if the user supplies context from memory, ask "did you know this on the decision date?" and drop it if not. The outcome is never mentioned.

**Checkpoint:** show the brief and the horizon. The user confirms or edits. Nothing else starts before this.

### 2. Seat the table (draw in code)

Each side has `seats` seats. People take theirs first; the panel fills what is left. A group writing one sheet counts as one seat. Run this, with the people's labels (names or "Group A"):

```python
import secrets

def seat(people: list[str], seats_per_side: int = 3) -> dict:
    """Assign people to + or - at random; with two or more, never all on one side."""
    rng = secrets.SystemRandom()
    pool = list(people)
    rng.shuffle(pool)
    big, small = rng.sample(["+", "-"], 2)       # which side takes the odd one out
    cut = len(pool) - len(pool) // 2
    sides = {big: pool[:cut], small: pool[cut:]}
    panel = {s: max(0, seats_per_side - len(sides[s])) for s in ("+", "-")}
    return {"people": sides, "panel_seats": panel}
```

| Mode | People | The draw | Panel agents (3 seats a side) |
|---|---|---|---|
| Solo | 1 | You land on + or - | 5 |
| Small team | 2 | One on each side | 4 |
| Small team | 3 | Two on one side, one on the other | 3 |
| Full team | 6+ | Split evenly, the odd one out by draw | 0: skip step 3 and 4a/4b |

Show the result verbatim. It is final; a redraw is allowed only if the user says the input was wrong (a miscounted group), and the log records it.

### 3. Cast the personas (checkpoint)

Cast one pool of personas, as many as the panel seats on both sides together, **without deciding their sides**. Then assign sides with a second draw in code, so the casting cannot stack one side:

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

**Where personas come from.** Insiders first: whoever decides (the CEO or founder before the board) and whoever executes (the person who must build or deliver what is being sold, and the person who sells it) each get a seat before any outsider. Then the rest of the brief's stakeholders. Then, if seats remain, the library below. Ask the user what role each person writing by hand holds (role only, never what they think), and cast the panel to cover the roles the people do not.

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

**Real people.** When the cast uses real people (a backtest, a live deal), the user's descriptions are rewritten as behaviour, never as labels or insults, and the persona brief carries the real-people line (Templates). The outputs are private; anything meant for others is anonymised. The traits the user gives, and what the run says about those people, never go to a vault or to memory.

**Keep the user's traits at full strength.** "No villains" forbids one-trait cartoons, not hard edges. A trait the user gives is rewritten as behaviour and kept whole, and the card says where it shows: "signs off on figures he has not checked when the founder is in the room; in a failure story he names the meeting where he did". In run 3 a rewrite sanded off the trait that mattered.

**Library (fallback and seed).** House bank credit officer · largest customer's buyer · key supplier's owner · the operations manager who executes · the CFO · a board member or investor · a competitor's sales head · the newest front-line hire · works council or staff representative · auditor or regulator · the longest-serving employee · an outside industry analyst.

**Checkpoint:** show the cast as a table (name, role, side, the three axes in a few words), and ask one question with it: who here would think about how the product or deal is classified, licensed or certified? Personas cast by role rarely do, and that question can hold both the worst disaster and the best triumph (in run 2, only the human found health-product status). The user can approve, **kick** a persona (cast a replacement for the same seat and side) or **adapt** one (edit the card as told). Log each kick and edit with the user's reason if given.

### 4. Write, sealed

**4a and 4b, the panel.** Spawn one subagent per persona, all at once, each with the persona brief (Templates, below) filled from its card, the brief and its frame. Nothing else goes into its context. Check each return: 3 to 5 points, ranked without ties, every field present. A return that fails is sent back once to the same subagent with the defect named; a second failure is kept as is and logged.

**4c, the people.** Give each person (or group) the people's card (Templates): their side, the frame, the rules. They write alone, without discussion, 5 to 8 minutes. On paper or a whiteboard, photographed afterwards; a solo user may type. Until step 5 is confirmed, say nothing about the panel's output. If the user asks to see it early, say once why it is held back; if they insist, show it and mark every output *people not independent*.

### 5. Read the input (checkpoint)

For each photo: transcribe each point verbatim, one row per point, with the photo, the side (from the draw, or as written on the sheet), the author if visible and the rank if written. A word that cannot be read is written `[illegible]`, never guessed. Typed input is taken as is. If the people did not rank, keep the order as written and mark the points *unranked*.

**Checkpoint:** show the transcription table. The user corrects it. Nothing goes further until it is confirmed.

### 6. Strip the source

The orchestrator holds the key; the synthesis agent never sees it.

- **Blind form.** Every point, from the panel or a person, becomes: side, plus one or two sentences stating the claim and its mechanism, 15 to 40 words, plain register, spelling corrected. Remove anything that marks the writer: names, "as the CFO I", ranks, indicators, horizons, typos, fragments. Cut the panel's points down; never pad a person's point up.
- **No invention.** If a person's point states no mechanism, the blind form carries the claim alone. That point is then recognisable as human; record it in the run log as a known leak rather than invent a mechanism.
- **Shuffle and label in code.** Shuffle all blind points with `secrets.SystemRandom().shuffle`, then label them P01, P02 ... in the shuffled order. Give each seat a neutral label S1, S2 ... in a separate shuffled order and attach it to its points, so the synthesis can tell three seats agreeing from one seat repeating itself without learning which seats are people.
- **[ASSUMED] marks.** Personas mark facts they supplied themselves; people do not. Drop the marks from the blind form, since they would give the panel away, and keep them in the key. The synthesis brief has the synthesis check every point against the plan brief instead.
- **The key** (kept by the orchestrator): ID, seat (persona or person), people or panel, side, rank, the full original point with its [ASSUMED] marks, the transcription where there is one.

### 7. Blind synthesis

Spawn one new subagent, which has taken no part in the run, with the synthesis brief (Templates), the plan brief and the blind points. It returns types (points grouped by the kind of failure or success, not by story) and buckets:

- **Convergent:** the same type found by three or more seats. One seat repeating itself counts once.
- **Lone extremes:** one seat, severity or upside 4-5.
- **Unwatchable:** types with no warning sign anyone could watch. They call for insurance or design, not monitoring.
- **Contradictions:** points that assume different facts about the situation on the decision date (not different outcomes, which the split produces by design), and what would settle it.
- **Assumptions to verify:** from the + side, what has to be true that is not verified on the decision date, and how it could be checked now.
- **Swing factors:** one factor named on both sides independently, as a cause of success and as a cause of failure. Inside one mind a mirror is laziness; arising separately in two sealed groups it marks what the plan hinges on.
- **Cross-side agreement:** a fact both sides imply in common that the plan does not assume. When the success story and the failure story agree, for instance that the money is made in a channel the plan treats as secondary, the plan may be betting on the wrong one.

It also returns, for each type, its most extreme point on each side; the types grouped into 3 to 5 families; and one check before committing per family, with that family's most extreme triumph and disaster. These drive the one-page view (8a).

**Recount from the key.** The synthesis counts seats from neutral labels and can miscount (run 3 credited one type with four writers where the key showed three). Before rendering, the orchestrator recounts writers and points per type from the key, and the outputs use the recount.

Then the orchestrator adds a last bucket from the key, mechanically and without judgement:

- **People vs panel:** types found only by people, only by the panel, or by both. Shown only when people took part.

**Late points.** A point that arrives after the synthesis (for example the user's own point from an earlier session) never enters the blind synthesis. It is added to the right type in the outputs, labelled with where it came from.

**Specialist claims.** A type whose support rests on law, regulation, tax or standards that a writer supplied from its own knowledge is labelled *to check with a specialist* in every output. The panel brings knowledge nobody in the room had, and cannot vouch for it: in run 3 the counsel persona's legal mechanisms were the most expert-sounding points of the run and none of them came from the brief.

**A thin brief.** If most types rest on facts the brief does not contain, say so at the top of every output: the run has measured the writers' imagination, and its types are questions to check before committing, not findings. The fix is a fuller brief, not a bigger panel.

### 8. Render

Ask which the user wants, or both:

- **8a. One-page view, an artifact page.** No charts: in run 2 the grids were the hardest part to read. In this order:
  1. **Headline** stating what the plan hinges on, as a claim; a one-paragraph lede on who wrote (seats, sides, people and panel).
  2. **The thin-brief warning**, when it applies.
  3. **A key of the families**, each with a solid colour box.
  4. **3 to 5 checks before committing**, one per family, **the team's check first** (rule 7). Each check: a title that **names the success or risk factor itself**, two to six words ("A signed buyers' pact", "Financing secured before the settlement figure", "A written CMO mandate"), not an instruction; the types it covers (with the family's colour box), two or three sentences on what to check, then **one triumph and one disaster** for that family, the most extreme each side wrote, each on its own line and highlighted: a green rule with an up triangle for the triumph, a red rule with a down triangle for the disaster, followed by who wrote it. Colour is never the only signal: the triangle and the words Triumph and Disaster carry it too.
  5. **The detail: worst and best, by type.** One ruled table, one row per type, **most cited first** (by number of writers, then number of points): the family's colour box and type ID, the worst (disaster) story, the best (triumph) story, each with its writers, and the citation count. A type with no story on one side says so and names its flip side if another type holds it.
  6. **A source line**: run number, skill version, how seats and sides were drawn, the personas and their sides, and what was added after the synthesis or grouped by the orchestrator rather than by the synthesis.

  Draw the triangles and colour boxes as inline SVG or CSS, never as typed characters. Apply the user's style guide if one is loaded.
- **8b. Full presentation, a deck.** Use the Slides artifact type if this surface has it; otherwise follow the user's deck skill. In order: the checks before committing, one slide each, with its triumph and disaster; the decision, horizon and method (seats, draw result, who wrote by hand); one slide per seat with its points **in full, restored from the key** (for a person: the transcription, then the cleaned point); one slide per synthesis bucket; last, **decisions needed**: for each check, the three options the user must choose between (mitigate with an owner, set a stop trigger, or accept), left blank.

Neither output says whether to go ahead.

### Run log

Keep a short log and offer it with the outputs; it documents the process. Brief versions and edits; the two draw results; kicks and edits at the cast checkpoint, with reasons; subagent returns sent back; transcription corrections; leaks recorded in step 6; any rule broken (panel shown early, no subagents, manual draw).

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
[-] It was an unmitigated disaster, the kind people in the industry still talk about.
[+] It was a triumph beyond anything anyone planned for, the kind people in the industry still talk about.

You are certain of this. Explain, from your own position, why it happened.

- Give 3 to 5 points, ranked by how much [-] damage / [+] upside each one did. 1 is the biggest. No ties.
- Do not stop at what was likely. Go to what actually happened in this extreme outcome, however far it goes.
- At least one point is about people: who decided what, who clashed with whom, who left or took over.
- Write from your position: what you saw, what you were part of, whom you dealt with.
- Be specific enough that a person could own the point. "Execution slipped", "the market softened" or "the team worked well" are not points unless you say what, who and when.
- When a point rests on a figure, a fact or an event the plan does not give (a lead time, a defect, a rate from your experience, a meeting, a call, a decision someone took), write it as you believe it to be and put [ASSUMED] after it.
- When a point rests on specialist knowledge (law, regulation, tax, standards), name the rule or article you rely on, so a specialist can check it.
- [Real people only] The people named here are real. Do not invent anything about their health, private or family life, or anything that would read as an accusation; keep to what they decide and do in their roles.
- Do not hedge with the opposite scenario.

[-] Format for each point:
RANK:
CLAIM: one sentence
MECHANISM: how it came about, two or three sentences
LEADING INDICATOR: what was visible early, and when
HORIZON: when the failure became visible

[+] Format for each point:
RANK:
CLAIM: one sentence
MECHANISM: how it came about, two or three sentences
WHAT HAD TO BE TRUE: a condition that was not verified on {decision_date}
LEADING INDICATOR: what was visible early, and when
HORIZON: when the success became visible

Return only the points.
```

Each point must carry a mechanism (how the plan got from the decision date to this outcome) and a leading indicator. A point without a leading indicator is kept; the synthesis marks its type unwatchable.

### People's card

Read aloud or hand out. One per person or group.

```
Side: {+ or -}
It is {outcome_date}. The decision "{decision}" was taken as planned.
[-] An unmitigated disaster.   [+] A triumph beyond anything planned.

Write alone. No talking until everyone has finished. {5 to 8} minutes.
Give 3 to 5 reasons why it happened, the biggest first. Do not hold back
on the extreme ones. One reason per line or per sticky note: what
happened, and why. Write legibly; the sheet will be photographed.
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

1. Group the points by TYPE of failure or success, not by story: a toy
   that harms children and a toy that brainwashes them are one type, "the
   product does serious harm to its users". A type can hold points from
   both sides. Give each type an ID, a one-line label, its point IDs and its
   number of distinct seats. Keep to about ten types: merge before you
   split.
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
   every type that rests on law, regulation, tax or standards a writer
   supplied: TO CHECK WITH A SPECIALIST.

Do not recommend whether to go ahead. Do not add causes nobody wrote;
if you see an important gap, list it separately under GAPS, labelled as
yours.
```

## Version 2, not built

A fully autonomous run, for instance as a step inside a due diligence: no people, no checkpoints, every seat filled by the panel, the brief and cast taken without confirmation. It reuses every step above and drops every human one; its outputs are marked *unreviewed*.
