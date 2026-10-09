---
hide: false
preview: false
next:
  text: Course Setup
  link: /recruit-nextgen/00-course-setup
lastUpdated: false
---

# Recruit: Build an agent with the GitHub Copilot harness

Welcome to a practical course in Microsoft Copilot Studio. You’ll build one employee-facing facilities support agent, then extend it with approved workplace guidance, a SharePoint connector, reusable skills, and a workflow. The course ends with channel publishing and a review of usage-based billing.

The course uses the **GitHub Copilot harness** in Copilot Studio. Here, “GitHub Copilot harness” describes an agent runtime; it does not mean GitHub Copilot is required. You do not need a GitHub account or GitHub Copilot subscription for these labs.

## What you’ll build

The **Contoso Workplace Concierge** helps employees find facilities guidance, report workplace issues, and request shared office equipment. It retrieves current equipment options from a SharePoint list, follows dedicated procedures for facilities requests, and sends a test email through a workflow after the employee confirms.

Each lesson adds one capability to the same solution. This makes it easier to test what changed and to understand how the parts fit together.

## Learning outcomes

After the course, you can:

- Describe how a model, harness, instructions, knowledge, tools, skills, and workflows contribute to an agent.
- Choose a Copilot Studio harness that fits a scenario.
- Create an agent in a Power Platform solution and ground it in approved sources.
- Connect a SharePoint action and guide it with reusable skills.
- Build, publish, and test a deterministic workflow called by the agent.
- Publish to Teams and Microsoft 365 Copilot, and identify where to check licensing and usage.

## Before you begin

You’ll need access to a Microsoft 365 work or school tenant, a Power Platform environment, Copilot Studio, and SharePoint. Some steps require administrator approval or a suitable license. The GitHub Copilot harness uses Copilot Credits for applicable AI creation, testing, and runtime activity; check the current Microsoft licensing guidance before starting.

Follow [Course Setup](./00-course-setup/index.md) if you need a dedicated development environment. You’ll create a `FacilitiesEquipment` SharePoint list there. Use test data only; do not connect the labs to production records or send test requests to real facilities staff.

## Course map

| Mission | Lesson | You’ll do |
|---|---|---|
| 00 | [Course Setup](./00-course-setup/index.md) | Prepare a development environment and sample facilities equipment list. |
| 01 | [Introduction to Agents](./01-introduction-to-agents/index.md) | Learn the concepts behind reasoning, grounding, and orchestration. |
| 02 | [Copilot Studio Fundamentals](./02-copilot-studio-fundamentals/index.md) | Compare build surfaces and harnesses; map the agent capabilities. |
| 03 | [Creating a Solution](./03-creating-a-solution/index.md) | Create the package that will contain the course work. |
| 04 | [Build an Agent](./04-build-a-custom-agent/index.md) | Create and test the Contoso Workplace Concierge with approved guidance. |
| 05 | [Add a Tool](./05-add-tools/index.md) | Read the facilities equipment list through a connector action. |
| 06 | [Add Skills](./06-add-skills/index.md) | Add reusable facilities triage and equipment-request procedures. |
| 07 | [Automate with Workflows](./07-automate-with-workflows/index.md) | Send a confirmed facilities request through a workflow. |
| 08 | [Publish Your Agent](./08-publish-your-agent/index.md) | Configure Teams and Microsoft 365 Copilot, then test the live agent. |
| 09 | [Understanding Licensing](./09-understanding-licensing/index.md) | Review the usage and licensing decisions to make before rollout. |
| Final | [Course Completion](./course-completion-badges-recruit/index.md) | Review the course completion and badge process. |

The missions are designed to be completed in order. If you already have an appropriate tenant and environment, use the setup lesson’s prerequisites to skip the environment-creation steps—not the sample-data setup.

## A note about examples

Prompts and sample skill files in this course are teaching materials. Test them in a development environment and replace the sample Contoso workplace content with approved organizational guidance before adapting it for real users. Preview results can vary; verify sources, tool inputs, workflow outcomes, permissions, and cost rather than treating a sample response as proof of correctness.

<analytics-tag section="recruit-nextgen" />
