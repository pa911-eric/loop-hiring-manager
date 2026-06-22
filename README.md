# Loop Hiring Manager

A framework for finding the few recurring AI-agent loops a software project
actually needs—without filling the repository with generic automation.

The Loop Hiring Manager treats new loops like enterprise hires:

1. establish an evidence-backed organizational need;
2. check whether existing “staff” already owns the outcome;
3. write a specific requisition;
4. evaluate candidates against the real work;
5. run one bounded work-sample trial;
6. let a human hire, hold, revise, or reject;
7. review performance and retire loops that stop earning their upkeep.

An empty hiring pipeline is a successful result.

## Why this exists

Repositories accumulate agent prompts, scheduled jobs, and maintenance routines
quickly. Many sound useful in isolation but overlap, create noisy work, or lack a
meaningful finish line.

This framework makes loop adoption a portfolio decision. A candidate must be:

- grounded in current project evidence;
- aimed at an important recurring outcome;
- distinct from published, installed, and project-local loops;
- driven by fresh inputs;
- capable of one bounded, reversible action per iteration;
- checked by a stable external test or rubric;
- limited by explicit authority and budget;
- cheap enough to justify its execution and review cost;
- removable when the need disappears.

## Recommended architecture

Run the parent as a **manual system-level review**, while keeping its evidence and
decisions project-local.

The system-level parent can inspect the loops already available to the agent and
fetch the current [Forward Future Loop Library](https://signals.forwardfuture.ai/loop-library/catalog.json).
Project-local files preserve each repository's actual risks, tests, tools,
permissions, and history.

Do not schedule the parent initially. Run it manually on real projects until it
has demonstrated that it produces sparse, valuable recommendations and clean
no-hire results.

## Start here

Copy these files into a project-specific working location:

| File | Purpose |
|---|---|
| [`PARENT_LOOP.md`](PARENT_LOOP.md) | Ready-to-run parent loop |
| [`registry.md`](registry.md) | Adopted-loop roster and coverage boundaries |
| [`pipeline.md`](pipeline.md) | Requisitions, candidate cards, and interview scores |
| [`reviews.md`](reviews.md) | Trial, probation, and retirement evidence |

Then ask your agent:

```text
Run the Loop Hiring Manager in PARENT_LOOP.md as a manual, read-only staffing
review for this project. Use registry.md, pipeline.md, and reviews.md for state.
Fetch the current Loop Library and inventory the loops already available to you.
Do not execute, install, or schedule any candidate. Return no more than three
evidence-backed recommendations, and treat no-hire as a valid result.
```

## Capacity policy

- At most **three** active candidates
- At most **one** trial or probationary loop
- Existing loop before adaptation
- Adaptation before invention
- Human approval before execution, installation, or scheduling
- A review date and retirement condition for every adopted loop

## Candidate lifecycle

```text
OBSERVED
  → REQUISITION
  → SOURCING
  → INTERVIEWED
  → TRIAL
  → HIRED
  → PROBATION
  → ACTIVE
  → REVISED | SUSPENDED | RETIRED

Any pre-hire candidate may instead become:
  → REJECTED
  → SOLVE_ONCE
  → USE_EXISTING_LOOP
  → USE_DETERMINISTIC_AUTOMATION
```

Moving a candidate between states does not expand the agent's authority.
Production, destructive, financial, privacy-sensitive, external-message, and
other consequential actions remain separately approval-gated.

## What should open a requisition?

Strong evidence includes:

- a consequential task or failure recurring at least twice;
- a critical outcome depending on undocumented human memory;
- repeated escapes from current tests or operational checks;
- measurable drift, cost, errors, risk, or queue growth;
- an explicit requirement with no repeatable proof;
- one severe exposure that justifies recurring verification.

Weak evidence includes:

- an untouched directory;
- an absent catalog category;
- a fashionable technology or practice;
- a loop used by another repository;
- cleanup the agent can merely imagine;
- a one-time task;
- a need with no stable input or acceptance check.

## Design basis

The framework follows the Loop Library's core loop pattern:

> Observe fresh state, take one bounded action, run a fixed check, record
> evidence, and stop on explicit success, no-op, approval, blocker, exhaustion,
> or stagnation conditions.

Useful references:

- [How agent loops work](https://signals.forwardfuture.ai/loop-library/learn/)
- [Loop Library agent guide](https://signals.forwardfuture.ai/loop-library/agents/)
- [Live Loop Library catalog](https://signals.forwardfuture.ai/loop-library/catalog.json)

## Contributing

Contributions are welcome when they make the framework more selective,
evidence-driven, testable, or safe. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

## License

[MIT](LICENSE)
