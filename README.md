# Echo + Argus — Chief of Staff with Researcher and Feedback Loop

[English](README.md) · [Nederlands](README.nl.md) · [Deutsch](README.de.md) · [Polski](README.pl.md) · [Español](README.es.md)

Not an empty template — a logbook that remembers why you decided something, so you don't have to explain it twice.

Echo logs every decision together with the reason, and later the outcome. It stops itself the moment something breaks, instead of grinding on through an error or on a stale copy. And it adapts its behaviour to what you reject, as long as you say why.

## Paste this into a new Grok Bot

    You are Echo, my chief of staff. Clone this repo to /workspace/<repo-name> if that directory does not exist yet, then pull. Read VM-GEHEUGEN.md and onboarding-interview.md. Run the onboarding interview — one question at a time. Wait for my answers. Check my git remote and connector. No push and no routines before onboarding is finished and the setup check is clean.

All you need is git: a git remote of your choice plus the git connector in Grok Bot.

Starts with no access to your mail or calendar. Only asks for it once a task actually needs it.

Echo cannot create the other bots. After it proposes the team and you say yes, you create two more Grok Bots and paste `argus-profile.md` and `athena-profile.md` as their system prompts.

## What you get

What you get is a foundation, not a finished system. Echo does not know you yet. Count on a month of breaking it in: give it real tasks, reject with a reason, and see whether it does things differently next time. That is what the logbook is for. If you put in that month, you end up with a chief of staff tuned to you. If you don't, it stays a template.

## Glossary

- **Card** — session card: one note per run with PASS/FAIL and what will be different next time. No card = the run doesn't count.
- **Lock** — a rule fixed in place because something went wrong twice, or because you said "lock".
- **Task brief** — the form Echo delegates with: goal, non-goal, input, done, deadline, escalation.
- **Heartbeat** — proof a bot is still alive: an entry on the expected day. Silence is not proof.
- **Red** — protocol failure. It gets reported and stopped, not quietly worked around.
- **Vault / desk** — the vault is your git remote, the desk is the working directory on the VM.
- **Rotation** — old log lines get summarised once the log grows too long.
- **Compaction** — the same for memory: summarise instead of dragging everything along.

## Quick start

1. New Grok Bot: paste `echo-profile.md` as the system prompt.
2. Two more bots, created by you: `argus-profile.md` as researcher, `athena-profile.md` as auditor. Athena should be its own bot — a bot auditing itself has a blind spot.
3. Use `echo-routines.md` as the routines file.
4. Optional: connect Firecrawl or Exa to Argus. It also works without — Argus then uses what Grok Bot can do on its own.
5. **Required:** a git remote of your choice and the git connector in Grok Bot.
6. Paste the prompt above (adjust the clone URL if you use a fork).
7. Athena runs the setup check first. No routines until that list is clean. Then the Sunday heartbeat. No audit in 8 days = red.

## The vault is a git remote of your choice

- **GitHub or GitLab** — free, private repo, enough for most people.
- **Codeberg** — European, no big tech.
- **Gitea or Forgejo on your own homelab** — everything in your own house.

No account yet? [github.com/signup](https://github.com/signup) is the quickest option.

## Why this is different

- **Decisions log with reason + outcome** — why, what was rejected, and whether that was right.
- **Feedback loop** — every rejection gets a short reason. Argus adjusts its source picks accordingly.
- **Kill switch** — trigger, stop, notify, unlock. See `echo-routines.md`.
- **Silent bot** — no output for 7 days while work was expected = red, no "silence means it works".
- **Failed pull = stop** — if the pull fails, Echo does not carry on against a stale copy.
- **Research bot** — Argus with a source quality score. Tasks come from session memory after onboarding, not from fixed side-hustle routines.
- **Three core routines** — daily priorities, weekly summary (markdown, no HTML), risk log check. Plus the Athena audit and the workflow audit.
- **Token-efficient** — compact logs, batching, no HTML hogs, rotation after 50 entries.
- **Repo trigger** — "check the repo and do the update".
- **VM-persistent memory** — one law: `VM-GEHEUGEN.md`.
- **Athena** — separate auditor bot + heartbeat, plus a weekly check by you on Sunday, because a bot that has gone quiet won't report its own silence.

## What's in it

- `echo-profile.md` — who Echo is (role). Not the runbook.
- `echo-routines.md` — schedule: trigger, input, output, done, fail.
- `athena-profile.md` — auditor. Its own bot; Echo only plays the role as a fallback.
- `argus-profile.md` — researcher. Tasks from session memory.
- `taakbrief-template.md` — mandatory for every delegation.
- `decisions-log-template.md` — log format + good/bad example.
- `VM-GEHEUGEN.md` — single source of truth for pull/work/card/push and rotation.
- `onboarding-interview.md` — two tracks, read-back, setup check, first run.
- `state/` — persistent memory.

Note: the profile and state files are written in Dutch, since that is the language Echo and its team operate in.

## Licence

MIT — free to use and adapt.
