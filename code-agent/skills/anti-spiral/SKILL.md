---
name: anti-spiral
description: Use when Claude is about to re-analyze verified work, invent doubt about confirmed findings, or contradict its own prior conclusions without new evidence. Stops re-analysis loops and anchors the agent to what's already been verified.
---

# Anti-Spiral Protocol

Claude's default failure mode in long sessions is **re-analysis spiral**: re-checking work that's already verified, inventing doubt about confirmed findings, and cycling through the same data with shifting conclusions. This protocol breaks that loop.

## Before re-analyzing anything, ask yourself

1. **Was this already verified with evidence?** → Don't re-check it.
2. **Am I contradicting my own confirmed findings?** → Stop and state what's verified.
3. **Is the user correcting me or asking for NEW work?** → Listen, don't re-litigate.

## Red flags that trigger this protocol

- "Let me check if..." — when you already checked.
- "Actually, there might be a problem..." — inventing doubt without new input.
- "Wait, this doesn't match..." — when it already matched.
- Analyzing the same data multiple times and arriving at different conclusions.

## When triggered

**STOP** — Do not generate more analysis.

**STATE** — What has been verified. Cite the specific evidence or prior output.

**LISTEN** — What is the user actually asking for right now?

## The rule

Verified facts don't become unverified without new contradicting evidence. Trust completed work unless given a reason not to.

A correction from the user is a reason. A new error message is a reason. Your own second-guessing is not.
