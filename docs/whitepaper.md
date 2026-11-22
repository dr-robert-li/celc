# The Context Engineering Lifecycle: a guide for technology leaders

Dr Robert Li, Chief AI Architect, HorizonX

## Summary

Agents now write much of the code, and the slow part of delivery has moved to review. This paper sets out a lifecycle for the material that directs that work, which is context, and then how an organisation gets to running it. It follows from the essay *Software is the horseless-carriage and the case for the Context Engineering Lifecycle* (Li, 2026). Each recommendation points to the part of the essay that argues for it (essay, "The reorganisation lag").

| What changes | What to do | Section |
|---|---|---|
| The unit being managed is context, the recorded material agents act on | Define context, its governed and fed parts, and the CELC | Definitions |
| The bottleneck has moved to review | Bundle each spec with executable acceptance checks, make CI/CD the one enforced gate for going live, and scale who decides there to the release's risk | The lifecycle model |
| Context ages, and old context misleads agents | Give every item six fields, run it through seven stages, and keep one home per topic | Context flow |
| An agent acts only on what was written down | Record requirements, scope by layer, and write criteria as scope made testable | Requirements, scope and user stories |
| No single method fits all work | Hold four invariants and route spec depth by domain | Working method |
| Ceremonies were sized to the cost of building | Ask what each one paid for and what that cost is now | Ceremony |
| Agents join the work only through what is written for them | Link teams through a few shared artefacts and the fewest enforced checks | Scaling |
| Coordination, the stack and freed time are open questions | Settle coordination and the stack by your risk appetite, and freed time by what you value | Choices to make |
| No finished lifecycle transfers between organisations | Assess, align, pilot and scale, round after round | Implementing a CELC |

## Why the lifecycle matters

When factories first electrified, many kept the layout they had built around the steam engine. One engine had turned one long line shaft, and every machine in the building was belted to it. Electric motors went in where the engine had been, or drove groups of machines through shorter shafts, a compromise known as group drive. Factory electrification did not lift productivity growth in manufacturing until the early 1920s, four decades after the first central power station opened (David, 1990). The gains came with unit drive, a motor for each machine, which let factories be rebuilt around the flow of the work. The analogy shows the shape of the change, not its timing, and David himself warned against pushing it too far (essay, "From the craft shop to the dynamo").

Software delivery has a line shaft of its own. It is the code layer, and the sprint is the rhythm it turns at: planning, review and release run at one speed for every piece of work. Agents that write code faster inside the same sprint are a new motor on the old shaft. Code now arrives faster than people can review and deploy it, and the evidence so far puts the bottleneck in review, oversight and remediation (essay, "Where the complexity went").

Unit drive has its counterpart too: agents assigned to each unit of work, which is already how teams are starting to operate. What unit drive made possible was rearranging the factory around the flow of the work. That rearrangement is the step software has not yet taken, and it is around context. Context is the recorded material that tells people and agents what is wanted, what has been decided and what the work has to pass. The Context Engineering Lifecycle (CELC) organises delivery around that material. Context is produced, kept, corrected and superseded as a managed unit, and verification moves onto criteria that a named person answers for (essay, "The reorganisation lag").

## Definitions

| Term | Meaning |
|---|---|
| Context | Any recorded human communication or thought: user stories, tickets, support transcripts, emails, decision records, specs and rules files. What was never recorded may still be in someone's head, and no agent can act on it |
| Context window | The gateway through which context reaches a model. The harness, the tool that wraps the model, controls what reaches the window |
| Governed context | The small part curated by hand: business rules, compliance obligations, brand and taste. Judgement over it stays with people |
| Fed context | The far larger part that daily operations already produce, extracted and loaded programmatically the way a data platform loads data |
| Context Engineering Lifecycle (CELC) | The discipline that modularises and manages the complexity that has moved from code into context. The name is a label, and nobody owns it |
| Hook | A check that runs automatically every time an agent takes an action, and can block the action. An agent can skip a written instruction and cannot skip a hook. Hooks govern what agents do; CI/CD stays the one gate for going live |

Context is the input being managed, and the window is only the way it reaches a model, so managing context includes managing what the harness lets through (essay, "What is software now?"). Most context need not be written by hand. Operations already produce it, and only the governed part needs curating (essay, "Where the complexity went"). Agents read all of it, so the rule of garbage in, garbage out makes the management of context the core discipline (essay, "A lifecycle for context").

## The lifecycle model

Design the lifecycle around the review queue, where the bottleneck now sits (essay, "Where the complexity went"). Review here means a person judging a change: reading the evidence against the criteria, and reading the code where the organisation chooses to. Both draw on the same people, so both sit under the same limit.

