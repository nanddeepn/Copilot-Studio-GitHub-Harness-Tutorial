---
name: workplace-resource-guidance-v1-0-2
description: Finds shared workplace equipment using the configured Get Facilities Equipment SharePoint action.
license: MIT
metadata:
  author: Agent Academy
  version: 1.0.2
---

# Workplace equipment guidance

Use this skill when an employee asks what shared workplace equipment is available or wants help choosing an item.

## Procedure

1. If the requested equipment type is unclear, ask one focused question.
2. Query only the configured `Get Facilities Equipment` tool. The tool is pinned to the course test site and list; do not choose another site or list.
3. When a filter input is available, use SharePoint internal field names. In the sample list: `field_1` is Status, `field_2` Category, `field_3` Model, `field_4` Color, and `field_5` Asset Tag. Example:

   ```text
   $filter=field_2 eq 'Meeting Room' and field_1 eq 'Available'
   ```

   Verify the schema before applying this query to another list. If the action cannot apply a filter, inspect its returned items and do not claim a server-side filter was used.
4. Present only matching records returned by the tool. Include the model, category, and useful returned details. Do not infer availability from a record that lacks an availability value.
5. Assign displayed options A, B, C, and so on. Keep each label mapped to its exact SharePoint item ID internally; never show the ID to the employee.
6. Ask whether the employee wants to continue. If they decline, stop. If the selected label is invalid, ask them to choose a displayed option. Do not submit a request in this version.

If there is no verified match or the query fails, explain the limitation and direct the employee to Facilities. Do not invent a result or silently substitute another source.
