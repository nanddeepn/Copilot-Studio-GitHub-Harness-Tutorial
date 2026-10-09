---
hide: false
preview: false
prev:
  text: Copilot Studio Fundamentals
  link: /recruit-nextgen/02-copilot-studio-fundamentals
next:
  text: Build an Agent
  link: /recruit-nextgen/04-build-a-custom-agent
short-description: Create a solution to organize and move the course components
difficulty: 1
codename: PACKAGE THE PROJECT
time: 30
harness: github-copilot
tags: [solutions, alm]
products: [copilot-studio, power-platform]
industries: [facilities]
created-date: 2026-08-05
last-edited-date: 2026-10-09
---

# Mission 03: Put the agent in a solution

<mission-meta />

## Why use a solution?

A Power Platform solution groups related components so they can be managed as one application. For this course, the solution will contain the `Contoso Workplace Concierge` agent and related components. Creating it first keeps the work out of the default solution and prepares it for controlled movement between environments.

An **unmanaged** solution is typically the editable development version. A **managed** solution is commonly used to distribute a tested package to downstream environments. Export/import is only one part of application lifecycle management: dependencies, connections, environment-specific values, permissions, and test plans also need attention.

A publisher identifies the owner of custom components and supplies a prefix. Choose a prefix that is unique and consistent with your organization; avoid reusing the example prefix in a real project.

## Lab: Create a publisher and solution

### Prerequisites

- Copilot Studio access in a development environment.
- A role that permits solution creation, such as Environment Maker, or an equivalent role granted by your administrator.
- The GitHub Copilot harness authoring experience available in your tenant.

### 1. Select the development environment

Open Copilot Studio and switch to the non-production environment prepared in [Mission 00](../00-course-setup/index.md). Confirm the environment name before creating anything.

### 2. Create a publisher

Open **Solutions** from the navigation and start a new solution. In the publisher dialog, create a publisher for the course project. Example values:

| Field | Example |
|---|---|
| Display name | Contoso Workplace Learning |
| Name | ContosoWorkplaceLearning |
| Description | Course practice components |
| Prefix | `ctwork` |

Use a prefix accepted by the UI and your organization's naming policy. Keep the automatically generated choice value prefix unless your administrator has specified a standard. Save the publisher.

### 3. Create the solution

Create a solution with these example values:

```text
Display name: Contoso Workplace Concierge
Name: ContosoWorkplaceConcierge
Version: 1.0.0.0
Publisher: Contoso Workplace Learning
```

Set it as your preferred solution if the option is available, then create it. Verify that the solution opens and is selected as preferred. It will initially be empty; the agent is created in the next mission.

## Before moving changes between environments

For a real release, keep development and production separate. Export and validate a deployment package in a test environment before production. Review component dependencies, connection references, environment variables, user permissions, and data policies. A managed package does not by itself guarantee that connections or data are correctly configured.

## Mission complete

The course solution is ready for the agent. Continue to [Build an Agent](../04-build-a-custom-agent/index.md).

## References

- [Create a solution](https://learn.microsoft.com/power-apps/maker/data-platform/create-solution)
- [Manage solutions in Copilot Studio](https://learn.microsoft.com/microsoft-copilot-studio/authoring-solutions-overview)
- [Power Platform pipelines](https://learn.microsoft.com/power-platform/alm/pipelines)
- [Solution versioning](https://learn.microsoft.com/power-apps/maker/data-platform/update-solutions)

<analytics-tag section="recruit-nextgen" mission="03-creating-a-solution" />
