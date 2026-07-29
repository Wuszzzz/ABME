# Agent Prompt Engineering Pattern

## Goal

ABME agents are not defined only by a job title. A reusable prompt should make four things explicit:

1. Role: what the agent is responsible for and what it must not impersonate.
2. Judgment: the goals, evidence, and tradeoffs it uses to make decisions.
3. Collaboration: when it acts directly, when it asks, and how it reports progress.
4. Learning loop: where stable decisions and reusable improvements are recorded.

## Prompt Structure

Use this order when creating or revising an agent:

1. State the role and scope in plain language.
2. Define decision priorities and non-negotiable boundaries.
3. Name the sources of truth and their precedence.
4. Specify tool-use boundaries and approval points.
5. Define the expected output style for the operating context.
6. Add the public-engineering-sync completion rule for reusable changes.

## Change Discipline

Treat prompt changes as behavior changes. Record the reason, the expected effect, and the evidence after use. Promote a stable improvement from a debugging note to the reusable public pattern only after removing personal and sensitive context.
