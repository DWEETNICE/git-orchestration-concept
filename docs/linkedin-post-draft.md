# LinkedIn Post Draft

I have been thinking about a pattern for agentic systems that feels increasingly important:

Models should think.
Memory should remember.
But orchestration should be deterministic.

When agent work only lives in chat, the system gets fragile. A session resets, context disappears, an output is produced but never verified, or nobody can tell which task is actually done.

The pattern I am exploring is a Git-backed orchestration layer:

- tasks are explicit files
- state transitions are governed by a small kernel
- agents receive scoped context packets
- verification is separate from production
- events are append-oriented
- Git records the trail of what changed and why

Git is not the brain of the system. It is the audit layer.

The goal is not to make a comprehensive framework yet. It is to sketch a deterministic floor underneath probabilistic agents, so work can survive context loss, be reviewed by humans, and recover cleanly when something stalls.

I put together a small conceptual repo and diagram here:

TODO: add repo link

The design rule I keep coming back to:

If correctness, recovery, or auditability matters, it should live in deterministic state, not only in prompt memory.
