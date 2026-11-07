# Essay tension log

This log keeps the essay's argument with itself out of the essay. For each tension it records where drafting stopped to pose it, the strongest case on each side, the author's position, the passage of the essay that resolves or acknowledges it, and whether the claim should stay in the essay and not become whitepaper guidance (tension 8). The essay itself stays clean: it argues each position once the author has given it, without the scaffolding.

## T1: Does complexity move rather than vanish?
- **Status:** open
- **Stop:** 4A
- **Raised in:** pending
- **Steelman A:** pending
- **Steelman B:** pending
- **Author's position:** pending
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T2: The micro-agent army recreates the microservices problem
- **Status:** open
- **Stop:** 3A
- **Raised in:** pending
- **Steelman A:** pending
- **Steelman B:** pending
- **Author's position:** pending
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T3: Spec-driven redux
- **Status:** settled
- **Stop:** settled
- **Raised in:** n/a (settled; argued, not posed)
- **Steelman A:** n/a (settled; argued, not posed)
- **Steelman B:** n/a (settled; argued, not posed)
- **Author's position:** Settled 2026-11-06 in the thesis, §11.1. The CELC is waterfall vindicated only in the complicated domain; in the complex domain it probes first and writes the spec after learning. Cheap building is an argument for building first where you don't know, not for specifying more where you do.
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T4: "Code is a given" vs "quality matters"
- **Status:** open
- **Stop:** 5A
- **Raised in:** pending
- **Steelman A:** pending
- **Steelman B:** pending
- **Author's position:** pending
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T5: Ford, Sloan, or Toyota?
- **Status:** settled
- **Stop:** settled
- **Raised in:** n/a (settled; argued, not posed)
- **Steelman A:** n/a (settled; argued, not posed)
- **Steelman B:** n/a (settled; argued, not posed)
- **Author's position:** Settled 2026-11-07 in CONTEXT D-11 to D-13. Keep Toyota's learning loop (jidoka, stop-the-line) and built-in quality; refuse lean as it was repositioned in the West, as the intensification of work and the cutting of costs. AI-assisted development intensifies work too, but differently from lean, and it widens a continuum between better work in the same time and further cost-cutting. Humans choose where to land, and the CELC chooses quality.
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T6: "UX doesn't matter" vs defaults
- **Status:** answered
- **Stop:** 1A
- **Raised in:** "What is software now?" (Movement 1), 2026-11-07. Drafting halted after "The screen moves to the far end of the wire.", before the §4 claim that users stop caring about vendor UX or brand.
- **Steelman A:** *UX fades; value moves to data plus capabilities.* A bespoke interface created its own lock-in: a proprietary grammar of screens and flows that users had to learn, and that made leaving expensive. Chat has no such grammar to learn. It runs on reading and writing, and Karpathy's point is that "these prompts are written in English" (B2), so the skill that operates one front end operates every other. Once rendering happens in the harness, the vendor's opinion of how the work should go is no longer the product; what is left to compete on is whether the store holds the data the user wants, in the structure they want, reachable the way they want (thesis §4). Open protocols (API, MCP, A2A) mean a harness default does not bind the user to any one data vendor, because every capability is callable from every harness. Even the strongest recent finding on defaults concedes the limit: "defaults are less effective when the alternative has strong brand recognition and product quality" (N2, p.212). If quality now lives in the data and capabilities, defaults lose their grip where it matters. And the user Karpathy describes is "orchestrating agents who do and acting as oversight" (B6): someone judging outcomes, not someone living inside a vendor's chrome.
- **Steelman B:** *Defaults win; the harness vendor captures the value.* People accept defaults, by large margins, even on choices they say they care about. Johnson and Goldstein found effective consent to organ donation of 4.25% to 27.5% across explicit-consent (opt-in) countries against 85.9% to 99.98% across presumed-consent (opt-out) countries, and donation rates "about twice as high when opting-out as when opting-in" in an online experiment where changing the answer took one click (N1, p.1338). Their three mechanisms (a default read as a recommendation, the effort of deciding, loss aversion) apply to any harness's configuration. In software the effect is priced: the court in the US search case accepted the plaintiffs' expert's evidence that "defaults have a powerful impact on consumer decisions" (N2, p.30) and found that "All of this makes the defaults extremely valuable", with $26.3 billion paid in 2021 in revenue share under the contracts that bought those placements (N2, p.105; p.232). So UX does not vanish when it leaves the data vendor. It moves to whoever owns the harness, which sets the default sources, tools and presentation, and the brand relationship and the value go with it (thesis tension 6). Users stop caring about the data vendor's UX because they have already accepted the harness vendor's. A historical-materialist reading is available to this side: control of the means of interaction. Caution: N1 is organ donation, so its transfer to software is by analogy.
- **Author's position:** 2026-11-08: "I lean more to Side B. It is true that defaults have a powerful hold on users and a meaningful number will stay with default options for a variety of reasons (see Google anti-trust lawsuit), and therefore the UX (and client side UI) will often (though not always, as, again, was seen in the Google anti-trust lawsuit) default to whoever owns the harness (and ChatGPT and Claude Desktop are examples of highly opinionated harnesses), which is materially advantageous to the harness vendor, therefore. That said, (usually) the dataset and intermediary capabilities provided by proxies such as MCP/API servers and A2A agents, are not usually owned by the harness (and harness vendor), neither is the hardware (usually) so the harness takes the intermediary position that, perhaps, a search engine like Google used to take (but instead of forwarding, it owns the entire UX end to end as the interlocutor - maybe "interlocutor" is the best way to understand the role of the default harness now and therefore "control of means of interaction" is also an apt statement), it becomes the OPP for the operator/user connected to a range of services via MCP and API servers, and agents via A2A etc." Ruling on sources, same date: "A courts findings and rulings are strong source materials. This is admissable as a source, it does not need to come from a company directly, the legal system is an authoritative source." (D-17 amended.)
- **Resolution in essay:** resolved. The passage begins "From there it is tempting to take one more step" and runs to "They express that care through an interface the data vendor no longer controls.", in "What is software now?" (Movement 1). It keeps the §4 claim in qualified form: users stop caring about the data vendor's UX because the harness's UX has replaced it. Evidence: N1 (why defaults stick; registration against outcomes), N2 (the price of defaults, p.30, p.105, p.232; the brand-and-quality limit, p.212), N3 (one sentence: paying for default placement is still allowed). ChatGPT and Claude Desktop are named descriptively, as the author named them. "Obligatory passage point" gets its first, short gloss here (Callon, 1986); S4 deepens it. **Tentative:** "interlocutor" is the working term on the author's "maybe"; confirm or replace it at the stop-1B review.
- **Essay-only (tension 8):** proposed: no. The defaults claim (the harness vendor sets the defaults and captures the value the data vendor's UI used to hold; data, capabilities and hardware usually sit elsewhere; paying for default placement is allowed) is strategic, and the whitepaper can carry it in plain language. The wording "obligatory passage point" and "control of the means of interaction" is essay-only vocabulary (D-07).

## T7: Conway's Law frames the socio-economic wall
- **Status:** open
- **Stop:** 5B
- **Raised in:** pending
- **Steelman A:** pending
- **Steelman B:** pending
- **Author's position:** pending
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T9: The bitter lesson
- **Status:** open
- **Stop:** 1B
- **Raised in:** "What is software now?" (Movement 1), 2026-11-08. Drafting halted after "any claim to succeed the SDLC has to say where it stands among them.", before the CELC is positioned among the neighbouring terms.
- **Steelman A:** *Scale erodes handcrafted context.* Sutton's lesson is that "general methods that leverage computation are ultimately the most effective, and by a large margin", and that "We have to learn the bitter lesson that building in how we think we think does not work in the long run" (A24). Thoughtworks applied it to spec-driven development on 5 November 2025 (Radar Vol. 33): "We may be relearning a bitter lesson — that handcrafting detailed rules for AI ultimately doesn't scale." (B11). The one hands-on trial in the register points the same way: "I am a lot more productive without SDD, around ten times faster", after "2,577 lines of markdown" and "3.5 hrs review time" (C5, n=1, one app). If the CELC asks organisations to curate context by hand, larger windows, better retrieval and models that infer intent from code and tickets may make that work redundant, as Sutton's history predicts.
- **Steelman B:** *Context is not handcrafted rules.* Sutton's target is human knowledge about a domain built into methods, and he leaves room for exactly what context supplies: "we should build in only the meta-methods that can find and capture this arbitrary complexity" (A24). Organisation-specific intent, decisions and facts about an estate are data, not method, and no model can learn them from scale, because they are in no training corpus. Karpathy's definition is selection, not rule-writing: "filling the context window with just the right information for the next step" (B5). Thoughtworks's target is "handcrafting detailed rules", that is, spec-driven development, not context in general (B11), and Eberhardt's trial is of one spec toolkit on one app (C5). Naur adds that a program's theory is "inextricably bound to human beings" (A10, p.258), so someone has to externalise what agents need; scale does not do it for them.
- **Author's position:** pending
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T10: Reclaim "context engineering" or keep a distance
- **Status:** open
- **Stop:** 1B
- **Raised in:** "What is software now?" (Movement 1), 2026-11-08. Drafting halted after "any claim to succeed the SDLC has to say where it stands among them.", before the CELC is positioned among the neighbouring terms.
- **Steelman A:** *Reclaim the term.* "Context engineering" has dated, respectable origins: Lütke on 19 June 2025, "the art of providing all the context for the task to be plausibly solvable by the LLM" (B4), and Karpathy six days later, "the delicate art and science of filling the context window with just the right information for the next step" (B5). The CELC carries the term in its name, and D-19 rules out renaming to avoid a collision, so keeping a distance from one's own name would look evasive. Practitioners already tie the term to the lifecycle question: "The SDLC is dead. The new skill is context engineering." (B26). Reclaiming lets the essay say what the term should mean, in the open, and argue that the narrow sense (filling one window) is the first instance of a wider discipline, not the whole of it.
- **Steelman B:** *Keep a distance.* The term is now heavily vendor-coded (the naming-landscape research records vendor and certification uses; B10 is one such use), so taking it on brings their associations with it. Its own originators define it narrowly: both definitions concern filling one model's context window for one task (B4, B5), and Karpathy says outright that "context engineering is just one small piece of an emerging thick layer of non-trivial software" (B5). The essay's referent is far wider, all recorded human communication and thought in an organisation (thesis §2). Leaning on the term invites the reading "prompt engineering with a lifecycle", which is the deflationary reading the essay argues against. The CELC can keep its name as a label (D-19) while the essay defines context engineering on its own terms, and says that it differs from the vendor sense.
- **Author's position:** pending
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T11: A lifecycle of context, or through context?
- **Status:** open
- **Stop:** 1B
- **Raised in:** "What is software now?" (Movement 1), 2026-11-08. Drafting halted after "any claim to succeed the SDLC has to say where it stands among them.", before the CELC is positioned among the neighbouring terms.
- **Steelman A:** *Of: context is the managed unit.* The thesis defines context as any recorded human communication or thought (§2), and says it has a lifecycle and ages: records are superseded, descriptions drift from the code, transients should expire (§11.3). That is a lifecycle of an object, parallel to the SDLC as a lifecycle of software, and it gives the whitepaper and the SOPs a unit with stages to manage. The neighbours already read it this way, and honesty about kinship is a strength: Debois's CDLC runs Generate, Evaluate, Distribute, Observe because "The object moving through the pipeline isn't code. It's knowledge and intent." (B12); The Brick Learning calls context engineering "a practice, a continuous lifecycle" for enterprise data context (B10). Movement 1's own argument points here too: once software is data plus capabilities rendered in someone else's harness, what is left to engineer is the context that reaches it.
- **Steelman B:** *Through: context is the medium.* The CELC claims to succeed the SDLC, and what it produces is still software, now data plus capabilities; context is the medium through which code, decisions and operations are produced and interrogated (thesis §9.1: "context becomes the mediator"). Karpathy's Software 3.0 is a claim about medium, "your prompts are now programs that program the LLM... these prompts are written in English" (B2). Choosing "of" collapses the CELC into the CDLC (B12) and the Brick Learning lifecycle (B10), which is exactly the "just the CDLC renamed" objection D-25 pre-empts: Debois frames his lifecycle by analogy with DevOps, alongside code. The conservation claim also reads as "through": essential complexity (A8) moves into context, so context is where the software's complexity is managed, not a second artefact beside it.
- **Author's position:** pending
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T12: Naur against the CELC
- **Status:** open
- **Stop:** 2A
- **Raised in:** pending
- **Steelman A:** pending
- **Steelman B:** pending
- **Author's position:** pending
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## T13: What causes the reorganisation lag?
- **Status:** open
- **Stop:** 3A
- **Raised in:** pending
- **Steelman A:** pending
- **Steelman B:** pending
- **Author's position:** pending
- **Resolution in essay:** pending
- **Essay-only (tension 8):** pending

## Tension 8 outcome

The final pass lists here every claim the author flags essay-only in the entries above.
