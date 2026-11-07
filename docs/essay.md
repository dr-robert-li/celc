## What is software now?

What is software once agents produce and operate it?

I mean the question literally. In November 2017 Andrej Karpathy argued that neural networks "represent the beginning of a fundamental shift in how we develop software", and drew the line in two sentences: "Software 1.0 is code we write. Software 2.0 is code written by the optimization based on an evaluation criterion" (Karpathy, 2017). In June 2025 he went a step further, giving the large language model "a new designation of Software 3.0" on the grounds that "your prompts are now programs that program the LLM. And remarkably, these prompts are written in English" (Karpathy, 2025a). By February 2026 he was describing a working day in which "you are not writing the code directly 99% of the time, you are orchestrating agents who do and acting as oversight" (Karpathy, 2026). Three statements from one practitioner, spread across a little over eight years, each further from the idea that software is something a person types. The question is no longer hypothetical.

The received view in our industry is that none of this changes what software is, only how quickly it can be made: the same lifecycle, with its slow parts compressed. I will come to who holds that view, and in what words, later in this movement. I think it is wrong. This essay argues that software itself is being redefined, not merely sped up, and that its lifecycle has to change with it.

Before I go on, I should say where I stand, because it shapes what I look for. I am an actor-network theory practitioner by doctorate (Li, 2020), a historical materialist (Li, 2011), and now a CTO, which means I spend my working days on the question above with a budget attached. I will use each lens where it explains best, and say so when they pull against each other. After this paragraph the argument has to carry itself.

I will start with the thing itself, before its lifecycle: first what is being stripped out of software, then what is left.

For as long as most of us have built it, software has carried two things at once. One is the what: the data, rules and operations a business needs. The other is the how: the particular sequence of screens, fields, menus and confirmations through which a person was expected to get at them. The two were shipped together because they had to be, since nobody could reach the what except through somebody's how. That coupling is coming apart, and the how is the half being stripped away.

It helps to be blunt about what the how always was. A user interface is an opinion: a vendor's judgement about the lowest common denominator of how its users would want to work, fixed in layout and shipped identically to everyone. Some of those opinions were very good. They were still opinions.

Chat is a different kind of interface, because what it asks of the user is something they already have. It is built on reading and writing, skills that are learned but learned universally, so language is a standard that already exists at a scale no interface designer could build. That is the force of Karpathy's "remarkably" (Karpathy, 2025a): the programs are now written in the medium their users already read and write. Gesture or eye contact might be more intuitive still, but they carry too much individually particularised meaning for a model's averaging to capture, short of training a vision model on one person. Language is the human-native interface that already scales. Where a picture is needed, a chart, a diagram or a model in three dimensions can be rendered alongside the text.

Strip the how out and what remains is the what, made available: data, and the capabilities to act on it, exposed through an API, an MCP server, an agent-to-agent protocol or direct access to the data layer. In effect, a store and a pipeline over it, with the rendering done at the other end, in whichever harness and model the user happens to be working through. The screen moves to the far end of the wire.

## References

Karpathy, A. (2017) "Software 2.0", *Medium*, 11 November, <https://karpathy.medium.com/software-2-0-a64152b37c35>.

Karpathy, A. (2025a) "Software Is Changing (Again)", keynote address, YC AI Startup School, 17 June, <https://www.youtube.com/watch?v=LCEmiRjPEtQ>.

Karpathy, A. (2026) Post on X, 4 February, <https://x.com/karpathy/status/2019137879310836075>.

Li, R. (2011) *'Killing the Noob': A Thesis on Meritocracy and What It Has to Do with Massive Multiplayer Online Role Playing Games*, Bachelor of Arts (Honours) (Media, Games and Multimedia) thesis, Swinburne University of Technology.

Li, R. (2020) *Reconceptualizing MMORPG Play: A Study on Actor-Network Theory in Practice*, PhD thesis, Swinburne University of Technology.
