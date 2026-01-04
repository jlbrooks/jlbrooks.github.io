---
layout: post
title: 1/4/2026 Weekly what's up
subtitle:
tags: [weekly-whats-up]
comments: true
---

# What I'm reading
Unhinged stuff from the creator of [Beads](https://github.com/steveyegge/beads): [Welcome to Gas Town](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04). I've been using beads and I like it, though it feels a bit excessive, token heavy, and over-engineered at times. Love that it's just local and uses git, nice for syncing between agents and having them create issues themselves.

Gas town builds on beads and takes it to another level: a full-on agent orchestration system. He analogizes to Kubernetes, a comparison that resonates with me. Explaining the core of what Kubernetes is was a favorite interview question of mine for prospective engineers with infra focus: it's a state reconciliation machine. You say what you want, that is stored in etcd, and it has many controllers that try to make that state a reality. Gas Town does the same but for... actual feature development with multiple agents coordinating? It's a lot. I mean..

> If I tell the Mayor, "Our tmux sessions are showing the wrong number of rigs in the status bar — file it and sling it", the Mayor will file a bead for the problem, and then `gt sling` it to a polecat, dog, or crew, depending on how it feels as a factory chimpanzee that day.

He describes 8 stages of AI development:

```
  Stage 1: **Zero or Near-Zero AI:** maybe code completions, sometimes ask Chat questions
  Stage 2: **Coding agent in IDE**, permissions turned on. A narrow coding agent in a sidebar asks your permission to run tools.
  Stage 3: **Agent in IDE, YOLO mode:** Trust goes up. You turn off permissions, agent gets wider.
  Stage 4: **In IDE, wide agent**: Your agent gradually grows to fill the screen. Code is just for diffs.
  Stage 5: **CLI, single agent. YOLO**. Diffs scroll by. You may or may not look at them.
  Stage 6: **CLI, multi-agent, YOLO**. You regularly use 3 to 5 parallel instances. You are very fast.
  Stage 7: **10+ agents**, **hand-managed**. You are starting to push the limits of hand-management.
  Stage 8: **Building your own orchestrator**. You are on the frontier, automating your workflow.
```

This past week I've been between stage 5/6 - I guess I need to up my game before trying out something like Gas Town ;) And also up my Claude subscription...

# What I'm playing
I have a 2026 goal to play every game in my collection (burn down?). This past week: Two plays of [Patchwork](https://boardgamegeek.com/boardgame/163412/patchwork). Such a tight little two-player, I love it!

# What I'm up to
Writing (telling agents to write) lots of code! This has been a very fun two weeks, enabled by the enhanced Claude usage limits and my Termius->Claude-box connection. So many things seem possible now, and I feel very much like the bottleneck to getting stuff done - agents can write code faster than I can give them instructions! I'll be continuing to invest in improvements to this workflow and raising my level of abstraction throughout the year.

But - I want to actually ship too, and not get nerd-sniped every other day by a little side idea that I spend 2 hours on then leave in the dust. Another 2026 goal is to actually finish and ship stuff. My thinking right now is 4 projects (1x/quarter) that are polished enough to write up on the blog, permanently post to my projects page, and post on HN/equivalent. Plus a stretch - one project that I hook up some form of monetization/payment. Gotta pay for those tokens somehow!

# What I'm writing
I wrote up my [favorite video games of 2025]({{ '/2026-01-02-my-favorite-video-games-of-2025/' | relative_url }}). Next up - an outline of my 2026 theme/goals, and a full writeup of the Specmark app.
