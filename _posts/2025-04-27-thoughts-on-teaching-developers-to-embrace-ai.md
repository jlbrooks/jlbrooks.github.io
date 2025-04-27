---
layout: post
title: Thoughts on teaching developers to embrace AI
subtitle: 
tags: [AI, software-development]
comments: true
---

I'm thinking a lot about AI-assisted software development at work. I believe that it will (already is?) transform how software engineers build systems - I don't think we'll be out of a job, but I do think it'll be a shift on the order of the transition from assembly code to building a web application with the Django framework.

# The problem: old patterns, old solutions
My challenge right now is, how do I teach these skills and encourage the developers on my teams to learn this new paradigm? I've been asking the question "How are you using AI?" in 1:1s for the past 8 weeks or so and common answers are:
- I use it every once in a while, but it gets things wrong
- I tried to use it a couple times but don't reach for it automatically.
- I forget to use it

Most engineers are solely using the "smart-autocomplete" feature in vscode, with a few engaging in more intentional highlight->edit mode interactions, and fewer still interacting with chat/edit/agent mode directly alongside the codebase. So I'm asking myself: Why is this the case? Why aren't devs fully embracing the tools? I see a few possible explanations:
1. The AI doesn't actually work
2. The devs don't have the skills to use the tools well
3. The devs aren't aware of what the tools can do
(maybe a 4th option - the devs actively refuse to use the tools in a futile attempt to retain job security, but I can't do much to positively fix that)

I believe that the main issue is a combination of (2) and (3), in a way that leads most people to believe in (1). Where we're at right now, in my opinion:
- It's hard to use AI well
- The common tools to use AI aren't good at teaching you how to use AI well.

Unfortunately for Microsoft (sorry Kaitlin!), I think that the VsCode interface is pretty bad for learning effective AI development. It's too close to the editor, which makes it _extremely_ easy to give up the second that it stops working perfectly. This is not conducive to learning! To learn a new skill you need to struggle, iterate, and try new things. Combined with the fact that effective AI usage requires thought and intention, the interaction loop of "type something, AI suggests something that is just ok, use it or move on" does not lead to unlocking the potential of this new tool.

# The solution: New tools for new patterns
With the state of AI tools today, I think that a radical shift in mentality is critical to effectively harnessing the technology. Folks like [Andrej Karpathy](https://x.com/karpathy/status/1915581920022585597) and [Simon Willison](https://simonwillison.net/2025/Mar/11/using-llms-for-code/) have advocated for a development loop that looks like:
1. Put everything relevant into the model context
2. Describe a change that you want to make, and ask for potential solutions (not code!)
3. Choose one of the proposed solutions and ask for an implementation plan
	1. Bonus points: Ask it to write this implementation plan down in a file to reference later
4. Ask the model to work on the implementation plan, step-by-step
5. Test and iterate.
6. Ask another model for review of the implementation, and suggestions for improvements

You can't do this kind of development with a fancy autocomplete! This is much closer to how you'd interact with a developer that you're managing than actually writing code today. To that end, then, I think that a general-purpose text editor with some LLM interfaces bolted on is the worst way to learn this kind of development. You need to immerse yourself 100% in the new model: *You're not writing code, you're directing something else to write it.*

So, with all of the above in mind, I think that [Claude code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview) or [OpenAI Codex](https://github.com/openai/codex)  are currently the best way to fully embrace AI development and train yourself to learn this new skill. You are creating new pathways, new patterns, new techniques to build software, so you need to isolate yourself from the tools that you feel comfortable with. Can you make a PR without editing a single line of code yourself? Can you get the AI to run tests for you? Can you get the AI to run the code and interact with APIs for you? It's much easier to ask these questions and try to answer them when you can't fall back onto your old habits. Embrace the AI!

I do think that the editor will remain important, and that in the long term we'll figure out how to effectively embed AI tools. Cursor or Windsurf may already be there, at least for the experienced practitioner. That experience is key, though, and for the learning stage that 99% of developers are in I think that the radical shift in approach and thinking is critical to ramp up on AI-driven development.
