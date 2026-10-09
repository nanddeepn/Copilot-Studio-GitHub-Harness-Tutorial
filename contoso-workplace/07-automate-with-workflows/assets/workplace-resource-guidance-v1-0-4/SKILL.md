---
name: workplace-resource-guidance-v1-0-4
description: Finds shared workplace equipment, confirms a request, and calls the configured workflow only after employee approval.
license: MIT
metadata:
  author: Agent Academy
  version: 1.0.4
---

# Workplace equipment request guidance

Use this skill when an employee asks to find, choose, or request shared workplace equipment.

## Procedure

1. Clarify the equipment category if needed. Use only the configured `Get Facilities Equipment` tool at the pinned test site and list.
2. If a filter input is available, use verified SharePoint internal field names. The sample list maps `field_1` to Status, `field_2` to Category, `field_3` to Model, `field_4` to Color, and `field_5` to Asset Tag. Verify this mapping against the actual list before use.
3. Present only options supported by tool results. Label them A, B, C, and so on; retain the exact SharePoint item ID mapped to each label, but do not show IDs. Do not claim availability unless returned data supports it.
4. If there is no confirmed match or the lookup fails, state that clearly and direct the employee to Facilities. Do not call the request workflow.
5. Ask the employee to select one displayed option. If the selection is invalid, ask them to choose again. If they decline, acknowledge and stop.
6. Ask for the location or timing needed to understand the request. If no additional details are needed, use `No additional details provided`.
7. Summarize the selected equipment and request details. Ask whether the employee approves sending the request to the facilities team. Do not proceed unless the employee explicitly confirms this summary.
8. After confirmation, obtain the requestor name only from authenticated user context if that value is available to the agent. Do not ask for credentials. If no verified name is available, pass an empty value only if the workflow supports it; otherwise explain that the notification cannot be sent and direct the employee to Facilities.
9. Call `Send facilities request email` with:
   - `sharepointItemId`: the item ID mapped to the selected option.
   - `requestDetails`: the employee's location/timing details or the no-details text above.
   - `requestorName`: the verified authenticated display name.
10. Wait for the workflow call to finish. Report success only if it completes without an error and returns `ModelValue`. If it fails or returns no model value, explain that the notification could not be confirmed and direct the employee to Facilities; do not claim an email was sent.
11. On confirmed success, say the equipment request was sent to the facilities team for review. Do not claim that a work order was created or the request was approved.

Do not use this workflow for unconfirmed requests, invalid selections, unavailable equipment, or unrelated tasks.
