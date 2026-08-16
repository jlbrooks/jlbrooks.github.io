---
layout: post
title: Eight years at GoDaddy (Part 1)
subtitle:
tags: [career]
comments: true
---

July 15 was my last day at GoDaddy after eight years (of full time work - if you count my internships, I was involved with the company for eleven years!). That's a long time, and even more it's the only company I've worked for in my full-time career - pretty uncommon in tech these days! Every 18 months or so for the past ~4 years I'd ask myself "is it time to move on yet?", and the answer continued to be "no, still learning, still growing" each time. I think that this says a lot about GoDaddy and the mentors and leaders that I had there, I couldn't be more grateful for the opportunities I had and all of the wonderful people that I worked with.

This post and the next will chronicle my time there while it's fresh, loosely organized into four chapters.

## Chapter 1: Growing as an engineer
2018-2021. Working as an IC, growing and learning. The authentication team offered no shortage of interesting things to work on, a few highlights stuck with me:
- GDPR. Shortly after I joined I worked on the auth team's part in the companies GDPR-compliance rollout - consent for marketing, hooray! I was responsible for a tiny piece of UI to collect consent on account create, but got my first window into some of the inter-company tensions that arise between marketing, product, engineering, and legal: Marketing pushing hard for... not quite "dark patterns" but certainly trying to find the boundary of the new law with respect to defaulting opt-in and what we would show. The way in which my engineering leaders took a hard stance for the user stuck with me.
- Migrating from on-prem to AWS. ~100 on-premise VMs across two datacenters, on-premise Cassandra, internally managed A10 load balancers, Jenkins-managed RPM deploys via Salt. This was a great place to start my career, and I learned a lot about remote server management from the talented senior engineers that set it up. SSHing into the salt master, running commands across a fleet, using screen/tmux, editing with vim... all skills that stuck with me. But the big thing was the move to AWS - going from this to EKS and DynamoDB without downtime! Huge migration effort and I learned the core pattern to do this well: Build a translation layer in the app in the db module, do a big bulk migration, dual-write to catch up and keep things current, switch reads to the new source, and turn off dual write once you have confidence.
- Fighting attackers at scale. Early 2022 and the onset of the pandemic brought about large-scale and persisted credential stuffing attacks against our platform. The cat-and-mouse game of trying to identify patterns was challenging but fun - after a bit I could tell where they were located because of when they would wake up and shift patterns to defeat our latest mitigation! Working on long-term fixes here was illustrative in the core tension in the auth space: friction for your real users vs. security against bad actors. The most secure system is one that can't be accessed - but that's not very useful, is it!

Towards the end of 2021 I was thinking about what was next, and had a choice. I was interested in management, and could have transitioned into a line manager role with a small team focusing on infra under my current manager. Or... my skip manager proposed another option that he preferred: I stay an IC but start reporting to him and work more broadly across the Identity group (~3 teams at that time). The choice is obvious now in hindsight but I was conflicted at the time. I remember a conversation with my dad asking his advice, his very simple answer was along the lines of "When a senior leader is giving you an opportunity, just say yes". I did, and of course the new role gave me new opportunities and set me on the path to impact at scale that I don't think I would have had if I'd transitioned into management at that time.

Next up: Staff and principal engineering across the Identity group.
