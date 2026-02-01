---
layout: post
title: "Specmark: annotating markdown specs for AI feedback"
subtitle:
tags: [AI, software-development, projects]
comments: true
---

The idea came to me in the AI coding frenzy this holiday season as I was burning through the extra Anthropic API limits and experimenting with development via my iPhone and Termius. For bigger features, I try to follow a spec-driven development model: Ask the agent to write a spec and iterate on it before actually writing any code. This is what Claude Code's Plan mode does, and you can get pretty far with that and just interactively asking questions.

There comes a point, though, when you really should _actually read the whole spec_. At least, if you care a bit about the code or want to give the implementing agent the best chance at one-shotting the feature. I'd do this in the editor, which was fine for making changes but if I wanted to give the planning agent broader feedback a couple of things annoyed me:
- It's hard to reference specific lines. You could type out "in the auth section..." but that's extra typing, exactly what I'm trying to avoid!
- It was practically impossible in Termius, and any extra typing there is more painful.

I thought of how I do this professionally - we have a pretty strong writing culture, and I am always reviewing documents and adding inline comments in Word or Confluence. Why not bring that same experience to editing markdown?

## What is Specmark?
[Specmark.dev](https://specmark.dev/?view=annotate) is a lightweight tool that allows the user to:
1. Paste markdown content
	1. Or, "teleport" it to the site from anywhere using short-lived share codes
2. Annotate the rendered markdown content with comments, a la' Readwise Reader or any review mode like in Word or Confluence
3. Copy the comments made with context like line numbers and the quoted content to the clipboard in order to be fed back to an LLM.

Everything except for the share-code feature is local in the browser. There is also a [small cli tool](https://specmark.dev/cli/specmark) to make the share code easier to use and import markdown files directly.

Here's the code: [github.com/jlbrooks/specmark](https://github.com/jlbrooks/specmark). This is also an experiment in fully AI-driven development — 99% of the code was generated without detailed review.

## Challenges building it
The highlighting interaction took way more iteration than I expected. I had a kinda-crappy version working within a couple of hours — maybe 25% of the total time I spent on the project. Getting to "done" was the real work. This is an area I have no familiarity with, and is not a super common thing - maybe not "in distribution" for LLMs compared to other interactions. I spent too much time in some form of "make it better!!" loop which was not fun and not efficient. I eventually got to an ok place by giving it browser access and pointing it at the Readwise Reader interface for inspiration.

The other area where I would have struggled was design. The first iteration website was... fine... but not great. Thankfully I am married to a fantastic visual designer, and Kaitlin whipped up the outline of what you see on the site now in an hour or so in Figma. I pointed the LLM at the Figma MCP and the look and feel of the site increased tenfold.

## What I learned
**Human expertise is still critical**. The highlighting experience was instructive for me. Many of my LLM interactions on software until now have been on topics that I have a decent understanding of, know the pitfall, know what decent approaches look like, etc. When that's true, it's very easy for me to:
1. Set the agent on the right course from the start
2. Course-correct when things are getting off the rails
3. Throw away bad implementations and try again

I had none of this expertise (or "taste") on highlighting in the browser. This made development so much harder as I was flying blind. In hindsight, a better path may have been something like:
1. Use the agent to try and learn the space. Have it go read APIs, blog posts, etc. and come back with reports.
2. _Actually read and internalize this myself_. I think it'd be easy to skip this step and just feed the report into the implementation planning agent, and that might work pretty well, especially for a small side project. But for bigger important features and long-running projects that will need to evolve over time I believe that it is critical for the human operator to internalize these details.
3. Take those learnings and start the implementation as usual - write a spec, review, iterate, and then execute.

Maybe another year of model development will make this irrelevant, and I'm sure that there will be many successful projects where the operator has little to no understanding of the internals or interfaces used. Hell, this is kind of true in general of software - we build on abstractions, most web devs do not know and do not usually need to know the details of TCP networking or TLS. But those that do are more successful and more valuable, and I believe that will continue to be the case.

## What's next?
I'm pretty happy with the tool as-is and don't have any plans for the web version. An obvious next step is some sort of native experience - why can't I do this in my editor or terminal? Could a history of these comments be persisted somehow into the project history so that future agents can internalize the feedback?

I think that this broadly falls in a similar space as "local code review of agent work", a problem that I know many people are working on. Excited to see how the space develops, maybe I'll try to make my own contribution.
