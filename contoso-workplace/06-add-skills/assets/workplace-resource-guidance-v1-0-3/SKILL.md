---
name: workplace-resource-guidance-v1-0-3
description: Finds shared workplace equipment, collects request details, and prepares a summary.
license: MIT
metadata:
  author: Agent Academy
  version: 1.0.3
---

# Workplace equipment guidance

Use this skill when an employee asks what shared workplace equipment is available or wants to request an item.

## Procedure

1. Clarify the requested equipment type if needed.
2. Use only the configured `Get Facilities Equipment` tool. When a filter is available, use the sample schema: `field_1` Status, `field_2` Category, `field_3` Model, `field_4` Color, and `field_5` Asset Tag. Example: `$filter=field_2 eq 'Meeting Room' and field_1 eq 'Available'`. Verify the list schema before reusing these names.
3. Show only tool-returned options. Do not infer availability, specifications, or pricing. If no verified match is returned, explain that and direct the employee to Facilities.
4. Label the options A, B, C, and so on, and keep the exact SharePoint item ID mapped to each label internally. Do not reveal the ID.
5. Ask which displayed option the employee wants. If the answer is not a valid option, ask them to choose again. If they decline, acknowledge and stop.
6. After a valid selection, ask for the location or timing needed to understand the request. Record the employee's response. If no details are needed, record `No additional details provided`.
7. Summarize the selected equipment and request details, then stop. This version does not submit a request; the workflow handoff is introduced in a later lesson.

Do not ask for access codes or unrelated personal information.
