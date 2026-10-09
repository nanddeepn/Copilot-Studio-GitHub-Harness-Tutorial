---
hide: false
preview: false
prev:
  text: Recruit overview
  link: /recruit-nextgen
next:
  text: Introduction to Agents
  link: /recruit-nextgen/01-introduction-to-agents
short-description: Prepare a development environment and sample inventory for the course
difficulty: 1
codename: PREPARE THE WORKBENCH
time: 30
harness: github-copilot
tags: [setup]
products: [copilot-studio, sharepoint, microsoft-365]
industries: [facilities]
created-date: 2026-08-05
last-edited-date: 2026-10-09
---

# Mission 00: Prepare your course environment

<mission-meta />

## Purpose

Before building the Contoso Workplace Concierge, prepare a development environment and a sample SharePoint facilities equipment list. Use a dedicated test tenant or an environment approved by your administrator. Do not use production data: later lessons send a test email and publish an agent.

## What you need

- A Microsoft 365 work or school account with SharePoint.
- Access to Microsoft Copilot Studio and a Power Platform environment.
- Permission to create a SharePoint site and list, and to create solutions and agents.
- A modern browser.

Trials, developer plans, self-service sign-up, and publishing permissions depend on tenant eligibility and administrator policy. Check current availability with Microsoft and your administrator rather than assuming a trial can be started in every tenant. A Microsoft 365 Copilot license is not a substitute for Copilot Credits used by the GitHub Copilot harness.

## Choose your environment

If your organization has provided a non-production environment with Copilot Studio access, use it and confirm that you have permission to create solutions. Otherwise, check Microsoft's current [Power Apps Developer Plan](https://aka.ms/PowerAppsDevPlan) and [Copilot Studio trial](https://aka.ms/TryCopilotStudio) availability. Sign in with the same work or school account throughout the course.

If the sign-up pages reject your account, self-service sign-up may be disabled or your tenant may not qualify. Ask your administrator for an approved development environment. Do not work around a tenant restriction by using a personal account.

For publishing exercises, an administrator may need to grant the appropriate author role or security group access. Request the least privilege required; do not broaden a tenant-wide setting just to complete a lab.

## Create a SharePoint site and equipment list

Create a test SharePoint team site named `Contoso Workplace` (or a clearly identified course equivalent). Use the site address you actually receive; it may not match the example below.

Download the course's facilities equipment CSV using the download control:

<download-files path="recruit-nextgen/00-course-setup/assets/facilities-equipment" label="Download the FacilitiesEquipment sample data" />

In SharePoint, create the facilities equipment list from the CSV:

1. Open the test site and choose **New** → **List** → **From CSV** (or create a list from the uploaded file using the equivalent option in your SharePoint UI).
2. Upload `FacilitiesEquipment.csv` and inspect the detected columns and sample rows.
3. Name the list `FacilitiesEquipment`. Set `Status` and `Category` to **Choice**, and `Date Added` to **Date and time**. Set `Replacement Cost` to **Number**. Keep `Title`, `Model`, `Color`, and `Asset Tag` as text.
4. Confirm the list contains the sample records and that the status values distinguish available equipment from reserved items.

Download and inspect the sample guidance file:

<download-files path="recruit-nextgen/00-course-setup/assets/facilities-guide" label="Download the workplace facilities guide" />

Upload its text content to the Contoso Workplace SharePoint site or add it as an approved knowledge source in the agent. It contains fictional training guidance only; replace it with current, authorized procedures before real use.

The tool lab reads the equipment list; the workflow retrieves a selected item. Column display names and SharePoint internal field names can differ. The skill example documents the sample schema; verify your list's internal names if you change the CSV or rebuild the list.

## Checkpoint

Before continuing, record the environment name and SharePoint site URL somewhere private to your course work. Confirm you can open the site, see the `FacilitiesEquipment` list, and read its sample rows. You will select the actual site and list in Copilot Studio instead of copying placeholder addresses into a connector.

### Troubleshooting setup

- **No access to Copilot Studio or environment creation?** Ask your administrator to provision an approved environment and assign the role required for the lab.
- **SharePoint list import fails?** Confirm the workbook is uploaded, the table is selected, and the column types are reviewed before creating the list.
- **Cannot publish later?** Publishing and channel availability can be tenant-controlled. Ask an administrator; do not change organization policy yourself.

## Mission complete

You have an isolated place to build, fictional workplace guidance, and a sample facilities list for the later labs. Continue to [Introduction to Agents](../01-introduction-to-agents/index.md).

## References

- [Power Apps Developer Plan](https://aka.ms/PowerAppsDevPlan)
- [Try Copilot Studio](https://aka.ms/TryCopilotStudio)
- [SharePoint lists](https://support.microsoft.com/sharepoint)

<analytics-tag section="recruit-nextgen" mission="00-course-setup" />