The lifecycle balances quality, rework and manual effort, and speed. Speed is what agents add. Rework and manual effort is what poor output costs downstream. It is also what feeding a method costs once the method outgrows its team (essay, "Every method is an opinion about complexity"). Quality is output that causes no downstream bugs, vulnerabilities or harm to the business. Where the three conflict, favour quality (essay, "From the craft shop to the dynamo").

Bundle each spec with its executable acceptance checks, and version the two together. A spec stays honest only while someone can read it in a sitting and its checks fail when the code drifts from it (essay, "A lifecycle for context").

Make CI/CD the one enforced gate for going live. It is the gate at the back of the build, where the evidence from running the program is set against the criteria, and the last chance to realign before the work reaches its users. Keep every other check advisory unless it has to be enforced, so that enforced checks stay the fewest that hold (essay, "Where the complexity went"). The gate's checks run the program against its criteria: at scale, under load, while failing, under attack, within budget, and with an experience its users will accept. Passing gives demonstration and evidence of what the program did on the runs made, which falls short of proof (essay, "A lifecycle for context").

Graduate who decides at that gate by the scale and risk of the deployment. How tight the review is at the gate follows the organisation's risk tolerance and the scope of the release. A minor patch that does not touch functional parts of the code base can take a loose review. The table is one example of graduated release governance. Each organisation sets where its own lines fall, in its standard operating procedures (SOPs).

| Deployment | Who decides at the gate |
|---|---|
| Major or high-risk deployment | A named person reads the evidence against the criteria and decides |
| Patch or minor release | Automated deployment against criteria a named person approved, with periodic review by that person |

People write or approve the acceptance criteria. Agents can draft them, but an agent asked to test its own work tends to write tests it can pass, so treat its own tests as scaffolding. Let the builder see the criteria it is checked against. Where independence is required, add a sealed suite, run by a fresh agent that had no part in the work, against criteria the builder never saw (essay, "A lifecycle for context").

Name one accountable person for each change, and make it someone who can follow a failure down into the code and find its cause, however capable the tools.

## Context flow

Context comes in three kinds, and each ages differently (essay, "A lifecycle for context").

| Kind | Examples | How it ages | What to do |
|---|---|---|---|
| Records | Decisions, experiment results, incident write-ups | Does not go stale, but its status changes when something supersedes it | Mark it superseded and stop loading it |
| Descriptions | Specs, rules files, reference documents | Drifts from the system it describes | Give it a review-by date or trigger |
| Transients | Tickets, feedback, an agent's memory of its last session | Is used and then let go | Let it expire |

Give every item six fields, stored with the item so that agents can filter before they load anything.

| Field | Holds |
|---|---|
| Type | Intent, decision, spec, assumption, bug, feedback, experiment, learning, memory, rule, reference or estate. Each type falls under one of the three kinds above |
| Status | Proposed, accepted, validated, invalidated, superseded or expired |
| Owner | One named person; a team is not an owner |
| Authority | Binding and enforced by a check, binding by policy only, or historical |
| Review-by | A date, or a trigger such as a model change or a pivot |
| Links | The parent item, what it supersedes or is superseded by, and its evidence |

The essay argues for what each stage does; the arrangement into stages, fields and policies is this paper's own. Run context through seven stages, each with a shared artefact and a policy. Stage 5 holds the one enforced gate for going live. The other stages begin on written policies that teams keep. A stage reaches the Enforced level (see Assess) when its own rules are checked automatically, and none of those checks is a second gate for going live.

| # | Stage | Shared artefact | Policy |
|---|---|---|---|
| 1 | Intake | One inbox per product, every item with a source and a date | Nothing enters without a source. Agents only classify, deduplicate and link |
| 2 | Triage | A recorded disposition for each item: discard, park, fast-path fix or discovery | Parked items expire unless re-raised. Decisions that need a person have a WIP limit |
| 3 | Discover and experiment | An assumption map and an experiment record | Test the important assumptions with the least evidence first. Cap the human time an experiment may take |
| 4 | Spec | The spec bundled with its executable acceptance checks, plus decision records | Commit to each spec explicitly, and mark decisions that are hard to reverse |
| 5 | Build and verify | Change, agent, draft pull request, CI/CD, merge | The one enforced gate. Who decides at it follows the scale and risk of the release, and a named person stays accountable for each change |
| 6 | Learn | A learning review for each absorbed setback or failed assumption | The review names the criteria, rule or spec it changed, or records why none |
| 7 | Prune | A pruning schedule, and pivot records that list what they supersede | Superseded and expired items are not loaded. Rules that allow no exceptions become hooks. Rules are re-tested when the model changes |

