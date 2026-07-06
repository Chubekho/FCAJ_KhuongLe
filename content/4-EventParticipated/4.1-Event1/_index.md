---
title: "Event 1"
date: 2026-05-23
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

## Event Report: FCAJ Community Day

### Why I attended this event

While going through the AWS learning path with FCAJ, I saw a post in the community group about the FCAJ Community Day — bringing together many people in Vietnam who are also learning and working with AWS. I registered mainly to hear real-world perspectives from people already working in the field, instead of just learning from documentation.

### Event information

| Item | Detail |
| --- | --- |
| Event name | FCAJ Community Day |
| Organized by | Huynh Hoang Long, Thien Lu & Tran Dai Vi |
| Location | 26th Floor, Bitexco Financial Tower, 2 Hai Trieu Street, Ho Chi Minh City |
| Time | 08:30 – 12:00, May 23, 2026 |
| Attendance | 399 people |

One thing I noticed that was different from typical tech conferences: the speakers weren't outside experts invited in, but people from within the community itself — recently employed engineers and former students just like us. That made it feel a lot more approachable and relatable.

### Sessions in the morning program

The program had 6 sessions spread evenly over 3 hours:

1. **Context Is Everything** — why AI gives poor answers, and how to improve it by giving AI enough context.
2. **Amazon QuickSight Q** — an AI assistant for querying data in natural language, no SQL required.
3. **CloudFront: From Edge to Origin** — CloudFront isn't just a CDN; it also handles security, cost optimization, and performance.
4. **36 Hours at LotusHacks** — the journey of building the UTMorpho product from idea to demo.
5. **Why "Deterministic" LLM Settings Aren't Actually Deterministic** — a common misconception about Temperature=0.
6. **Multi-Agent System for Startup Credit Scoring** — a case study using multiple coordinated AI agents instead of one agent doing everything.

### My notes on each session

**On Context for AI:** This part made me realize something fairly basic that I hadn't really paid attention to before — AI gives bad answers not because the model is weak, but usually because we didn't give it enough information. The speaker mentioned building up a kind of personal "context memory" over time, instead of re-explaining everything to the AI from scratch every time.

**On QuickSight Q:** What impressed me most was being able to build a dashboard just by describing it in words, with the AI picking the right chart type on its own. For someone not very comfortable with SQL like me, that's a genuinely useful feature.

**On CloudFront:** I used to think CloudFront was simply "a cache that makes a website load faster." After this session I learned it also handles security (WAF, Shield, geo-blocking) and has its own mechanism to lock down an S3 bucket so only CloudFront can access it (called OAC) — which is actually relevant to the infrastructure work I'm doing on my own project.

**On the 36-hour hackathon:** This part wasn't very technical, more about teamwork experience. What stuck with me most was that the team chose to drop two major features near the end to keep the demo stable — better to have fewer features than a broken demo.

**On non-deterministic LLMs:** This was the part that surprised me the most, since I used to think setting Temperature=0 meant the AI would always give the exact same answer every time. Turns out that's not the case — due to how calculations run on hardware (GPUs) and how the model gets split across multiple machines, results can still vary slightly even for the same question.

**On Multi-Agent credit scoring:** The problem was that startups often struggle to get loans because banks don't have enough data to evaluate them properly. The solution used multiple AI agents, each handling a separate piece (data collection, financial analysis, market assessment, etc.) and then combining the results — instead of making one agent handle everything.

### What I took away

Overall, this session gave me a few things I can apply right away to my own studying and project work:

* When using AI to help with code or documentation, it's better to describe the context in detail (what I'm working on, what tech stack, what constraints) rather than asking a bare-bones question — the quality of the answer changes noticeably.
* CloudFront isn't just for speed; it's also the first security layer in front of a system — directly relevant to choosing a CDN for my own workshop project later on.
* I shouldn't assume AI output is always perfectly consistent — if my system depends on AI, there needs to be a step to verify the result before using it.
* When building a real product (even a small assignment or project), knowing when to stop and keeping the core stable matters more than trying to cram in more features.

### Overall impression

This was the first time I attended a tech community event of this scale. What I liked most wasn't necessarily the technical content (some parts were fairly advanced and I didn't fully follow everything), but the feeling of sitting among so many other people also learning AWS — it felt a lot less isolating than studying alone at home.

### Photos from the event

> ![Event photo](/images/4-Events/4.1-Event1/photo1.jpg)
>
> ![Event photo](/images/4-Events/4.1-Event1/photo2.jpg)
>
> ![Event photo](/images/4-Events/4.1-Event1/photo3.jpg)
>
> ![Event photo](/images/4-Events/4.1-Event1/photo4.jpg)