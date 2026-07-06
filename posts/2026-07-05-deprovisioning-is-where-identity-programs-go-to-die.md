---
title: Deprovisioning Is Where Identity Programs Go to Die
date: 2026-07-05
tags: identity, lifecycle, deprovisioning, governance
summary: Every organization I've walked into has a polished onboarding story and a leaver process held together by tribal knowledge. Here's why that asymmetry exists and how I reason about fixing it.
---

Every identity program I have walked into over fifteen years has had the same shape: a reasonably polished joiner process, a mover process that mostly works if HR remembers to update the record, and a leaver process held together by tribal knowledge and a shared spreadsheet somebody maintains as a favor.

The asymmetry isn't an accident. Onboarding has a customer. A new hire who can't log in on day one generates a ticket, an angry manager, and visibility. Deprovisioning has no customer. Nobody calls the help desk to complain that their departed coworker's service account still authenticates. The failure is silent by design, which means it accumulates by default.

## The pattern I look for first

When I assess a leaver process, I don't start with the workflow diagram. I start with three questions:

1. **What is the authoritative signal that someone has left?** If the answer involves the word "usually," the process is already broken. HR-driven termination in the HRIS should be the only trigger; anything downstream of an email or a manager remembering is a gap.
2. **What does the signal actually reach?** The directory account almost always gets disabled. The interesting question is everything the directory doesn't govern: the SaaS app with local accounts, the shared mailbox delegation, the API key created two years ago, the OAuth grant nobody documented.
3. **Who owns the identities the person left behind?** Human offboarding is the easy half. The service accounts, automation credentials, and tokens a departing engineer created are non-human identities that outlive their creator — and in most environments, ownership dies with the employment relationship.

That third question is where the real exposure lives, and it's the one most offboarding checklists never ask.

## Why "just automate it" isn't the answer

The instinct is to treat this as a tooling problem. It's a governance problem wearing a tooling costume. Automation faithfully executes whatever ownership model exists — and if the ownership model is "nobody," automation just makes the neglect faster and more consistent.

> Before you automate a leaver workflow, you have to be able to answer, for every credential in the environment: who owns this when its creator is gone?

The sequencing that actually works, in my experience: establish ownership first (every non-human identity mapped to a role or team, never a person), instrument second (discovery tooling to find what the inventory missed), and automate third. Organizations that start at step three end up with beautifully automated processes that deprovision 60 percent of the actual attack surface.

## What I'd tell a team starting from zero

Pick the last ten people who left the organization. Manually trace everything they could still touch if they wanted to. Not what the checklist says was removed — what actually still authenticates. That exercise takes a week, costs nothing, and produces a more honest picture of your leaver process than any maturity assessment. It's also, in my experience, the fastest way to get leadership attention, because the findings are never abstract.

The organizations that handle this well aren't the ones with the best tools. They're the ones that decided departure is a security event, not an HR event, and built the accountability to match.