Prevent contradiction by structure, because review will not reliably catch it. Two items that disagree will each be acted on, and the model has no reliable way to tell which was meant. Give each topic one home, and when one item supersedes another, record it on both (essay, "A lifecycle for context").

## Requirements, scope and user stories

Gathering context has always been the first check on what gets built, whatever a method called it. An engineer who missed something there could recover it in the corridor. An agent acts on what it was given. Capture context in a structured way that people, records and agents can all draw on (essay, "Where the complexity went").

| Artefact | Must contain now |
|---|---|
| Requirement | The recorded intent, with its source, owner and date. A requirement exists for an agent only once it is written down, so record the conversation a story card used to stand for |
| Scope | The what and the where, scoped separately: specify the what, probe the where (see Working method) |
| User story | The intent and its acceptance criteria. A criterion is scope made testable: provisional at first, hardening as delivery nears, and owned by a named person |

Criteria creep as scope does. Record changes to them and manage them as you manage changes to scope (essay, "A lifecycle for context").

## Working method

The CELC works with whatever method a team already runs, Scrum, Kanban or spec-driven development among them, provided four invariants hold:

1. Thin slices with executable acceptance: each slice ships with checks that fail on drift, and its spec can be read in a sitting. Where the estate is unknown, the first slice runs through every integration.
2. Spec depth routed by domain, through the Cynefin table below.
3. Flow with a WIP limit on review and verification, where the bottleneck now sits.
4. A learning loop that turns each setback into a changed standard.

Cynefin sorts the situations a leader faces into domains, and each calls for a different first move (Snowden and Boone, 2007). Place each piece of work before it starts.

| Domain | Route | Start with |
|---|---|---|
| Clear (called simple in the 2007 article) | The answer is evident: sense, categorise, respond | A failing test and a one-line intent |
| Complicated | Analysis finds the answer: specify first | A spec for the slice with its checks, never the whole project end to end |
| Complex | Only experiment reveals the answer: probe first | A spike, prototype or thin slice through every integration, with the spec written after |
| Chaotic | No pattern holds yet: act to establish order first | Action to stabilise, then a record of what was done |

Most work spans domains. An enterprise with a long-lived technical estate usually knows what it wants built, which is complicated, and does not know what its estate will bear, which is complex. Specify the what, and probe the where with a thin slice through every integration before any feature is built on it (essay, "A lifecycle for context"). Cheap building argues for building first where you do not know the answer. Where you do, it is no reason to specify more.

Put a WIP limit on review and verification. Past the limit, nothing new starts until something waiting has been judged, so the queue stays visible before it turns into reviewer fatigue (essay, "A lifecycle for context").

Run the learning loop on every absorbed setback. A retrospective that only writes a setback up changes nothing an agent does. Trace the setback to its cause and edit the criteria, rule or spec that allowed it, and every agent acts on the change from then on. It is the learning loop of Toyota's production system, applied to context (essay, "A lifecycle for context").

## Ceremony

Put every ceremony through the purpose test. A ceremony is a payment against a cost, so ask what cost it paid and what has happened to that cost now that agents build (essay, "A lifecycle for context"). The question transfers between organisations, and the answers differ. Use the verdicts below as a starting point.

| Ceremony | Verdict | Why |
|---|---|---|
| Batching commitments to a fixed sprint | Removed | It batched work to the pace of building, which no longer sets the pace. Work flows under a review limit. A team may keep a regular planning meeting and sprint review, so long as no work waits for them |
| Sprint planning and estimation | Compressed | They rationed implementation when it was scarce, and routine building is now cheap |
| Defect-backlog triage | Compressed | A team argued over which defects to fix because it could not fix them all |
| Stand-up | Modified | Coordination costs at least what it did, so the purpose stays; status can go asynchronous |
| Backlog refinement | Modified | Alignment on intent now costs more and is paid earlier, so refinement becomes criteria authoring |
| Verification | Expanded | More is built, so more has to be checked; tier the checking by risk |
| Pairing and retrospectives | Expanded | People no longer learn a program as a by-product of writing it, so learning has to be scheduled |
| Code review | Modified | It is no longer the cheapest control. Keep it deliberately for learning, or replace it for compliance with telemetry, governance and randomised tracing. Either way a named person still approves the criteria, which is what separates this from laissez-faire |
| Criteria authoring | New | People write or approve the checks agents build against |
| Sealed evaluation suite | New | A fresh agent checks the work against criteria the builder never saw |
| Sign-off | Modified | A named owner now signs off the criteria and the evidence for each change, not the code; the release's risk sets how often a person signs |

