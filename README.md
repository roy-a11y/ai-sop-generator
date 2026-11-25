# AI SOP Generator

A reusable prompt and SOP template that turns a messy, rambling process description into a clean, standardized SOP, and flags what is missing instead of guessing.

## Problem

In operations teams, process knowledge usually lives in people's heads and chat messages. New joiners learn slowly, steps get skipped, and the same mistakes repeat. Writing a proper SOP by hand takes time, so it often doesn't get done.

## Solution

A fixed 8-section SOP format and a prompt that converts raw process notes into that format in about a minute. The prompt follows one important rule: **never invent facts**. Anything vague, uncertain or missing in the input is marked "Not specified" and listed under **Open Questions** for a human to confirm.

## How it works

1. Open `prompt-template.md` and copy the prompt.
2. Replace the placeholder with the messy process description.
3. Run it in Claude, ChatGPT or Gemini.
4. Read the **Open Questions** section and confirm each one with the process owner.
5. Update the SOP and save it as final.

## Repository structure

```
ai-sop-generator/
├── README.md
├── prompt-template.md      # the reusable prompt (v2)
├── sop-format.md           # the 8-section SOP format
└── examples/
    ├── 01-booking-failure/        # before.md (messy) -> after.md (SOP)
    ├── 02-agent-refund-request/
    └── 03-new-agent-onboarding/
```

## SOP format

Purpose, Scope, Roles and Responsibilities, Step-by-Step Procedure, Exceptions and Escalations, Checklist, Metrics, Open Questions. See `sop-format.md`.

## Examples

The three processes below are **fictional sample processes** written in the style of a B2B travel company. Each folder holds the messy input (`before.md`) and the generated SOP (`after.md`). The SOPs were generated with Claude using the prompt in this repo.

| Process | What the messy input contained | Open questions flagged |
|---|---|---|
| Failed booking handling | Late supplier confirmations, vague wait time, an unclear PNR case, an unfilled tracking sheet | 7 |
| Agent refund request | Unclear fee, unsure payment-before-airline policy, vague timelines | 8 |
| New agent onboarding | Uncertain documents, no owner for the demo call, unclear follow-up rules | 7 |

## Results (my testing)

> Fill this table with your own measurements before publishing. Time yourself writing one SOP by hand, then time the tool-assisted version including your review of the Open Questions.

| Process | Time to write manually | Time with tool (incl. review) |
|---|---|---|
| Failed booking handling | _ min | _ min |

## Prompt iteration

> Document what you actually changed. After running the prompt on all three inputs, note one thing the first version got wrong and how you fixed it.

- **v1:** a simple instruction to "turn this into an SOP". Issue observed: _(write what you saw, for example invented details or missing sections)_.
- **v2 (current):** added the no-invention rule, the "Not specified" convention, uncertainty-word handling and a numbered Open Questions list. Result: _(write what improved)_.

## Limitations

- Human review is still required. The SOP is only as good as the description given, and the AI can still misread unclear input.
- The example processes are fictional and not taken from any real company.
- Different AI tools produce slightly different wording, so check the output each time.

## Tools

Claude, ChatGPT, Gemini, Perplexity, prompt engineering, Markdown, Git and GitHub.

# Prompt iteration

v1: a simple instruction to "turn this into an SOP". Issue observed: (write what you saw).
v2: added the no-invention rule, the "Not specified" convention, uncertainty-word handling and a numbered Open Questions list. Result on the booking-failure input: correct structure and no invented details, but "Not specified" was repeated on almost every step, the roles table gained roles the input never mentioned, and there were 17 overlapping open questions.
v3 (current): added rules 9-13 to drop repeated "Not specified" lines, stop added roles, group and cap Open Questions at 10, and remove empty metrics. Result: (re-run the booking-failure input and write the new number of open questions and what improved).

# Limitations

- Human review is still required. The SOP is only as good as the description given, and the AI can still misread unclear input.
- The example processes are fictional and not taken from any real company.
-Different AI tools produce slightly different wording, so check the output each time.

# Tools
Claude, ChatGPT, Gemini, Perplexity, prompt engineering, Markdown, Git and GitHub.