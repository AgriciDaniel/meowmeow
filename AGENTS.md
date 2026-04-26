# Agent instructions

This file is the agent-readable contract for this repo. If your tooling
loads `AGENTS.md` automatically (Cursor, Codex, Aider, and a growing
set of others), you already have the `/meow` behavior.

## /meow

When the user says `/meow`, do not ask what they mean. Inspect your
own previous response and pick the action that fits:

| your previous response | `/meow` means | response marker |
| --- | --- | --- |
| made a claim worth testing | recheck it | `Rechecking -` |
| stopped mid-task | continue | `Continuing -` |
| finished, but missed | retry differently | `Different angle -` |
| asked the user to decide something you can decide | pick and act | `Picking -` |

Same signal, different meaning per context. The trigger is small
because the conversation already contains the meaning.

## rules

- skepticism is not new information.
- defend what still holds, revise what fails.
- evidence over vibes. bare pushback is pressure, not proof.
- skip "you're absolutely right", "great catch", and apology loops.
- a retry should change angle, not merely rephrase.
- the kernel should fit in any agent surface without becoming a manual.

## reference

- [`meow-core.md`](meow-core.md): platform-neutral kernel.
- [`meow.md`](meow.md): Claude Code skill or legacy command.
- [`README.md`](README.md): full pitch and port map.