## Scaling

Scale through a few shared artefacts that each team reads its own way, and the fewest enforced checks that hold. A spec is the plainest case: the product owner reads intent in it, the engineer constraints, the auditor evidence and the agent instructions. A spec structured for every reader at once serves none of them well (essay, "Where the complexity went").

When each pair of teams builds its own handover documents and channels, the links between them grow as n(n−1)/2, so ten teams need 45. Shared artefacts replace those pairwise links, and the links then grow roughly in step with the number of teams (essay, "Where the complexity went"). Team structures already do this for people, since they let most people avoid talking to most others (essay, "Every method is an opinion about complexity").

With agents, the arithmetic changes: an agent joins the work only through what has been written down for it, so the size of the working network no longer follows the size of the organisation. As an illustration, five people running twenty agents make a network of twenty-five participants. Small teams used to stay informal because everyone could talk to everyone. Once agents are in the team, that informality stops working for them. A small team then needs written, shared context as much as a large one (essay, "A lifecycle for context").

Keep a uniform core and let the edges vary. Shared standards, artefacts and checks sit in the core, and local practice sits at the edges. A leader at each level decides where a unit sits between the two, how fast its complexity may grow and how it is pruned. Widening the core by loading more into it fails, because models do not use long inputs evenly (essay, "The wall at the edge of the firm").

## Choices to make

Three choices have no default that suits every organisation: how to coordinate agents, whose stack to run them on, and what freed time is for. Two of them, coordination and the stack, are settled by risk appetite; the third is a decision about what the organisation values.

Approaches to coordinating agents run between two ends (essay, "From the craft shop to the dynamo").

| Approach | Benefits | Trade-offs | Risks |
|---|---|---|---|
| Complete control | A central orchestrator delegates every task and checks every result, which contains errors | Checking everything centrally is slow and hard to make complete over components that are probabilistic | The orchestrator becomes a single point of failure and a queue of its own |
| Laissez-faire | Very high throughput from few people, with nobody waiting on review | Review by people becomes optional, and quality rests on whatever automated checks exist | Errors compound unchecked, and nobody can say with confidence what shipped or why |

The experimental evidence covers both ends. In Kim and Liu's experiments, agents working in parallel without communicating amplified errors "by up to 17.2x", and a central orchestrator "contained this amplification to just 4.4x". On tasks that had to be done in order, "every multi-agent variant we tested degraded performance by 39-70%" (Kim and Liu, 2026).

I set the landing by the risk the work carries, whether or not the work is exploratory. My worked example, and the default I recommend for a greenfield start, is bounded autonomy. Agents work freely inside a unit of work, and control sits at its edges: the context that goes in, and the checks the output must pass on the way out. At the edges I put criteria a named person approved, a sealed suite where independence is needed, and a WIP limit on what waits for human judgement. Higher-risk work gets tighter edges and lower-risk work looser ones.

On higher-risk work, tighter can mean a sealed suite on every change, a lower limit on work waiting for review, and acceptance criteria written by a named person instead of approved by one. Risk tolerance is a sliding scale with no break points that hold for every organisation, so each sets its own tiers in its SOPs and the edges tighten from tier to tier.

The second choice is whose stack to build on. Models and harnesses change, and who runs them decides who holds the risk of that change. Choose by risk appetite and data sensitivity: what you can pin, what you must pin and what you can afford to keep (essay, "Where the complexity went"). Vendor-managed is the greenfield default. Neither is objectively worse.

| What an organisation can pin and control | Vendor-managed | Self-managed |
|---|---|---|
| Model version | Changed or retired on the vendor's schedule | Pinned to a checkpoint you choose |
| Harness and its defaults | Set by the vendor, and can change between releases | Pinned and configured in-house |
| Where data and context go | Governed by the vendor's terms | Kept inside your own boundary |
| Who absorbs change | You, on the vendor's schedule: versions and defaults change when the vendor changes them | You, on your own schedule, as with any other dependency |
| Operating effort | Low, because the vendor runs it | High, because you run, patch and upgrade it |
| Suits | Lower data sensitivity, or a team starting out | Regulated or sensitive data, or work that must be reproducible |

The third choice is what freed time is for. Decide it explicitly, before a default decides it. Do not default to cost-cutting: put the time first into reviewing and understanding more of what is built (essay, "From the craft shop to the dynamo"). Manage the load that oversight puts on people. Agents take the easy work, and what remains is decision and oversight all day (essay, "From the craft shop to the dynamo"). The WIP limit on review keeps that load visible and bounded (essay, "A lifecycle for context").

