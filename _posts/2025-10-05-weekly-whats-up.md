---
layout: post
title: 10/5/2025 Weekly what's up
subtitle: 
tags: [weekly-whats-up, investing]
comments: true
---

# What I'm reading
Paid for [Citrini Research](https://www.citriniresearch.com/) to get behind the paywall and catching up on his investing themes from this year. His [Investment philosophy](https://www.citriniresearch.com/p/the-citrindex-part-one-redux-investment) is free and a good read. Overall I find this compelling. The smart play is still broad index funds for the majority of people, and for the majority of my capital, but I think that there is room for direct stock allocation if you have strong beliefs. That has worked out well for me this year in two ways:
- Believing that Trump was serious about tariffs before liberation day -> bought SPX puts that did quite well.
	- Granted, I have _lost_ money on puts after this (but still up ~500% overall), some overconfidence after that initial win. Attributing that to not quite as solid of beliefs and have since dialed back.
- Believing that Google is one of the strongest AI players and was criminally undervalued -> Bought GOOG in May at $170 (now $245).

A bit of confirmation bias after these successes, maybe? But I do believe that the world is changing rapidly and there are gains to be had by being more intentional about investment.

Plus, this has led to a fun development project (see below).

# What I'm playing
- Silksong can be a lot, and not always what I'm looking for so I picked up [Deep Rock Galactic: Survivor](https://store.steampowered.com/app/2321470/Deep_Rock_Galactic_Survivor/) after it's 1.0 release and it's been a nice casual experience. The single stick vampire-survivors-like fits perfectly with the DRG theme.

# What I'm up to
The Citrini thematic baskets contain between 30 and 70 weighted individual stocks (a fair number of which are international), along with some short positions. There is some rebalancing every quarter as well. This would be quite the chore to manage manually, but is of course a natural task for computers.

Most brokerages don't let you build-your-own basket like this. I think fidelity might, but a) I'm not a customer there and b) it seems like it has some limitations. After a conversation with Claude+research, I landed on building an application using the Interactive Broker's API (it helps that I already have an account). No way I would have done this a couple of years ago, but after ~2 hours with Claude Code I'm like 80% of the way to a working prototype.

Vibe-coding a portfolio manager hooked up to your real investment account - what could go wrong?? Taking a bit more care and incorporating more of the practices we're using at work, compared to building the [learn to golf app](http://learntogolf.jlbrooks.tech/) or other toy apps.
