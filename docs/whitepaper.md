# The Context Engineering Lifecycle: a guide for technology leaders

Dr Robert Li, Chief AI Architect, HorizonX

## Summary

Agents now write much of the code, and the slow part of delivery has moved to reviewing it, overseeing it and putting right what gets through. This paper sets out a lifecycle for the material that directs that work, which is context, and then how an organisation gets to running it. It follows from the essay *Software is the horseless-carriage and the case for the Context Engineering Lifecycle* (Li, 2026), and each recommendation points to the part of the essay that argues for it (essay, "The reorganisation lag").

| What changes | What to do | Section |
|---|---|---|
| The unit being managed is context, the recorded material agents act on | Define context, its governed and fed parts, and the CELC | Definitions |
| The bottleneck has moved from writing code to reviewing and correcting it | Bundle each spec with executable acceptance checks, and make CI/CD the one enforced gate for going live | The lifecycle model |
| Context ages, and old context misleads agents | Give every item six fields, run it through seven stages, and keep one home per topic | Context flow |
| An agent acts only on what was written down | Record requirements, scope by layer, and write criteria as scope made testable | Requirements, scope and user stories |
| No single method fits all work | Hold four invariants and route spec depth by domain | Working method |
| Ceremonies were sized to the cost of building | Ask what each one paid for and what that cost is now | Ceremony |
| Agents join the work only through what is written for them | Link teams through a few shared artefacts and the fewest enforced gates | Scaling |
| Coordination, the stack and freed time are open questions | Settle each by your risk appetite | Choices to make |
| No finished lifecycle transfers between organisations | Assess, align, pilot and scale, round after round | Implementing a CELC |

## Why the lifecycle matters

When factories first electrified, many kept the layout they had built around the steam engine. One engine had turned one long line shaft, and every machine in the building was belted to it. Electric motors went in where the engine had been, or drove groups of machines through shorter shafts, a compromise known as group drive. Factory electrification did not lift productivity growth in manufacturing until the early 1920s, four decades after the first central power station opened (David, 1990). The gains came with unit drive, a motor for each machine, which let factories be rebuilt around the flow of the work (essay, "From the craft shop to the dynamo").

Software delivery has a line shaft of its own. It is the code layer, and the sprint is the rhythm it turns at: planning, review and release run at one speed for every piece of work. Agents that write code faster inside the same sprint are a new motor on the old shaft. Code now arrives faster than people can review and deploy it, so the queue builds up in review, and the bottleneck has moved from making code to reviewing it, overseeing it and putting right what gets through (essay, "Where the complexity went").

The reorganisation that matches unit drive is around context: the recorded material that tells people and agents what is wanted, what has been decided and what the work has to pass. The Context Engineering Lifecycle (CELC) organises delivery around that material. Context is produced, kept, corrected and superseded as a managed unit, and verification moves onto criteria that a named person answers for (essay, "The reorganisation lag"). This paper sets out the lifecycle first, and then how an organisation gets to running it.

## Definitions

| Term | Meaning |
|---|---|
| Context | Any recorded human communication or thought: user stories, tickets, support transcripts, emails, decision records, specs and rules files. What was never recorded may still be in someone's head, and no agent can act on it |
| Context window | The gateway through which context reaches a model. The harness, the tool that wraps the model, controls what reaches the window |
| Governed context | The small part curated by hand: business rules, compliance obligations, brand and taste. Judgement over it stays with people |
| Fed context | The far larger part that daily operations already produce, extracted and loaded programmatically the way a data platform loads data |
| Context Engineering Lifecycle (CELC) | The discipline that modularises and manages the complexity that has moved from code into context. The name is a label, and nobody owns it |

Context is the input being managed, and the window is only the way it reaches a model, so managing context includes managing what the harness lets through (essay, "What is software now?"). Most context need not be written by hand. Operations already produce it, and only the governed part needs curating (essay, "Where the complexity went"). Agents read all of it, so the rule of garbage in, garbage out makes the management of context the core discipline (essay, "A lifecycle for context").