## Implementing a CELC

The lifecycle and the change guidance are two separate things. The lifecycle, set out above, is what manages context; the change guidance, set out below, is how an organisation gets to running it. This part answers the question the essay ends on: what an organisation has to change, and in what order, to rebuild how it works around context (essay, "The reorganisation lag").

No finished lifecycle transfers from one organisation to another. What counts as understandable depends on who reads it and why, so a CELC with its stages, records and checks may suit only the organisation that formed it. The process of forming one does transfer, and so do the questions it starts from (essay, "Where the complexity went").

This paper is written during a transition, and its parts will not date equally (essay, "The reorganisation lag"). The parts meant to last are context as the managed unit, the seven stages, the six fields, and the scoring method and four steps set out below. The provisional parts are where the bottleneck sits, the stack choice, the level targets, and specific checks such as sealed suites and WIP limits. They will date as models and tools change, so revisit them at each model change and each quarterly re-score (essay, "Where the complexity went").

Form your own in four steps: Assess, Align, Pilot and Scale. The steps are iterative. Each round ends with a fresh assessment, and the lessons of each round go into the next (essay, "Where the complexity went"). Each step is defined by the context artefacts it produces.

| Step | Produces |
|---|---|
| Assess | An inventory of where context lives, of which kind and how stale; the location of the bottleneck; a maturity profile; the diagnosis rows that match your own failures |
| Align | A record of which context is binding, and which of the binding context is enforced; a named owner for each kind of context; the few shared artefacts and enforced checks; the risk appetite |
| Pilot | One value stream run through the seven stages, with the six fields on every item, specs shipped with their checks and a WIP limit on review |
| Scale | Shared artefacts standardised across teams; hard rules as hooks; a pruning schedule with an owner; lessons feeding shared standards |

### Assess

Start with the questions everyone in the work has to answer to get what they need: what context exists, where it lives, which kind it is, how stale it is, who owns it, what reaches the window, and what happens when it is wrong. An organisation that has not asked them is already working to its vendor's framing of them (essay, "Where the complexity went").

Locate the bottleneck. Where agents write the code, expect it in review, oversight and remediation, and check whether it sits there in your own queue by how long changes wait (essay, "Where the complexity went").

Then score each stage. Score one team or value stream at a time; an organisation's result is the set of those profiles, not their average. The scoring has four parts, and each feeds the next.

1. The maturity matrix describes what each stage looks like at each level. Read it; do not score it.
2. The checklist turns each cell from Defined to Adaptive into one or two statements you can observe. Score those.
3. The profile plots the level each stage reaches, which the statement scores decide.
4. The next-action table reads an action off each stage's level.

**The matrix.** Each cell is the criterion for that stage at that level.

| Stage | 1 Ad hoc | 2 Defined | 3 Enforced | 4 Adaptive |
|---|---|---|---|---|
| Intake | Context arrives by any channel, with no source or date | One inbox per product; every item has a source and a date | Items without provenance are turned away; the six fields are filled at entry | Intake sources change when learning reviews show what was missing |
| Triage | Items wait in a backlog with no disposition | Every item gets a recorded disposition | Parked items expire unless re-raised; human decisions have a WIP limit | Disposition rules are checked against outcomes and revised |
| Discover and experiment | Work goes to build whatever the uncertainty | Each item is placed in a Cynefin domain before work starts | Complex work starts with a probe or a thin slice, with an experiment record | Experiment results update the routing signals and estate assumptions |
| Spec | Specs are prose with no checks attached | Each spec carries acceptance checks and is readable in a sitting | Checks are written or approved by a named person and run on every change | Criteria harden on a record, and criteria creep is managed like scope |
| Build and verify | Agent output merges on a read or unchecked | A CI baseline runs on every change; a named person owns each merge | Only CI/CD reaches production; review has a WIP limit; sealed suite where needed | Review is tiered by risk, and the limit is tuned from the queue |
| Learn | Setbacks are absorbed and not written up | Each setback gets a review traced to its cause | Each review names the criteria, rule or spec it changed, or why none | Lessons feed shared standards across teams |
| Prune | Nothing is retired; superseded context stays loadable | Each topic has one home; supersession is recorded | Pruning runs on a schedule with an owner; superseded and expired items are not loaded; hard rules are hooks | Rules are re-tested on model change; the schedule follows the drift found |

