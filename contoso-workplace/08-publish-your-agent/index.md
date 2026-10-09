---
hide: false
preview: false
prev:
  text: Automate with Workflows
  link: /recruit-nextgen/07-automate-with-workflows
next:
  text: Understanding Licensing
  link: /recruit-nextgen/09-understanding-licensing
short-description: Configure, publish, and verify the workplace agent
difficulty: 1
codename: RELEASE TO A TEST CHANNEL
time: 20
harness: github-copilot
tags: [publishing]
products: [copilot-studio, microsoft-365, teams]
industries: [facilities]
created-date: 2026-08-05
last-edited-date: 2026-10-09
---

# Mission 08: Publish and verify the workplace agent

<mission-meta />

Publishing makes an agent version available through configured channels. It does not automatically grant access to every employee: sharing, admin approval, and tenant policy also apply. Keep the course agent limited to a test audience until it has passed an organizational review.

## Before release

Confirm the knowledge is approved for the audience, the SharePoint connector is pinned to test data, the email workflow targets only your test inbox, and the skills handle cancellation and failures. Preview tests should verify sources, tool inputs, workflow results, and the absence of unintended actions.

## Configure and publish a channel

1. Open the `Contoso Workplace Concierge` agent and publish the saved version.
2. Add the Teams and Microsoft 365 channel if your environment makes it available.
3. Update the listing with accurate course details. For example:

   **Short description**
   ```text
   Find workplace guidance and explore shared office equipment.
   ```

   **Long description**
   ```text
   Contoso Workplace Concierge helps employees find fictional workplace guidance, report non-emergency facilities issues, and review shared-equipment options from a test catalog. In the course environment, it can send a confirmed equipment request to a test inbox. It does not create a work order, perform repairs, or approve requests.
   ```

4. Use the correct developer name for your test tenant and save.
5. Publish the updated agent if required by the channel workflow.

If the channel is unavailable, ask your administrator to verify tenant and channel prerequisites. Adding a channel does not necessarily make the agent visible to the organization.

## Verify the published experience

Open the agent through the channel's test experience using an account authorized for the test SharePoint site. Try:

```text
How should I report a flickering light in the east meeting room?
```

Check that the answer is grounded in the approved sample guide and does not invent a repair or response-time promise. Then test an equipment request using Mission 07's test cases. Confirm that any notification still goes only to your test inbox.

Check authentication, citations, tools, and policy messages in the actual channel. A successful Preview conversation does not prove that user permissions or connector behavior are correct after publishing.

## Release checklist

Before a real rollout, replace fictional guidance and sample data, use an approved facilities inbox and request process, verify data access, establish an owner and support path, and agree on monitoring and rollback. Re-publish and re-test after changes.

## Mission complete

You have verified the workplace agent in a published channel where your tenant allows it. Continue to [Understanding Licensing](../09-understanding-licensing/index.md).

## References

- [Publish an agent](https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/publication-publish-agent)
- [Available channels](https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/publication-channels-overview)
- [Publishing fundamentals](https://learn.microsoft.com/en-us/microsoft-copilot-studio/agents-experience/publication-fundamentals-publish-channels)

<analytics-tag section="recruit-nextgen" mission="08-publish-your-agent" />
