---
name: ctspe-jira-ticket
description: >-
  Draft CTSPEK Jira tickets using the team ticket-writing template (summary,
  user story, context, acceptance criteria, engineering notes, Intake status,
  Component, labels). Use when the user asks to create a Jira ticket, create a
  Jira story, open a new Jira, or draft CTSPEK ticket text.
---

# Create Jira Ticket (CTSPEK)

Use this format when creating a CTSPEK ticket, including when an AI drafts the text. Ranking, the t-shirt estimate, and reviewers (when they are not already obvious) are set in refinement.

Source: https://homestead.app.cfahome.com/docs/default/component/ctspe-docs/about/ticket_writing/

## Workflow

1. Gather enough to fill **Summary**, **user story**, and **Acceptance criteria**. Ask only for missing pieces.
2. Draft the ticket using the template below.
3. Set Jira fields per the rules below.
4. Present the draft for confirmation before creating or pasting into Jira.
5. If a Jira integration (MCP, CLI, or API) is available and the user wants the ticket created, create it after they approve the draft. Otherwise hand them copy-paste ready text.

## Concise and non-repetitive

Say each fact once. The summary names the work, and the description starts with the user story. Add context only when the story needs more color. Acceptance criteria list checkable outcomes. Engineering notes hold links and constraints. Prefer a short sentence over a paragraph that restates the same outcome.

## Summary

One short line in the Jira Summary field that describes the work to be done. The user story and later sections carry who it is for, why it matters, and the checkable outcomes.

## User story

Write the story in sentence form. It answers three things, in this order:

- As a [type of user] — who it is for?
- I want to [perform an action / need a feature] — what they want to do?
- So that [achieve a goal / get a benefit] — why they want it?

The notes after the dashes are for the author. Leave them out of the ticket.

## Context

Optional. A few sentences only when the story needs more color.

## Acceptance criteria

A bulleted list of checkable outcomes. Each bullet is one outcome.

## Engineering notes

Optional. Links and notes that help the person doing the work.

## Description template

```markdown
As a <type of user>, I want to <action>, so that <benefit>.

**Context**

<omit this section when the story is enough>

**Acceptance criteria**

- <checkable outcome>

**Engineering notes**

- <link or constraint>
```

Omit the **Context** and **Engineering notes** headings entirely when unused.

## Jira fields

### Status

New tickets start in **Intake**. Use **Ready to Refine** only when the work is high priority and the description is already detailed: user story, acceptance criteria, and context only where it adds something.

### Component

Set Component to the pillar the work belongs to: **Architecture**, **Platform**, or **Quality**. Choose from the ticket's subject using team structure boundaries.

### Reviewed by

Set Reviewed by to two teammates. Leave it for refinement unless the two reviewers are already obvious.

### Labels and parent

- T-shirt size is applied in refinement. Do not invent a size.
- If the ticket is spun off a support request, add the `support` label and set the parent to the current quarter's support epic, titled like `Support & Maintenance (Q3 2026)`.
- When the work is obvious and an AI can likely carry it out, add the label `ai-ready`. The label means the ticket is specific enough for an AI to do the work. A ticket can carry `ai-ready` and stay in Intake.

## Output format

Present the draft like this:

```markdown
### Summary
<one short line>

### Description
As a <type of user>, I want to <action>, so that <benefit>.

**Acceptance criteria**

- <outcome>

### Fields
- Status: Intake
- Component: <Architecture | Platform | Quality>
- Reviewed by: <two teammates | leave for refinement>
- Labels: <none | support | ai-ready | …>
- Parent: <none | Support & Maintenance (Q…)>
```

## Checklist before delivering

- [ ] Summary is one short line; does not duplicate the full story
- [ ] Description starts with the user story sentence
- [ ] No author coaching notes (“who it is for?”) in the ticket
- [ ] Context omitted unless it adds color the story lacks
- [ ] Each acceptance criterion is one checkable outcome
- [ ] Engineering notes are links/constraints only, or omitted
- [ ] Status is Intake (or Ready to Refine only if high priority and fully detailed)
- [ ] Component is Architecture, Platform, or Quality
- [ ] `support` / parent epic only when spun from a support request
- [ ] `ai-ready` only when the work is specific enough for an AI