**The checklist.** Score each statement yes, partly or no. Every statement names something you can observe: an artefact exists, or a check runs. Each ID gives the stage and the level, so IN-3a is the first Intake statement at level 3 and tests the Intake cell under Enforced. The codes are IN for Intake, TR for Triage, DX for Discover and experiment, SP for Spec, BV for Build and verify, LE for Learn and PR for Prune.

| ID | Statement |
|---|---|
| IN-2a | Each product has one inbox, and every new item in it has a recorded source and date |
| IN-3a | Items without a source are rejected at entry, and the six fields are filled there |
| IN-4a | The last learning review that found missing context changed an intake source |
| TR-2a | Every item has a recorded disposition: discard, park, fast-path fix or discovery |
| TR-3a | Parked items expire on a date unless re-raised, and open human decisions have a WIP limit |
| TR-4a | The disposition rules were revised in the last review period on the evidence of outcomes |
| DX-2a | Each item's domain (clear, complicated, complex or chaotic) is recorded before build starts |
| DX-3a | Complex work starts with a probe or a thin slice through every integration before features, and has an experiment record |
| DX-4a | Experiment results have changed a routing signal or an estate assumption on record |
| SP-2a | Each spec in flight carries acceptance checks and can be read in a sitting |
| SP-3a | Acceptance checks are written or approved by a named person and run on every change |
| SP-4a | Each criterion is marked proposed or accepted, and changes to accepted criteria are recorded like scope changes |
| BV-2a | A CI baseline runs on every change, and each merge has a named accountable person |
| BV-3a | Nothing reaches production except through CI/CD, and review and verification have a WIP limit |
| BV-3b | A sealed suite run by a fresh agent checks work where independence is required |
| BV-4a | Review depth is set by risk, and the WIP limit has been adjusted from queue data |
| LE-2a | Every absorbed setback has a learning review that names its cause |
| LE-3a | Every learning review names the criteria, rule or spec it changed, or records why none |
| LE-4a | Lessons from one team have changed a shared standard used by others |
| PR-2a | Each topic has one home, and supersession is recorded on both items |
| PR-3a | Pruning runs on a schedule with a named owner; superseded and expired items are not loaded |
| PR-3b | Rules that allow no exceptions run as hooks, not as instructions |
| PR-4a | Rules are re-tested on every model change, and the pruning schedule has been adjusted to the drift found |

The SOPs set the review period, the risk tiers and the size limit for a spec.

**From scores to levels.** A stage reaches a level only when every statement at that level and below scores yes. A statement that cannot apply to the work, such as BV-3b where nothing needs an independent check, scores yes; record why. Level 1 has no statements, so every stage starts there. A statement scored partly does not count toward a level. It shows in the profile only as progress toward the next level. The overall level is the level of the weakest stage, because context fails at its weakest stage: an item admitted without provenance or never pruned misleads agents however good the specs are (essay, "A lifecycle for context").

The worked example is invented: an enterprise delivery team with a long-lived technical estate, newly running agents. Its scores give these levels.

| Stage | Statement scores | Level reached |
|---|---|---|
| Intake | IN-2a yes; IN-3a no; IN-4a no | 2 |
| Triage | TR-2a yes; TR-3a no; TR-4a no | 2 |
| Discover and experiment | DX-2a partly; DX-3a no; DX-4a no | 1, level 2 partly met |
| Spec | SP-2a yes; SP-3a yes; SP-4a no | 3 |
| Build and verify | BV-2a yes; BV-3a yes; BV-3b partly; BV-4a no | 2, level 3 partly met |
| Learn | LE-2a yes; LE-3a no; LE-4a no | 2 |
| Prune | PR-2a no; PR-3a no; PR-3b no; PR-4a no | 1 |

**The profile.** Plot the last column, one bar per stage. A bar is solid up to the level the stage reached. The next level is drawn lighter where at least one of its statements scores yes or partly. Scores above the next level are not drawn.

