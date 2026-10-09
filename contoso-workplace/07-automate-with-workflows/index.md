---
hide: false
preview: false
prev:
  text: Add Skills
  link: /recruit-nextgen/06-add-skills
next:
  text: Publish Your Agent
  link: /recruit-nextgen/08-publish-your-agent
short-description: Build a workflow for confirmed workplace equipment requests
difficulty: 1
codename: AUTOMATE THE FACILITIES HANDOFF
time: 60
harness: github-copilot
tags: [automation, workflows]
products: [copilot-studio, power-automate, sharepoint, outlook]
industries: [facilities]
created-date: 2026-08-05
last-edited-date: 2026-10-09
---

# Mission 07: Automate an equipment request

<mission-meta />

The agent interprets the employee's request and gathers missing details. The workflow performs the predictable operation: retrieve a selected equipment record and send a test notification to the facilities inbox. It must run only after the employee confirms the request summary.

> [!WARNING]
> This lab sends email. Use a test list, test connection, and your own test inbox. Do not send requests to live facilities staff or use the workflow to initiate a real purchase.

## Workflow contract

| Input | Meaning |
|---|---|
| `sharepointItemId` | ID of an option selected from the tool results |
| `requestDetails` | Employee's location, timing, or other relevant details |
| `requestorName` | Verified name, if available from authenticated context |

The workflow looks up the selected item, emails the test inbox, and returns its model/name to the agent. Do not pass user-controlled site or list names to the workflow.

## Lab: Create the workflow

1. In Copilot Studio, open **Workflows**, create a workflow, and name it `Send facilities request email`.
2. Choose the trigger for when an agent calls the workflow.
3. Add the three text inputs above, with descriptions that explain the expected values.
4. Add SharePoint **Get item**. Select the course test site and `FacilitiesEquipment` list. Map `sharepointItemId` to **Id**.
5. Add the Office 365 Outlook email action. Use a test connection; set **To** to your own test inbox.
6. Use a subject such as `Facilities equipment request: [Model]`. Add the verified requestor name, model, asset tag, item link, and request details to the body using dynamic content.
7. Keep the email as plain text for the lab. If using HTML, use a static anchor element and the dynamic item URL; do not interpolate user-provided text into raw HTML.
8. Add **Respond to the agent** and return the item's `Model` field as a text output named `ModelValue`. If the designer supports an explicit success result, return it too.
9. Save, resolve validation errors, and publish. Confirm the workflow is published before adding it to the agent.

Example plain-text body (replace labels with dynamic content tokens):

```text
Test facilities request from: [requestorName]
Equipment: [Model]
Asset tag: [Asset Tag]
Item details: [Link to item]
Request details: [requestDetails]

Training message only. No work order or purchase has been created.
```

## Add it to the agent

Add `Send facilities request email` to the Contoso Workplace Concierge as a workflow tool. Check that each input matches the workflow trigger's exact name and meaning. Replace the installed equipment skill with v1.0.4:

<download-files path="recruit-nextgen/07-automate-with-workflows/assets/workplace-resource-guidance-v1-0-4" label="Download workplace resource skill v1.0.4" />

Save the agent. Verify that the skill requires explicit employee approval before it calls the workflow and that it does not claim to create a work order.

## End-to-end tests

Run every case in a separate Preview conversation. First confirm the intended skill is available without invoking actions:

```text
Load only workplace-resource-guidance-v1-0-4. Confirm its name and purpose. Do not read inventory, call tools, or send email.
```

Inspect the trace, then run these cases:

1. Select a returned equipment option, provide a location and timing, review the summary, then explicitly confirm.
2. Select another option, state that there are no extra details, review the summary, then explicitly confirm.
3. Select an option, then decline at the confirmation step.

For confirmed cases, verify the SharePoint item ID and workflow inputs in the trace, inspect the test inbox, and confirm the output includes `ModelValue`. For the declined case, verify that neither the workflow nor email action ran. Also test a missing location, an invalid option, no matching equipment, and a failed workflow. The agent must never claim completion when the workflow did not succeed.

## Mission complete

The agent now reasons about workplace requests while a workflow sends a controlled test notification. Continue to [Publish Your Agent](../08-publish-your-agent/index.md).

## References

- [Workflows overview](https://learn.microsoft.com/en-us/microsoft-copilot-studio/workflows-experience/flows-overview)
- [Add a workflow as an agent tool](https://learn.microsoft.com/en-us/microsoft-copilot-studio/workflows-experience/flow-agent)
- [Workflow expression reference](https://learn.microsoft.com/en-us/azure/logic-apps/expression-functions-reference)

<analytics-tag section="recruit-nextgen" mission="07-automate-with-workflows" />
