# Model Systems Labs

We build small, measured systems for agents that need to operate real software.

The through-line is simple: make the environment easier for the model to reason about, then prove the result with traces, evals, and repeatable checks.

## Current Work

### Lenslet

Compact browser observation frames for computer-use agents.

Lenslet captures the full Playwright/CDP accessibility and DOM state for traceability, then routes a smaller planner-facing frame: relevant controls, blocking errors, selected values, state changes, summarized repeated structures, context handles, and routing diagnostics.

Current local browser benchmark:

| Result | Measurement |
| --- | ---: |
| Planner token reduction | 26.49% |
| Compact-vs-raw task parity | 3/3 |
| Action benchmark success | 5/5 |
| Unsafe or forbidden actions | 0 |

This is an apples-to-apples benchmark inside Lenslet's own browser runner, not a claim about any private browser-agent implementation.

## What We Care About

- **Measurable agent systems:** every claim should have a trace, eval, benchmark, or direct artifact behind it.
- **Interface compression:** agents should see the useful structure of software, not every noisy pixel or repeated UI node.
- **Safety at the executor boundary:** planner actions are suggestions; the runner still blocks credentials, checkout, payment, booking, and incompatible field actions by default.
- **Small primitives over big theater:** capture, normalize, route, plan, execute, diff, repeat.

## Shape Of The Stack

```text
browser state
  -> full UI graph
  -> task-aware router
  -> compact planner frame
  -> typed planner action
  -> guarded executor
  -> recapture + trace
```

## Status

Model Systems Labs is early and intentionally narrow right now. The first public-facing work is around browser-agent observation, evaluation, and execution traces. More projects will become visible when the measurements are worth showing.

If something here sounds useful, the repo should show the receipts: commands, fixtures, reports, and the exact places where the prototype still has limits.
