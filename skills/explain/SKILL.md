---
name: explain
description: Use when a user needs a clear explanation of code, systems, bugs, concepts, architecture, or model behavior. Choose the smallest useful presentation and build from concrete evidence.
---

# Explain

Make the explanation easy to follow, technically accurate, and useful for the user's next action.

## Core method

Use this order:

1. **Answer** — State the main point in one or two sentences.
2. **Evidence** — For code, inspect the relevant files before explaining behavior.
3. **Mechanism** — Show the important steps in the order they happen.
4. **Example** — Use a concrete input, action, or request and show the resulting behavior.
5. **Next step** — Point to the next file, command, or concept only when it helps.

Do not add detail just to make the answer longer.

## Choose the presentation

Start with the simplest format that can explain the subject well.

### Text

Use text for:

- A single concept
- One bug or error
- A short code path
- A direct "why" question

Prefer short paragraphs and lists.

### Flow diagram

Use a diagram when the user needs to understand:

- Request flow
- Component relationships
- State changes
- Data movement
- A sequence of operations

Use simple boxes and arrows.

Example:

```
[User action]
      |
      v
[UI handler]
      |
      v
[API request]
      |
      v
[Server]
```

Keep diagrams small. Split a large system into separate flows.

### Reference page

Use a structured reference when the subject has many connected parts, such as:

- A complete feature
- A framework subsystem
- A large architecture
- A specification

Organize it into clear sections. Include real examples instead of definitions alone.

### Video

Only create or recommend a video format when the user asks for one.

## Code explanation rules

When explaining code:

- Read the relevant source first.
- Use exact file paths and line numbers when available.
- Explain the actual execution path, not a guessed implementation.
- Separate what the code does from what the code could do.
- Show a small real example before introducing abstractions.
- Mention assumptions when the repository does not provide enough evidence.

For a bug, use this shape:

```
Cause → Where it happens → Why it happens → Fix → How to verify
```

Do not claim a root cause until the available code or error evidence supports it.

## Technical writing style

Write in plain technical English.

Prefer:

- "use" instead of "utilize"
- "start" instead of "commence"
- "before" instead of "prior to"
- "about" instead of "approximately"
- "show" instead of "demonstrate" when the meaning is the same

Keep one main idea per sentence.

Use the same term for the same concept. Do not switch between synonyms only for style.

Prefer active voice:

- "The client sends the token."
- Not: "The token is sent by the client."

For instructions, put the action first:

- "Open the file."
- "Run the test."
- "Check the network request."

For warnings:

```
WARNING: Do not run this command in production.
It can delete existing data.
```

## Simple explanation mode

Use this mode when the user asks for an explanation "like I'm 13", "ELI13", "in simple words", or says they do not understand.

Use one familiar analogy and keep it consistent.

Build the explanation in this order:

1. What it is
2. Why it exists
3. How it works
4. A small example
5. One-line recap

Avoid unnecessary jargon. If a technical term is required, define it the first time.

Simple does not mean childish.

## Diagrams

For diagrams:

- Keep labels short.
- Use one direction: left-to-right or top-to-bottom.
- Avoid crossing arrows.
- Use one arrow for one relationship.
- Use at most a few visual groups.
- Split complex systems into multiple diagrams.

Prefer plain ASCII when the user is in a terminal or text-only context.

For richer output, use an appropriate diagram or artifact capability when available.

## Common answer patterns

### Concept

```
Short answer: <main idea>

Why it exists:
- <reason>

How it works:
1. <step>
2. <step>
3. <step>

Example:
<small concrete example>

Recap:
<one sentence>
```

### Code flow

```
Short answer: <what the code does>

Flow:
A → B → C → D

Key code:
- <file>:<line> — <role>
- <file>:<line> — <role>

Example:
<input> → <operation> → <output>
```

### Bug

```
Root cause: <supported cause>

What happens:
1. <step>
2. <step>
3. <failure>

Fix:
<change>

Verify:
<test or command>
```

## Quality check

Before finishing, verify:

- Did I answer the user's actual question first?
- Did I use repository evidence for code questions?
- Is every technical claim supported by the available evidence?
- Could I remove a paragraph without losing understanding?
- Did I give a concrete example?
- Did I avoid unnecessary jargon?
- Is the next step useful rather than automatic?

The goal is not to explain everything. The goal is to make the user understand the part that matters.
