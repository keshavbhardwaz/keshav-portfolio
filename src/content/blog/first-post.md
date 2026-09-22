---
title: 'From the Escalation Queue to On-Call SRE'
description: 'How years of resolving enterprise production escalations shaped the habits I now bring to site reliability engineering.'
pubDate: 'Sep 22 2026'
heroImage: '../../assets/blog-placeholder-3.jpg'
---

Production support teaches you quickly that systems rarely fail in neat, isolated ways. A slow database query becomes an exhausted PHP worker pool. A cache miss turns into an origin traffic spike. A routine deployment exposes an assumption that nobody knew the platform was making.

For more than three and a half years, I have worked in that space as a DXP Support Engineer at Acquia: close to the customer, close to the platform, and often closest to the moment when something stops behaving as designed. Before that, I worked as a Backend Operations Engineer supporting high-volume telecom systems for Bharti Airtel through Diksha Technologies.

Those roles taught me how to restore service under pressure. They also made me curious about the engineering decisions that determine whether an incident happens again. That curiosity is what is taking me deeper into Site Reliability Engineering.

## Support and SRE begin with the same question

When an alert fires or a critical ticket arrives, the first question is not “Who changed something?” It is:

> What is the system telling us right now?

Good incident response starts with evidence. Logs establish sequence. Metrics reveal scope. Traces connect symptoms across services. Recent changes provide context, but they should not become conclusions before the data supports them.

In enterprise Drupal environments, the visible symptom may be a slow page or an HTTP 500. The useful questions sit underneath it:

- Is latency rising at the edge, application, or database layer?
- Are workers saturated, blocked, or recycling?
- Did cache effectiveness change?
- Is the problem global, regional, or limited to one site or code path?
- What changed immediately before the impact began?

Support engineering builds the habit of moving from symptom to signal. SRE turns that habit into a repeatable operating model.

## The escalation queue is an observability classroom

An escalation contains more than a problem to solve. It is a compressed lesson in how users experience reliability.

A dashboard may show healthy averages while one customer path is unusable. Infrastructure can remain “up” while response time makes the product functionally unavailable. A service-level objective closes that gap by defining reliability from the user's perspective.

The support queue therefore offers valuable input for SRE work:

1. Repeated tickets reveal missing telemetry.
2. Long investigations expose unclear ownership or weak runbooks.
3. Recurring fixes identify automation opportunities.
4. Customer impact helps define meaningful service-level indicators.

The goal is not simply to close tickets faster. It is to reduce the number of incidents that require a ticket at all.

## Restore first, learn second, improve always

During an active incident, the priority is to reduce impact safely. Diagnosis and mitigation are related, but they are not always the same activity.

A useful incident rhythm is:

1. **Stabilize:** stop the immediate harm with the safest reversible action.
2. **Observe:** preserve evidence and establish a shared timeline.
3. **Diagnose:** test hypotheses against logs, metrics, traces, and changes.
4. **Recover:** verify the user journey, not only the infrastructure status.
5. **Learn:** document contributing conditions without blame.
6. **Improve:** assign concrete work that makes recurrence less likely or less damaging.

This is where calm communication matters. An incident bridge needs short updates, explicit owners, timestamps, and a clear distinction between facts and hypotheses. More voices do not automatically create more clarity.

## Runbooks should remove uncertainty, not judgment

The best runbooks do not attempt to encode every possible failure. They give an engineer a reliable place to begin.

A useful runbook should answer:

- What does this alert mean for users?
- Which dashboards, logs, and traces should I open first?
- What recent changes should I inspect?
- Which mitigations are safe and reversible?
- When and to whom should I escalate?
- How will I confirm that service is actually restored?

If the same diagnostic command is copied into multiple incidents, it may belong in a script. If the same set of checks is repeated manually, it may belong in an automated workflow. Python, CI/CD tooling, and n8n are valuable here because they can turn tribal knowledge into consistent execution.

Automation should not hide the system. It should make the system easier to understand and the response easier to reproduce.

## Reliability starts before on-call

On-call is often treated as the visible part of SRE, but reliable systems are designed much earlier:

- Containers create consistent runtime boundaries.
- CI/CD pipelines make changes testable and traceable.
- Kubernetes provides declarative deployment and recovery primitives.
- AWS services add scalable infrastructure, identity controls, and observability.
- SLOs force teams to discuss acceptable risk before an incident.

The transition from support to SRE is therefore not a departure from my previous work. It is an expansion of it: from resolving one production problem to improving the platform, automation, and feedback loops around every future problem.

## What I am carrying forward

The escalation queue gave me a few principles I intend to keep:

- **Users experience systems, not team boundaries.** Ownership must follow impact.
- **Evidence beats confidence.** Strong opinions should remain testable hypotheses.
- **Recovery is incomplete without verification.** A green dashboard is not the same as a working user journey.
- **Repeated toil is design feedback.** Manual repetition points toward automation.
- **Blameless does not mean actionless.** Learning should end with accountable improvements.
- **Calm is an engineering skill.** Clear thinking and communication reduce time to recovery.

I am still building depth in Docker, Kubernetes, AWS, CI/CD, Python, and reliability practices. But I am not starting from zero. I am bringing years of production context: the ability to investigate ambiguity, communicate through pressure, and stay focused on the people depending on the system.

That is the path from the escalation queue to on-call SRE—and this article is the first step in documenting it.
