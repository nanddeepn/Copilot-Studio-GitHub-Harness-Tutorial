---
hide: false
preview: false
prev:
  text: Build an Agent
  link: /recruit-nextgen/04-build-a-custom-agent
next:
  text: Add Skills
  link: /recruit-nextgen/06-add-skills
short-description: Let the agent read the sample facilities equipment list
difficulty: 1
codename: CONNECT THE EQUIPMENT LIST
time: 30
harness: github-copilot
tags: [tools, grounding]
products: [copilot-studio, power-platform, sharepoint]
industries: [facilities]
created-date: 2026-08-05
last-edited-date: 2026-10-09
---

# Mission 05: Connect the facilities list

<mission-meta />

The facilities guide provides procedures; the SharePoint list provides current sample equipment records. Add a read-only SharePoint **Get items** action so the Contoso Workplace Concierge can retrieve shared-equipment options.

## Before you begin

- The `Contoso Workplace Concierge` agent from Mission 04.
- The test `FacilitiesEquipment` list from Mission 00.
- An authorized SharePoint connection to the test site.

## Lab: Add and configure the action

1. Open the agent's **Build** view and add a tool from **Connectors**.
2. Find the SharePoint **Get items** action and add it.
3. Rename it:

   ```text
   Get Facilities Equipment
   ```

4. Pin **Site Address** to the test site and **List Name** to `FacilitiesEquipment`. Do not let the agent select arbitrary sites or lists.
5. Save the tool and inspect its available inputs and outputs. Connector schemas can vary; follow the current UI.

If editable, use a description such as:

```text
Read equipment records from the configured FacilitiesEquipment test list. Use this tool to find shared workplace equipment options for employees. This is a read-only catalog lookup; do not create, update, or delete records.
```

Keep inputs constrained. Do not add write operations in this lesson.

## Test the connection

Save and test in Preview:

```text
Show me the shared meeting-room equipment marked available in the test catalog.
```

Inspect the trace. Confirm the action uses the configured test site and list and returns the expected rows. If results are missing or the connector fails, verify its connection identity and list permissions. Do not substitute an answer from the knowledge source for a live inventory result.

The sample list uses `Status` and `Category` to distinguish available items and equipment types. In the imported list, field names may be internal names; the skills lesson explains the sample mapping.

## Mission complete

The agent can read the facilities test catalog through a scoped SharePoint action. Continue to [Add Skills](../06-add-skills/index.md).

## References

- [Add tools to agents](https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/tools-overview)
- [SharePoint connector: Get items](https://learn.microsoft.com/connectors/sharepointonline/#get-items)

<analytics-tag section="recruit-nextgen" mission="05-add-tools" />