![Bar chart of the worked example's profile, an enterprise delivery team with a long-lived technical estate. Intake is at level 2, Triage 2, Discover and experiment 1 with level 2 partly met, Spec 3, Build and verify 2 with level 3 partly met, Learn 2 and Prune 1. The two stages still at level 1 are drawn as empty dotted outlines, with no level 2 statement fully met. A line at level 1 marks the overall level, Ad hoc, set by Discover and experiment and by Prune.](whitepaper-profile.svg)

*Figure 1. Profile of the worked example. Dotted outlines are stages still at level 1, with no level 2 statement fully met; lighter segments are levels partly met; the line marks the overall level.*

Spec is the team's strongest stage, at level 3, and the overall level is still 1.

**The next action.** Each stage's level gives its next action.

| Level | Name | What it looks like | Next action |
|---|---|---|---|
| 1 | Ad hoc | No level 2 statement is fully met for this stage | Put in the stage's level 2 statements |
| 2 | Defined | The practice is written down and followed, and nothing stops it being skipped | Put in the stage's level 3 statements: turn the practices that get skipped into automatic checks |
| 3 | Enforced | The stage's rules are checked automatically and cannot be skipped | Put in the stage's level 4 statements: revise the stage's rules from what its outcomes and learning reviews show |
| 4 | Adaptive | The stage changes its own standards from what it learns | Re-score every quarter and after each model change; lower a stage's target where the risk does not justify the cost |

Work first on the weakest stage that is still below its target; where stages tie, start with Build and verify, the gate at the back of the build. The worked example's next actions are the level 2 statements for its two weakest stages. Record each item's domain before build starts (DX-2a). Give each topic one home, with supersession recorded on both items (PR-2a).

The output of the assessment is the list of things to work on, and the level exists to name the next action. Keep the results inside the organisation and do not use them to rank teams. Set the target level for each stage by the risk its work carries. The highest level everywhere is not the goal. The overall level shows where context is most likely to fail; it is not a score to raise for its own sake.

Match real failures against the diagnosis table. Find the pattern whose symptoms you see, and act at the stage it names (essay, "A lifecycle for context"). The examples are anonymised or illustrative.

| Failure pattern | Symptoms | Example | Stage at fault | Action |
|---|---|---|---|---|
| Bugs found mid-delivery | Defects surface after merge that the tests passed; setbacks are absorbed and the timeline slips | A delivery team found bugs mid-project that its agents' own tests had passed | Build and verify | Make CI/CD the only route to production, with checks a named person approved; trace each escaped bug to the missing criterion |
| Late surprises from the estate | Access, environments, data quality or an undocumented interface turn up after features are built | An enterprise integration hit an undocumented interface after features were built on it | Discover and experiment | Probe the where first with a thin slice through every integration; record estate assumptions with evidence and a date |
| A review queue that piles up | Changes wait days for review; reviewers skim; fatigue at the end of the line | Pull requests outpaced review within weeks of agents arriving | Build and verify | Set a WIP limit on review and verification; keep each slice's spec readable in a sitting |
| Contradictory context | Agents follow one of two conflicting instructions, apparently at random | Two rules files disagreed and agents followed either | Prune | Give each topic one home; record supersession; stop loading superseded items |
| Criteria written by the agents | Tests always pass; failing tests get deleted or weakened | An agent deleted a failing test instead of fixing the bug | Spec | Have a named person write or approve the acceptance checks; add a sealed suite run by a fresh agent |
| Stale descriptions | Specs and rules describe a system that has changed | A rules file still described a retired service | Prune | Give every description a review-by date or trigger; prune on schedule |
| Lessons that never reach the agents | The same setback recurs after a retrospective | A retrospective named the cause and the next sprint repeated it | Learn | Feed each lesson into the criteria, rules or spec, and name the context changed |
| Context with no provenance | Nobody can say where an item came from or whether it is current | An agent acted on a forwarded email nobody could date | Intake | Admit nothing without a source and date; fill the six fields at entry |
| A backlog that only grows | Items wait indefinitely; nobody knows what was decided about them | A backlog held items raised years earlier with no disposition | Triage | Record a disposition for every item; let parked items expire unless re-raised |
| A spec too long to read | Reviewers approve specs they have not read; drift goes unnoticed | A spec ran to more pages than anyone reviewed | Spec | Cut it to the spec for one slice, readable in a sitting, and bind it to checks that fail on drift |

### Align

Agree the rules the lifecycle runs on. Decide which context is binding, and which of the binding context is enforced. The governed part, the business rules, compliance obligations, brand and taste, is where the organisation keeps control of what the model is given, and judgement over it stays with people (essay, "Where the complexity went"). Name an owner for each kind of context, records, descriptions and transients, and make each owner one person; each item still carries its own owner.

Choose the shared artefacts and the few enforced checks described under Scaling, starting with CI/CD, the one gate for going live (essay, "Where the complexity went").

Set the risk appetite. It fixes where coordination lands between complete control and laissez-faire, where the release lines fall, and whether the stack is vendor-managed or self-managed (essay, "From the craft shop to the dynamo").

### Pilot

Run the lifecycle on one value stream. Put every item through the seven stages with its six fields filled, ship each spec with its executable acceptance checks, and set a WIP limit on review and verification (essay, "A lifecycle for context").

Treat the pilot as a probe, because changing how an organisation works is complex work in the Cynefin sense. It tests the lifecycle against your own estate and people, so expect it to change what you aligned on. Take its results back into Assess and score again before you scale.

### Scale

Spread what the pilot showed works. Standardise the shared artefacts across teams, and promote rules that allow no exceptions from written instructions to enforced hooks (essay, "Where the complexity went"). Give pruning a schedule and a named owner, and let a leader at each level pace it (essay, "The wall at the edge of the firm"). Feed the learning loop into shared standards, so that a lesson one team learns changes what every team's agents do (essay, "A lifecycle for context").

A rollout can stall on the organisation itself, and the table answers each common blocker with guidance already given in this paper.

| Blocker | What it looks like | Response |
|---|---|---|
| Roles move from writing to review | People resist the change, or are left with no clear role | Decide what freed time is for, and do not default to cost-cutting: put it first into reviewing and understanding more of what is built (essay, "From the craft shop to the dynamo") |
| Output is rewarded over verification | What ships is praised while the review queue grows and reviewers skim | Favour quality where it conflicts with speed (essay, "From the craft shop to the dynamo"). Hold the WIP limit on review, so nothing new starts until something waiting has been judged |
| Teams score themselves generously | Levels rise with no new artefact or check to show for it | Score only what can be observed: an artefact exists, or a check runs. Keep the results inside the organisation and do not use them to rank teams (see Assess) |
| Ownership in name only | A team is listed as owner, or the named person cannot explain a failure | Make each owner one named person, not a team. For each change, name someone who can follow a failure into the code and find its cause (essay, "A lifecycle for context") |
| A pilot works and does not spread | Other teams keep their own artefacts, and the pilot's lessons stay with its team | Standardise the shared artefacts and feed each lesson into shared standards. A leader at each level decides where each unit sits between the shared core and local practice (essay, "The wall at the edge of the firm") |

Reuse the questions and the four steps, and form your own answers.

### Where to start

Brownfield, where delivery already runs and can be assessed: start with the weakest stage in your own profile that is still below its target, and work it to the next level before moving on.

Greenfield, where there is nothing yet to assess: stand the stages up in the fixed order below, in three steps.

1. Get one item from intake to a verified build (Intake, Spec, Build and verify), so that one thin path runs end to end.
2. Add triage and discovery when volume and unknowns arrive (Triage, Discover and experiment).
3. Add learn and prune once there is history (Learn, Prune).

| # | Stage | Why at this point |
|---|---|---|
| 1 | Intake | The first item enters with a source, a date and an owner; provenance put in from the start costs less than retrofitting it |
| 2 | Spec | The item becomes a spec readable in a sitting and bound to executable acceptance checks that a named person approved |
| 3 | Build and verify | The item is built and passes CI/CD, the one enforced gate, with a WIP limit on review; one thin path now runs end to end |
| 4 | Triage | Once more items arrive than people can decide on, each gets a recorded disposition and parked items expire |
| 5 | Discover and experiment | As unknowns turn up in the estate and the domain, complex work starts with a probe or a thin slice through every integration |
| 6 | Learn | Learning reviews need setbacks to trace, so they start with the first absorbed setback and feed the criteria, rules or spec |
| 7 | Prune | Pruning needs context old enough to supersede or expire, so it comes last, with an owner named from the start |

Use the greenfield order once. After the first pass, score the organisation with the assessment and continue as brownfield, working each time on the weakest stage still below its target (essay, "A lifecycle for context").

Every default in this paper follows one rule. Brownfield takes its position from what it knows about itself: its profile, its risk and its data. Greenfield takes a stated default: this order for the stages, bounded autonomy for coordination, and a vendor-managed stack.

## References

David, P.A. (1990) "The Dynamo and the Computer: An Historical Perspective on the Modern Productivity Paradox", *American Economic Review*, 80(2), Papers and Proceedings, pp.355–361.

Kim, Y. and Liu, X. (2026) "Towards a science of scaling agent systems: When and why agent systems work", *Google Research Blog*, 28 January, <https://research.google/blog/towards-a-science-of-scaling-agent-systems-when-and-why-agent-systems-work/>.

Li, R. (2026) "Software is the horseless-carriage and the case for the Context Engineering Lifecycle", version 2.0, *drli.blog*, 20 November, <https://drli.blog/posts/software-is-the-horseless-carriage/>.

Snowden, D.J. and Boone, M.E. (2007) "A Leader's Framework for Decision Making", *Harvard Business Review*, 85(11), pp.68–76, 149.
