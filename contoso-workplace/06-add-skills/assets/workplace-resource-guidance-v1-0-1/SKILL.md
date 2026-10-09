---
name: workplace-resource-guidance-v1-0-1
description: Helps employees find shared workplace equipment using the configured Get Facilities Equipment tool.
license: MIT
metadata:
  author: Agent Academy
  version: 1.0.1
---

# Workplace equipment guidance

Use this skill when an employee asks what shared workplace equipment is available or wants help choosing an item.

## Procedure

1. If the requested equipment type is unclear, ask one question to clarify it.
2. Use only `Get Facilities Equipment` to retrieve catalog options. Do not invent models, prices, or availability.
3. Show a short list of matching records. Include the model and relevant details returned by the tool. If no matching record is returned, say that the test catalog has no confirmed match and direct the employee to Facilities.
4. Ask whether the employee wants to continue with one of the displayed options. Label options A, B, C, and so on, and keep an internal mapping from each label to its SharePoint item ID. Do not show the ID.
5. If the employee selects an option, ask for the location or timing only if needed to understand the request. If they decline, acknowledge and stop. If the selected label does not map to a displayed record, ask them to choose again.

Do not submit requests in this version. The facilities notification workflow is added in a later lesson.