## The lifecycle model

Code now arrives faster than people can review it, so the bottleneck sits in review, oversight and remediation (essay, "Where the complexity went"). Design the lifecycle around that queue.

The lifecycle balances quality, rework and manual effort, and speed. Speed is what agents add. Rework and manual effort is what poor output costs downstream, and what feeding a method costs once the method outgrows its team (essay, "Every method is an opinion about complexity"). Quality is output that causes no downstream bugs, vulnerabilities or harm to the business. Where the three conflict, keep the lifecycle at the quality end, and spend the time agents free on reviewing and understanding more of what is built (essay, "From the craft shop to the dynamo").

Bundle each spec with its executable acceptance checks, and version the two together. A spec stays honest only while someone can read it in a sitting and its checks fail when the code drifts from it (essay, "A lifecycle for context").

Make CI/CD the one enforced gate for going live. It is the gate at the back of the build, where the evidence from running the program is set against the criteria, and the last chance to realign before the work reaches its users. Keep every other gate advisory unless it has to be enforced, so that enforced gates stay the fewest that hold (essay, "Where the complexity went"). The checks run the program against its criteria: at scale, under load, while failing, under attack, within budget, and with an experience its users will accept. Passing gives demonstration and evidence of what the program did on the runs made, which falls short of proof (essay, "A lifecycle for context").

People write or approve the acceptance criteria. Agents can draft them, but an agent asked to test its own work tends to write tests it can pass, so treat its own tests as scaffolding. Let the builder see the criteria it is checked against. Where independence is required, add a sealed suite, run by a fresh agent that had no part in the work, against criteria the builder never saw (essay, "A lifecycle for context").

Name one accountable person for each change. That person must be able to follow a failure down into the code and find its cause. Someone who cannot do that cannot hold the role, however capable the tools.

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
| Kind | Intent, decision, spec, assumption, bug, feedback, experiment, learning, memory, rule, reference or estate |
| Status | Proposed, accepted, validated, invalidated, superseded or expired |
| Owner | One named person; a team is not an owner |
| Authority | Binding and enforced, binding and advisory, or historical |
| Review-by | A date, or a trigger such as a model change or a pivot |
| Links | The parent item, what it supersedes or is superseded by, and its evidence |

Run context through seven stages, each with a shared artefact and a policy. Only stage 5 is enforced. The other stages run on written policies that teams keep.

| # | Stage | Shared artefact | Policy |
|---|---|---|---|
| 1 | Intake | One inbox per product, every item with a source and a date | Nothing enters without a source. Agents only classify, deduplicate and link |
| 2 | Triage | A recorded disposition for each item: discard, park, fast-path fix or discovery | Parked items expire unless re-raised. Decisions that need a person have a WIP limit |
| 3 | Discover and experiment | An assumption map and an experiment record | Test the important assumptions with the least evidence first. Cap the human time an experiment may take |
| 4 | Spec | The spec bundled with its executable acceptance checks, plus decision records | Commitment is explicit. Decisions that are hard to reverse are marked as such |
| 5 | Build and verify | Change, agent, draft pull request, CI/CD, merge by a person | The one enforced gate. A named person stays accountable for each merge |
| 6 | Learn | A learning review for each absorbed setback or failed assumption | The review names the criteria, rule or spec it changed, or records why none |
| 7 | Prune | A pruning schedule, and pivot records that list what they supersede | Superseded and expired items are not loaded. Rules that allow no exceptions become hooks. Rules are re-tested when the model changes |

Prevent contradiction by structure, because review will not reliably catch it. Two items that disagree will each be acted on, and the model has no reliable way to tell which was meant. Give each topic one home, and when one item supersedes another, record it on both (essay, "A lifecycle for context").

## Requirements, scope and user stories

