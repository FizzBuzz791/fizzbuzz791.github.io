# The End of Copy & Paste?

_A while ago I wrote about my experiments using Large Language Models (LLMs) to build real software. Since then, I've continued developing several side projects, most notably [SetForm](https://setform-app.netlify.app) and, more recently, [Kindrel](https://kindrel.netlify.app). While the models have undoubtedly improved, the biggest change hasn't been the technology itself. It's been the way I work with it._

When I first started experimenting with AI-assisted development, I treated ChatGPT much like an incredibly knowledgeable colleague. I'd ask questions, generate code, refine requirements and bounce ideas around. It was useful, but it still felt like another tool in my toolbox.

Looking back now, I've realised the biggest productivity gains haven't come from newer models. They've come from removing friction from the workflow surrounding them.

## The first workflow

When I was building SetForm, my workflow looked something like this:

```text
Idea
 ↓
ChatGPT
 ↓
Generate GitHub Issue
 ↓
Copy Markdown
 ↓
Paste into GitHub
 ↓
Assign to Copilot
 ↓
Review Pull Request
```

I'd spend time thinking about the feature, ask ChatGPT to flesh out the requirements, generate a GitHub Issue, paste it into GitHub, then assign it to GitHub Copilot.

Copilot would usually produce a solid first implementation, particularly for smaller, well-defined pieces of work. My role shifted from writing every line of code to reviewing the implementation, making adjustments where needed and deciding what came next.

For a while, this felt revolutionary.

More importantly, it changed _how_ I worked. Instead of sitting at my keyboard implementing every feature myself, I could queue up a piece of work, let Copilot get started, and spend that time planning the next feature, reviewing another pull request or simply stepping away from the computer. Development became much more asynchronous.

## The surprising bottleneck

As I built more features, something became obvious.

The slowest part of the process wasn't the AI.

It was me.

Every feature involved a surprising amount of context switching:

- Switching between ChatGPT and GitHub.
- Copying markdown.
- Pasting descriptions.
- Creating issues.
- Assigning work.
- Waiting for implementations.
- Returning to ChatGPT to plan the next feature.

None of these tasks were difficult, but they added up. The workflow was smooth enough that I hadn't really noticed the overhead until I looked back at how often I was repeating the same sequence.

Ironically, I had become the integration layer between two AI tools.

## Removing the copy and paste

The first improvement came from ChatGPT's GitHub integration.

Instead of asking:

> "Generate a GitHub Issue."

I could simply ask:

> "Create the GitHub Issue."

That tiny change removed an entire step from the workflow.

No copying.

No formatting.

No creating issues manually.

It sounds insignificant, but after creating dozens of issues across multiple projects, it became one of those quality-of-life improvements that you quickly stop thinking about until you have to go back.

More importantly, it encouraged me to think about outcomes rather than artefacts. I wasn't asking for markdown anymore. I was asking for work to be queued.

## Discovering Codex

Around the same time, I discovered another limitation.

GitHub Copilot had become such a regular part of my workflow that I eventually exhausted my monthly AI allocation.

Rather than simply waiting for my credits to reset, I decided to experiment with Codex Desktop.

Getting started wasn't entirely frictionless. I primarily develop using WSL, so there was a little bit of setup required before everything was working smoothly. Once that was behind me, though, it became another opportunity to refine the workflow.

One thing I quickly discovered is that Codex doesn't simply replace Copilot.

It expects a little more guidance.

Initially my prompts were fairly minimal:

> Implement Issue #42.

The results were good, but inconsistent.

After a bit of experimentation, the prompts gradually evolved into something much closer to an implementation playbook:

> Ensure you're on the latest `main` branch, pulling the latest commits if necessary. Create a feature branch for Issue #42, implement the acceptance criteria following the repository conventions, run the appropriate checks, commit your changes, push the branch and open a pull request. If any manual steps are required, document them clearly in the PR description.

That's still only a short prompt, but it consistently produced pull requests that were ready for review.

The interesting part wasn't that Codex needed more instruction. It was that refining those prompts also forced me to think much more carefully about the engineering process itself.

## Better issues create better software

One unexpected lesson from both SetForm and Kindrel is that writing a good GitHub Issue has become a valuable engineering skill.

A well-written issue now serves multiple audiences:

- Future me.
- Human contributors.
- AI contributors.

Good acceptance criteria remove ambiguity regardless of who's implementing the feature.

Breaking work into smaller, independent tasks improves review quality regardless of who's writing the code.

Clear repository conventions help every contributor produce more consistent pull requests.

In hindsight, these were always good software engineering practices. AI simply made the benefits much more obvious.

## It's not about the model

Looking back, I don't think the biggest improvements came from moving between ChatGPT, Copilot and Codex.

They came from improving the workflow around them.

Instead of asking AI to write code, I started asking it to perform complete units of engineering work.

Instead of generating markdown, I asked it to create GitHub Issues directly.

Instead of relying on a single assistant, I used different tools where they fit best.

Each change removed a little more friction.

Individually, none of them felt revolutionary.

Collectively, they transformed the development experience.

## Where to next?

I'm still experimenting.

Kindrel continues to be my playground for refining this workflow, and I suspect the process will continue to evolve just as quickly as the models themselves.

One thing I'm increasingly convinced of, though, is that AI-assisted development isn't about finding the "best" model.

It's about designing a workflow where humans and AI complement each other's strengths.

For me, that means spending less time copying and pasting, and more time thinking about the problems worth solving.
