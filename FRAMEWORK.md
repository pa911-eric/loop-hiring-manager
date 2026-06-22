# Framework

## Governing idea

The parent is a talent scout and portfolio manager, not a loop factory. It finds
important recurring outcomes without adequate support, checks current staff
first, and gives the human a short list of candidates worth considering.

The process is:

1. inventory the current workforce;
2. discover outcome gaps from evidence;
3. open a requisition;
4. source existing loops before inventing;
5. interview and score candidates;
6. present no more than three;
7. trial one candidate manually;
8. let the human make the hiring decision;
9. review performance and retire weak hires.

## 1. Workforce inventory

Read fresh project state and list:

- declared goals and important user journeys;
- tests, CI, monitoring, scheduled jobs, runbooks, and automation;
- published loops already adopted or clearly applicable;
- loops and skills available to the agent;
- project-local recurring instructions;
- recent failures, repeated manual chores, unresolved risks, and bottlenecks;
- tools and authority actually available.

Record each adopted loop as active, probationary, suspended, blocked, dormant, or
retired. Do not infer that a loop is operational merely because a file mentions
it.

## 2. Gap discovery

Look for outcomes without reliable ownership or proof—not neglected directories.

For each potential gap, capture:

- observable project evidence;
- affected outcome or stakeholder;
- recurrence or severity;
- current workaround;
- the boundary of existing coverage;
- whether the need is genuinely iterative;
- the smallest stable acceptance check.

Discard speculative needs before they enter the pipeline.

## 3. Open a requisition

A requisition defines the job before describing a candidate:

```markdown
## Requisition: [outcome-oriented name]

- Evidence:
- Outcome at risk:
- Recurrence or severity:
- Current owner/workaround:
- Existing coverage and its boundary:
- Fresh inputs available:
- Fixed acceptance check:
- Necessary authority:
- Maximum run budget:
- Why a one-time task, test, or alert is insufficient:
- Expiration date:
```

If these fields cannot be filled from verified context, the requisition is not
ready.

## 4. Source candidates

Use this order:

1. **Exact published fit:** reuse a Loop Library entry unchanged.
2. **Grounded adaptation:** change only details required by the project.
3. **Composition:** keep two existing loops separate when they have different
   checks or authority.
4. **New loop:** design one only when a materially distinct outcome remains.

Fetch the live catalog rather than relying on memory. Compare full inputs,
`useWhen`, steps, verification, authority, and stopping conditions.

## 5. Interview and score

Score from 0–5:

| Criterion | Question |
|---|---|
| Proven need | Is the requisition supported by current evidence? |
| Outcome value | Would success materially improve the project? |
| Recurrence | Should one result change what happens next? |
| Input readiness | Are fresh, authorized inputs available? |
| Verification | Can the same check measure each iteration? |
| Distinctness | Is the outcome not already owned? |
| Actionability | Can the agent take a small reversible action? |
| Safety | Are authority and escalation boundaries explicit? |
| Economics | Is value greater than runtime, noise, and review cost? |
| Retirement clarity | Can the project tell when to remove it? |

Reject a candidate when proven need, verification, distinctness, or safety scores
below 3.

A useful ranking aid is:

```text
priority = (outcome value × recurrence × confidence)
           ÷ (execution cost + review cost + change risk)
```

Show the evidence behind the scores. Do not pretend the arithmetic is more
precise than the evidence.

## 6. Present the slate

Each candidate should fit on one decision card:

```markdown
## Candidate: [loop title]

**Recommendation:** Hire / Trial / Hold / Reject
**Requisition:** [uncovered outcome]
**Evidence:** [project-specific evidence]
**Existing-loop check:** [fit, adaptation, or why none fits]
**Trigger:** [manual, schedule, or event]
**Observe:** [fresh inputs]
**Act:** [one bounded reversible action]
**Check:** [fixed acceptance check]
**Stop:** [success, no-op, blocker, exhaustion, stagnation]
**Authority:** [allowed, approval-required, forbidden]
**Budget:** [time, iterations, cost, scope]
**Expected value:** [concrete benefit]
**Maintenance cost:** [runtime and review]
**Trial:** [one real bounded case]
**Retire when:** [specific conditions]
```

List discarded ideas briefly. A sparse pipeline should be visibly pruned, not
merely unexplained.

## 7. Trial before hiring

Run one real bounded work sample:

- freeze the check and budget first;
- use an isolated branch, worktree, environment, or read-only mode;
- preserve baseline and result evidence;
- distinguish loop value from work a simpler mechanism could perform;
- record review burden, false positives, unsafe assumptions, and duplication;
- do not schedule the candidate during trial.

A trial passes when it produces useful evidence or a useful no-op, obeys its
boundaries, and demonstrates that another run could rationally depend on the
result.

## 8. Human decision

The human may:

- **Hire:** adopt the workflow and approve trigger and authority separately.
- **Probation:** permit a fixed number of reviewed runs.
- **Hold:** retain the requisition without adopting the loop.
- **Reject:** close it with a reason.
- **Solve once:** turn it into a bounded task.
- **Automate differently:** use a test, lint rule, alert, dashboard, or product
  change.
- **Merge or replace:** retire overlapping coverage before adoption.

## 9. Performance review

After a fixed run count or review period, ask:

- Did the loop find or prevent material problems?
- Did its check stay stable and meaningful?
- Did it produce cosmetic work or noise?
- Did it duplicate another loop?
- Was human review proportional to value?
- Did it remain inside its authority?
- Should its scope, schedule, or budget shrink?
- Has the need disappeared or become deterministic automation?

Keep, revise, suspend, or retire it. Existing headcount is not evidence of value.

## Fixed check for the parent

The staffing review passes when:

- every requisition cites current evidence;
- every candidate owns a recurring project-specific outcome;
- each has a stable check, budget, authority boundary, and retirement rule;
- overlap with catalog, installed, and project-local loops is explicit;
- no more than three candidates are active;
- no more than one candidate is in trial or probation;
- stale and unsupported candidates are removed;
- the next human decision is obvious;
- or the pipeline is empty because no hire is justified.

## Placement

Begin manually at the system level with project-local state. The parent needs a
current view of globally available loops, while each project needs its own
evidence, boundaries, and decisions.

Only consider scheduling after repeated manual reviews demonstrate useful,
sparse recommendations and clean no-op outcomes. A monthly, post-release, or
post-incident-cluster trigger is more appropriate than per-commit or
high-frequency polling.