Gathering context has always been the first gate, whatever a method called it. An engineer who missed something there could recover it in the corridor. An agent acts on what it was given. Capture context in a structured way that people, records and agents can all draw on (essay, "Where the complexity went").

| Artefact | Must contain now |
|---|---|
| Requirement | The recorded intent, with its source, owner and date. A requirement exists for an agent only once it is written down, so record the conversation a story card used to stand for |
| Scope | The what and the where, scoped separately. Specify the what first where it can be analysed, and probe the where with a thin slice through every integration before features are built on it |
| User story | The intent and its acceptance criteria. A criterion is scope made testable: provisional at first, hardening as delivery nears, and owned by a named person |

Criteria creep as scope does. Record changes to them and manage them as you manage changes to scope (essay, "A lifecycle for context").

## Working method

The CELC works with whatever method a team already runs, Scrum, Kanban or spec-driven development among them, provided four invariants hold:

1. Thin slices with executable acceptance. Each thin slice runs through every integration it touches and is small enough to read in a sitting.
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

Run the learning loop on every absorbed setback. A retrospective that only writes a setback up changes nothing an agent does. Trace the setback to its cause and edit the criteria, rule or spec that allowed it, and every agent acts on the change from then on. It is the learning loop of Toyota's production system, applied to context (essay, "From the craft shop to the dynamo").

## Ceremony

Put every ceremony through the purpose test. A ceremony is a payment against a cost, so ask what cost it paid and what has happened to that cost now that agents build (essay, "A lifecycle for context"). The question transfers between organisations, and the answers differ. Use the verdicts below as a starting point.

| Ceremony | Verdict | Why |
|---|---|---|
| The sprint as a batch of commitments | Removed | It batched work to the pace of building, which no longer sets the pace. Flow with a review limit replaces it |
| Sprint planning and estimation | Compressed | They rationed implementation when it was scarce, and routine building is now cheap |
| Defect-backlog triage | Compressed | A team argued over which defects to fix because it could not fix them all |
| Stand-up | Compressed | Coordination between people costs what it did, so the purpose stays; status can go asynchronous |
| Backlog refinement | Modified | Alignment on intent now costs more and is paid earlier, so refinement becomes criteria authoring |
| Verification | Expanded | More is built, so more has to be checked; tier the checking by risk |
| Pairing and retrospectives | Expanded | People no longer learn a program as a by-product of writing it, so learning has to be scheduled |
| Code review | Modified | It is no longer the cheapest control. Keep it deliberately for learning, or replace it for compliance with telemetry, governance and randomised tracing |
| Criteria authoring | New | People write or approve the checks agents build against |
| Sealed evaluation suite | New | A fresh agent checks the work against criteria the builder never saw |
| Sign-off | Modified | Unchanged in substance and explicit in form, with a named owner for each change |

## Scaling

Scale through a few shared artefacts that each team reads its own way, and the fewest enforced gates that hold. A spec is the plainest case: the product owner reads intent in it, the engineer constraints, the auditor evidence and the agent instructions. A spec structured for every reader at once serves none of them well (essay, "Where the complexity went").

When each pair of teams builds its own handover documents and channels, the links between them grow as n(n−1)/2, so ten teams need 45. Shared artefacts replace those pairwise links, and the links then grow roughly in step with the number of teams. Team structures already do this for people, since they let most people avoid talking to most others (essay, "Every method is an opinion about complexity").

Agents change the arithmetic. An agent joins the work only through what has been written down for it, so the size of the working network separates from the size of the organisation. As an illustration, five people running twenty agents make a network of twenty-five participants. Small teams used to stay informal because everyone could talk to everyone. Once agents are in the team, that informality stops working, and a small team needs written, shared context as much as a large one (essay, "A lifecycle for context").

Keep a uniform core and let the edges vary. Shared standards, artefacts and gates sit in the core, and local practice sits at the edges. A leader at each level decides where a unit sits between the two, how fast its complexity may grow and how it is pruned. Widening the core by loading more into it fails, because models do not use long inputs evenly (essay, "The wall at the edge of the firm").

