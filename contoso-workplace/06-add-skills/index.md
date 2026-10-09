---
hide: false
preview: false
prev:
  text: Add a Tool
  link: /recruit-nextgen/05-add-tools
next:
  text: Automate with Workflows
  link: /recruit-nextgen/07-automate-with-workflows
short-description: Add reusable facilities issue and equipment request skills
difficulty: 1
codename: PACKAGE THE FACILITIES PROCEDURES
time: 30
harness: github-copilot
tags: [skills, instructions]
products: [copilot-studio, power-platform]
industries: [facilities]
created-date: 2026-08-05
last-edited-date: 2026-10-09
---

# Mission 06: Add facilities skills

<mission-meta />

Skills package focused procedures in reusable `SKILL.md` files. Add a workplace equipment guidance skill and a facilities issue-triage skill to the Contoso Workplace Concierge. The equipment skill develops through versions so you can test how schema and decision rules influence behavior.

Update the agent's top-level instructions:

```text
For facilities issues, follow the currently installed facilities-issue-triage skill.
For shared-equipment questions and requests, follow the currently installed workplace-resource-guidance skill.
Do not call a request workflow until the employee has reviewed the summary and explicitly confirmed.
```

Keep the global instructions and skill files aligned when replacing skills.

## Principles for useful skills

Each skill should state when it applies, which inputs are needed, which authorized knowledge or tools to use, how to handle missing or failed results, and when to stop or escalate. Keep personal data and hazardous procedures out of examples. A skill must not promise that an issue was filed unless an action confirms it.

## Lab: Add and iterate on equipment guidance

Upload each version in order through the agent's **Build** view, saving and testing after every replacement. Start with the first package:

<download-files path="recruit-nextgen/06-add-skills/assets/workplace-resource-guidance-v1-0-1" label="Download workplace resource skill v1.0.1" />

Test with a natural facilities request:

```text
What meeting-room equipment can I request?
```

Inspect the trace to confirm that the skill and `Get Facilities Equipment` tool are selected. Only present records returned by the tool.

Replace it with v1.0.2:

<download-files path="recruit-nextgen/06-add-skills/assets/workplace-resource-guidance-v1-0-2" label="Download workplace resource skill v1.0.2" />

For the sample CSV, the imported columns map as follows when SharePoint assigns its usual internal names: `field_1` Status, `field_2` Category, `field_3` Model, `field_4` Color, `field_5` Asset Tag. Verify the names in your actual list before using a filter. For example:

```text
$filter=field_2 eq 'Meeting Room' and field_1 eq 'Available'
```

If the connector action does not expose a filter input, inspect its returned rows and do not claim a server-side filter was applied.

Replace it with v1.0.3:

<download-files path="recruit-nextgen/06-add-skills/assets/workplace-resource-guidance-v1-0-3" label="Download workplace resource skill v1.0.3" />

Choose a returned option and provide an example request detail, such as `for the north meeting room on Tuesday`. Check that the assistant summarizes the option, location, and timing without exposing its SharePoint item ID.

## Lab: Add issue triage

Upload the facilities triage skill:

<download-files path="recruit-nextgen/06-add-skills/assets/facilities-issue-triage" label="Download facilities issue triage skill" />

Test in a new Preview conversation:

```text
The light is flickering in a meeting room. How should I report it?
```

The agent should ask for the location if missing, follow only the approved sample guide, avoid repair instructions, and provide a concise issue summary. Test a hazard report separately and verify that the agent points to local emergency procedures rather than continuing routine troubleshooting.

## Evaluate behavior

For each test, inspect the trace and verify the expected skill/tool, source, and input values. Also test a missing location, no matching equipment, an unavailable source, an invalid option, and a user who declines. A successful explicit skill-load prompt is only a version check; it does not demonstrate automatic skill selection.

## Mission complete

The agent now has focused procedures for workplace issues and equipment requests. Continue to [Automate with Workflows](../07-automate-with-workflows/index.md).

## References

- [Skills in Copilot Studio](https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/skills-overview)
- [Write effective skill instructions](https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/skills-create#write-effective-skill-instructions)

<analytics-tag section="recruit-nextgen" mission="06-add-skills" />
