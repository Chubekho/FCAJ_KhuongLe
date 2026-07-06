---
title: "Event 2"
date: 2026-06-08
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

## Event Report: FCAJ Community Day (Technical Session)

### Why I attended this event

This was my second time attending an FCAJ event, and this time I was even more excited since I already knew what to expect from the atmosphere. Unlike the previous session, which leaned more toward inspiration and career perspectives, this program announced 5 genuinely "heavyweight" technical topics — full of names that were completely new to me, like Deep Response Engine, Voice Agent, and MCP. It happened to line up with the exact moment I was wrestling with the SQS/Lambda asynchronous processing part of my own workshop project, so I figured: might as well go listen, maybe something useful would click and I could bring it back into my project, or at the very least I'd get a broader sense of where AI is heading beyond the labs I was already working through.

### Event information

| Item | Detail |
| --- | --- |
| Event name | FCAJ Community Day |
| Organized by | Huynh Hoang Long |
| Location | Bitexco Financial Tower, 2 Hai Trieu Street, Ho Chi Minh City |
| Time | 08:30 – 11:30, June 8, 2026 |
| Attendance | 325 people |
| Reference | [Event on Luma](https://luma.com/s1ymc95q) |

Same familiar venue up in the higher floors of Bitexco, but this time the atmosphere felt a bit more "dry and businesslike" than the last one — less of an opening mixer, and almost straight into technical content as soon as people settled into their seats. Probably because the organizers knew they had 5 sessions to squeeze into just 3 hours, leaving little room to linger.

### Sessions in the program

The program had 5 back-to-back technical sessions, each about 25-30 minutes, with almost no meaningful break in between — it felt more like grinding through a condensed course than a typical networking event:

1. **Deep Response Engine** (09:00–09:25) — a system that automatically detects and resolves cloud incidents without human intervention.
2. **Voice Agents** (09:25–09:55) — building AI voice assistants with Amazon Nova Sonic.
3. **AWS DevOps Agent** (09:55–10:20) — an AI "operations teammate" supporting DevOps 24/7.
4. **AI-Powered Productivity** (10:20–10:45) — applying AI to workforce management with Amazon Quick.
5. **Secure Private MCP Connection** (10:45–11:30) — secure MCP connectivity via VPC PrivateLink.

### My notes on each session

**On Deep Response Engine:** This opening session left me pleasantly stunned. The core idea is letting AI handle the entire lifecycle of an incident — from spotting an anomaly, tracing it back to the root cause, all the way to fixing it — without anyone staring at a dashboard overnight. The speaker talked about shifting the operations mindset from "wait for the alarm, then jump in" to "the system acts before a human even notices there's a problem." It sounded a bit like science fiction compared to the reality of my small project (I'm still debugging the old-fashioned way — opening CloudWatch Logs and scanning line by line), but it gave me a clear glimpse of where things are heading: operating a system is no longer just about "watching the screen."

**On Voice Agents:** This was probably the part that impressed me most in terms of raw numbers. The speaker emphasized that latency has to stay under 300 milliseconds, or the conversation starts feeling like the awkward, stilted pauses of old-school automated phone systems. I'd never really thought that such a small detail as latency could be the deciding factor in the entire user experience — for the kind of APIs I usually build (waiting a few seconds for AI to generate content), that delay feels perfectly acceptable, but for real-time voice it's clearly a completely different tier of problem, requiring a whole streaming infrastructure behind it rather than just calling an API and waiting.

**On AWS DevOps Agent:** The live demo on ECS was the moment I paid the most attention all morning, since it hit closest to home for my actual work. Watching the agent automatically detect a failing container and restart the service on its own, with no one pressing a button, made me chuckle remembering the times I've had to manually SSH into an EC2 instance at midnight just to restart a hung service. If a tool like this ever becomes accessible for a small project like mine, it would probably save a good amount of unnecessary "on-call" time.

**On AI-Powered Productivity:** Honestly, this was the part I understood the least, since the content leaned heavily into HR operations — a domain completely foreign to a technical person like me. But it did open up a new perspective: it turns out AI isn't just confined to the dev team anymore; it's quietly making its way into departments that seem to have nothing to do with technology at all, like HR or Finance. It felt a bit outside my expertise, but it was also a reminder that the scope of AI's application is much broader than I'd assumed.

**On Secure MCP Connection:** This was the longest session (45 minutes) and also the most "brain-melting" part of the whole morning for me. In essence, MCP is like a kind of "universal connector" that lets AI call into a company's tools, databases, and internal systems, instead of just answering chat prompts. The biggest headache raised was security: once you let AI "touch" internal data, how do you make sure that data never leaks out onto the public internet? The solution presented was running the MCP server inside a dedicated VPC, connected via PrivateLink — in other words, "locking" the sensitive data flow inside AWS's internal network so it never gets a chance to wander outside. The content was fairly advanced for my current level, and at times I couldn't quite keep up with every term, but I at least grasped the core issue and why people go through all that complexity instead of just letting AI call straight out to the internet.

### What I took away

* The "action-driven instead of alert-driven" mindset was probably the single most thought-provoking idea of the whole session — instead of just setting up alerts and waiting for something to go wrong before jumping in, it's entirely reasonable to consider letting the system handle certain familiar, recurring failures on its own, saving human effort.
* Latency, it turns out, is just as make-or-break as accuracy for anything involving real-time AI — not just voice, but really any interactive experience directly facing a user needs to keep this number in mind.
* MCP is a concept I've noted down to dig into further later, since it touches on something genuinely interesting: getting AI to actually "work" inside a real system instead of just sitting there chatting — even though my current project doesn't need that level yet.
* Zooming out, all 5 sessions circled around one shared theme: AI is gradually shifting from a role of "answering questions" to a role of "taking action" inside real systems — a trend I'll almost certainly keep running into in the years ahead.

### Overall impression

Compared to the previous FCAJ event I attended, this one was noticeably more technical, and the pace was a lot more relentless, so there were parts I couldn't fully keep up with — especially the MCP session at the end, by which point my brain was already a bit "overloaded" after four sessions in a row. Still, looking back, it was a worthwhile morning — getting to hear about the latest technologies firsthand, things that would have taken me a lot longer to stumble upon on my own through documentation, not to mention sitting among a whole community of people who share the same interest in AWS, which was a pretty enjoyable experience in its own right.

### Photos from the event

> ![Event photo](/images/4-Events/4.2-Event2/photo1.jpg)
>
> ![Event photo](/images/4-Events/4.2-Event2/photo2.jpg)