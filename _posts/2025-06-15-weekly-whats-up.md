---
layout: post
title: 6/15/2025 Weekly what's up
subtitle: 
tags: [weekly-whats-up]
comments: true
---

# What I'm reading
- Consuming all I can about how people are effectively integrating AI into their software development workflows. [Field notes from shipping real code with Claude Code](https://diwank.space/field-notes-from-shipping-real-code-with-claude) this week was good.
	- The "Anchor comments" for AI is interesting, a nice supplement to a repo-level `CLAUDE.md`.
	- The assertion "Never let AI write tests" is counterintuitive to how a lot of engineers I talked to started using AI (auto-generate tests!), but rings true with my limited experience. Too easy to accidentally mold code to incorrect tests.

# What I'm playing
- I played through [Dredge](https://store.steampowered.com/app/1562430/DREDGE/) over the past couple of weeks. Fun little game, a nice break from heavier stuff that I've been playing.

# What I'm up to
I used Claude Code to write a couple of simple apps last night:
- A "Learn to golf" tracker that is a simple interface to the [Operation 36](https://operation36.golf/) method to progress through golf learning. Kaitlin tried to sign up with their app this week and it's oddly linked to finding a local program? Luckily we're in a new era of personal apps! This took me ~2 hours and $9 of Anthropic credit. It would have been faster but I intentionally took a methodical approach that I'd use for a more complex web application.
	- Site: [learntogolf.jlbrooks.tech](https://learntogolf.jlbrooks.tech/)
	- Github: [github.com/jlbrooks/learntogolf](https://github.com/jlbrooks/learntogolf)
- The start of an interface to view history of a Claude.code working session. Claude code stores these histories on your machine, with full detail on all messages and tool calls. At work I've found myself wanting to preserve and share these for demonstration purposes - technique is so important! Local-only for now, but I think a hosted version where you can upload and share would be nice.
	- Github: [github.com/jlbrooks/claude-code-history-viewer](https://github.com/jlbrooks/claude-code-history-viewer).
