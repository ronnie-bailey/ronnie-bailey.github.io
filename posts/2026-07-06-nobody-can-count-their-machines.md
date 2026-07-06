---
title: Nobody Can Count Their Machines
date: 2026-07-06
tags: identity, nhi, governance, secrets-management
banner: posts/assets/nhi-banner.svg
summary: The industry says machine identities outnumber humans 10-to-1. Or 45-to-1. Or 100-to-1. The fact that nobody agrees within an order of magnitude is the actual finding.
---

Ask the industry how many machine identities exist per human employee and you'll get 10-to-1, 45-to-1, or 100-to-1, depending on which vendor's report you're holding. Those numbers can't all be right, and the spread is not a rounding error. It's an admission: nobody can count them. Not the analysts, and — more to the point — probably not you.

That's the honest starting position for non-human identity, and it's worth sitting with before anything else, because everything downstream depends on it.

## What we're actually talking about

A non-human identity is any credential that authenticates without a person behind the keyboard: service accounts, API keys, OAuth grants, workload identities, automation tokens, certificates. They run your integrations, your pipelines, your scheduled jobs, and increasingly your AI tooling. They don't take PTO, they don't get offboarded when their creator does, and they never call the help desk — which means they never generate the friction that forces human identity to be governed.

That last part is the whole problem in one sentence. Everything we built for human identity — MFA, access reviews, lifecycle tied to HR — assumes someone who joins, moves, and leaves. A service account does none of those things. It just persists.

## Where the conversation is versus where you are

The 2026 industry conversation has moved on to the exciting part. Agentic AI identities. Autonomous workflows with real authority in production systems. Secretless architecture, ephemeral tokens, continuous attestation. NIST is drafting guidance on governing AI agents like any other workload. The vendor category has consolidated, matured, and produced genuinely capable platforms.

Meanwhile, the survey data from the trenches tells a different story. The Cloud Security Alliance found that fewer than a quarter of organizations have formal, documented policies for creating or removing AI-related identities, and a meaningful share don't track their creation at all. Strip away the AI framing and the picture underneath is older and worse: most environments cannot produce a complete NHI inventory, cannot name an owner for what they can inventory, and are still running static keys that were pasted into a config file during an integration project three fiscal years ago.

![The gap between the 2026 industry conversation and most real environments](posts/assets/nhi-gap.svg)

Here's the thing I want to be careful about, because it's where most commentary goes wrong: **being behind the industry conversation is not automatically a failure.** The conversation is set by vendors and analysts, and it runs ahead of buyer reality by design — that's how markets work. An organization that deliberately ignores agentic identity governance this year because it's still establishing basic ownership of its service accounts is making a defensible, sequenced decision. I'd respect that roadmap.

But that's not what most of the lag is. Most of the lag is unexamined. Nobody decided to defer the problem; the problem was simply never on anyone's plate, because NHIs sit in the seam between security, identity, and engineering, and seams don't have owners. The risk isn't being behind the conversation. The risk is not knowing by how much.

## Why this compounds now

Two things changed the math. First, the environments generating these identities got faster — every cloud service, pipeline, and SaaS integration mints credentials as a side effect of normal operation. Second, AI tooling arrived, and it didn't create a new identity problem so much as pour accelerant on the old one. An AI agent with an OAuth grant is, mechanically, a service account that makes its own decisions at machine speed. If your governance couldn't keep up with credentials created by humans, it definitely can't keep up with credentials created by software.

Attackers understood this before most defenders did. The modern playbook rarely bothers with password spraying humans behind MFA. It looks for the long-lived, over-privileged token that no one is watching, because that credential offers everything the attacker wants: standing access, no second factor, no behavioral baseline, and — in most shops — no one who would notice it's gone.

## What I'd do first, in order

Not a framework. A sequence. The order matters more than the tooling.

1. **Count.** Get an inventory, even an ugly one. Cloud IAM exports, directory service account queries, OAuth grant reviews in your major SaaS platforms. You are not aiming for perfect; you are aiming for a number you can defend.
2. **Assign ownership.** Every NHI maps to a team or a role — never to a person, because people leave and their credentials don't. This is the unglamorous step everyone skips, and it's the one that determines whether anything after it works.
3. **Find what's exposed.** Keys in repositories, credentials in shared drives and collaboration platforms, tokens in wikis. This is consistently where the worst findings live, and it requires no purchase to start looking.
4. **Then, and only then, automate.** Rotation, just-in-time issuance, lifecycle tied to the owning team. Automation applied before ownership just industrializes the neglect.

If your organization is somewhere on steps one and two while the conference keynotes are on step nine, you're not failing. You're in the majority — the majority just doesn't publish survey responses saying so. The failure mode is pretending otherwise, buying the step-nine platform, and pointing it at an estate nobody owns.

Start by counting. The number will be worse than you think, and that's exactly why it's the right place to start.