## Choices to make

Three choices have no default that suits every organisation: how to coordinate agents, whose stack to run them on, and what freed time is for. Each is settled by risk appetite.

Approaches to coordinating agents run between two ends (essay, "From the craft shop to the dynamo").

| Approach | Benefits | Trade-offs | Risks |
|---|---|---|---|
| Complete control | A central orchestrator delegates every task and checks every result, which contains errors | Checking everything centrally is slow and hard to make complete over components that are probabilistic | The orchestrator becomes a single point of failure and a queue of its own |
| Laissez-faire | Very high throughput from few people, with nobody waiting on review | Review by people becomes optional, and quality rests on whatever automated checks exist | Errors compound unchecked, and nobody can say with confidence what shipped or why |

The experimental evidence covers both ends. In Kim and Liu's experiments, agents working in parallel without communicating amplified errors "by up to 17.2x", a central orchestrator "contained this amplification to just 4.4x", and on tasks that had to be done in order "every multi-agent variant we tested degraded performance by 39-70%" (Kim and Liu, 2026). Central coordination contains errors, and on sequential work every arrangement of several agents they tested did worse.

I set the landing by the risk the work carries, whether or not the work is exploratory. My worked example, and the default I recommend for a greenfield start, is bounded autonomy. Agents work freely inside a unit of work, and control sits at its edges: the context that goes in, and the checks the output must pass on the way out. At the edges I put criteria a named person approved, a sealed suite where independence is needed, and a WIP limit on what waits for human judgement. Higher-risk work gets tighter edges and lower-risk work looser ones.

The second choice is whose stack to build on. Models and harnesses change, and who runs them decides who holds the risk of that change. Choose by risk appetite and data sensitivity: what you can pin, what you must pin and what you can afford to keep (essay, "Where the complexity went"). Vendor-managed is the greenfield default. Neither is objectively worse.

| What an organisation can pin and control | Vendor-managed | Self-managed |
|---|---|---|
| Model version | Changed or retired on the vendor's schedule | Pinned to a checkpoint you choose |
| Harness and its defaults | Set by the vendor, and can change between releases | Pinned and configured in-house |
| Where data and context go | Governed by the vendor's terms | Kept inside your own boundary |
| Who absorbs change | You, on the vendor's schedule and at a new scale | You, on your own schedule, at the old scale of dependency drift |
| Operating effort | Low, because the vendor runs it | High, because you run, patch and upgrade it |
| Suits | Lower data sensitivity, or a team starting out | Regulated or sensitive data, or work that must be reproducible |

The third choice is what freed time is for. Decide it explicitly, before a default decides it. Do not default to cost-cutting: put the time first into reviewing and understanding more of what is built (essay, "From the craft shop to the dynamo"). Manage the load that oversight puts on people. Agents take the easy work, and what remains is decision and oversight all day. The WIP limit on review keeps that load visible and bounded (essay, "A lifecycle for context").

## References

David, P.A. (1990) "The Dynamo and the Computer: An Historical Perspective on the Modern Productivity Paradox", *American Economic Review*, 80(2), Papers and Proceedings, pp.355–361.

Kim, Y. and Liu, X. (2026) "Towards a science of scaling agent systems: When and why agent systems work", *Google Research Blog*, 28 January, <https://research.google/blog/towards-a-science-of-scaling-agent-systems-when-and-why-agent-systems-work/>.

Li, R. (2026) "Software is the horseless-carriage and the case for the Context Engineering Lifecycle", version 2.0, *drli.blog*, 20 November, <https://drli.blog/posts/software-is-the-horseless-carriage/>.

Snowden, D.J. and Boone, M.E. (2007) "A Leader's Framework for Decision Making", *Harvard Business Review*, 85(11), pp.68–76, 149.
