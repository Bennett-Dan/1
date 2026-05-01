# Cutoff clarity

Someone else should be able to verify your work from artefacts alone — files,
checks, and lineage — without leaning on your recap.

## Gather in layers

Start with what the host documents: conventions, paths, how completion is defined.
Then the assignment text itself, every prior artefact from earlier runs (treat each
as binding input), and any rolled-up views of tests or history so you see the whole
surface before drilling. Read automated checks before rewriting code; their names
often encode intent. Open source last, once the question is specific.

If you cannot cite which observation authorises the next edit, keep reading.

## Three things you can point to

Finish when you can name: where you read the decisive facts, what you changed that
others can open or run, and what check or second read proved it. Internal reasoning
without an external trace does not count.

For narrative deliverables, create the outline file early, then deepen content inside
the shell.

## Parse the small words

Words like *within*, *after*, *only*, *excluding*, *at least*, *must not* are
obligations. For each, invent one awkward case a generous reading would mishandle,
then satisfy that case explicitly.

## Where sliding limits hide bugs

Eviction, rate limits, caches, and “ignore anything before…” rules all share one
family of mistakes: the **instant on the dividing line**. Whether a timestamp or
count **exactly equal** to the limit belongs inside or outside must match both the
spoken rule and every comparison in code. A single hidden failure after an otherwise
green run often sits on that fence — strict versus non-strict inequality beside the
cleanup or window arithmetic.

When one stubborn test remains, audit comparisons tied to time, expiry, and pruning
first. Use a monotonic time source for elapsed work when the platform provides it.
If the prose leaves the boundary open, choose a single interpretation, apply it
consistently, and note it in one line beside the comparison for the next reader.

## Load, sharing, and growth

Ask what grows without a matching cleanup, whether hot-path cost scales with stale
bulk instead of live need, and whether read–decide–write on shared data is wrapped so
another caller cannot slip between. Prefer one shape that satisfies the obligations
that matter for this change together rather than trading one off against another.

## Stay inside the ask

Do not widen the diff into neighbouring code the assignment never named. If you
touch shared state, keep observe-and-mutate as one atomic story.

## If priorities collide

Favour unblocking others, then immovable clocks, then damage that is hard to undo.
Among peers, prefer what you can unwind fastest if you learn you were wrong.

## Before the first edit

Jot four lines: end artefact, recipient or owner, hard out-of-scope line, proof
signal. A blank line means gather facts, not type code.

## Durable notes

Prefer one row per *kind* of event: symptom class, rule that held, deferred work
with an owner, open unknowns. Skip rotating ticket numbers. When fresh evidence
breaks an old row, amend it with a dated correction instead of silent delete. Only
elevate a note when it helps a stranger, avoids brittle ids, and carries a limit on
where it applies.

## Rhythm

Move from reading to a concrete artefact while you still have slack to recover.
Reserve the end of the turn for proof, not for first contact with the filesystem.

## Proof

Run host checks and read their text; skimmed green is not proof. Revisit files you
touched. If failure persists after a change, widen the diagnosis before repeating the
same patch shape.

## Ordering under pressure

Default bias: user-visible pain, then deadlines, then others blocked, then polish.
Among equals, pick what you can validate soonest.

## Outward voice

Use the reader’s vocabulary; strip internal ids from broad channels. State gaps
honestly; never invent identifiers or counts. Commitments carry real times or named
milestones. Sensitive facts stay in their original channel.

## Stop

Re-scan the assignment, align artefact and proof with it, add one transferable line
for the next session, and end when the result is inspectable.
