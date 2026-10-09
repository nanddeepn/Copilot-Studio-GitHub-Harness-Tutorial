---
hide: false
preview: false
prev:
  text: Publish Your Agent
  link: /recruit-nextgen/08-publish-your-agent
next:
  text: Course Completion
  link: /recruit-nextgen/course-completion-badges-recruit
short-description: Identify the current licensing and consumption questions for your harness
difficulty: 1
codename: PLAN FOR USAGE
time: 20
harness: github-copilot
tags: [licensing]
products: [copilot-studio, microsoft-365]
industries: [facilities]
created-date: 2026-08-05
last-edited-date: 2026-10-09
---

# Mission 09: Plan for usage and licensing

<mission-meta />

Licensing and metering change over time and vary by tenant, harness, user, and scenario. This lesson gives you a checklist for a planning conversation; it is not a price quote or a substitute for current Microsoft terms.

## Start with the exact scenario

Record the harness, channels, authentication model, user population, connected services, and expected task volume. Do not assume that two agents built in Copilot Studio have the same billing treatment.

| Question | What to verify |
|---|---|
| Which harness runs the agent? | Current harness-specific licensing and metering documentation |
| Which activities are billed? | Creation, test/Preview, evaluation, and production runtime rules |
| Which users can access it? | Applicable user licenses, tenant configuration, and channel policy |
| How is consumption funded? | Current purchase option, capacity, and overage settings |
| Where is usage reviewed? | Current admin reporting and environment-level capacity controls |

The GitHub Copilot harness uses Copilot Credits for covered AI activity. A Microsoft 365 Copilot user license should not be assumed to cover every harness or usage scenario. Verify whether any published exception applies to the precise workload.

## What affects consumption?

Usage can depend on the model, runtime work, amount of context, number and kind of tool actions, and the complexity of each task. Creation and testing may also be metered. Use representative requests and current product documentation to estimate; a single short Preview conversation is not a reliable production forecast.

The simplest cost-control measures are also good engineering practice:

- Keep the agent's purpose and available capabilities focused.
- Avoid unnecessary retrieval and overlapping tools.
- Test typical, edge, and failure cases.
- Monitor real usage after a limited release and compare it with expectations.
- Agree on capacity thresholds, ownership, and escalation for unexpected spend.

## Before production

Ask your tenant administrator or Microsoft account team to verify current rates and licensing terms, credit purchase and allocation options, overage behavior, workload exceptions, and reporting locations. Record the date and source of the information used in any business estimate.

Do not copy a rate table or a dated product guide into a long-lived architecture decision. Link to the current official source instead.

## Mission complete

You can now identify the licensing questions to resolve before expanding the course agent beyond a test audience. Continue to [Course Completion](../course-completion-badges-recruit/index.md).

## Official references

- [Choose a harness](https://learn.microsoft.com/en-us/microsoft-copilot-studio/harnesses-overview)
- [Usage-based billing for the GitHub Copilot harness](https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/billing-credit-overview)
- [Purchase and manage Copilot Credits](https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/billing-manage-buy-credits)
- [Copilot Studio licensing](https://learn.microsoft.com/en-us/microsoft-copilot-studio/billing-licensing)
- [Manage Copilot Studio capacity](https://learn.microsoft.com/en-us/power-platform/admin/manage-copilot-studio-messages-capacity)

<analytics-tag section="recruit-nextgen" mission="09-understanding-licensing" />
