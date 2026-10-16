# MULTIBALL

[![MULTIBALL! MULTIBALL!! MUL-TI-BALL!!!](https://img.youtube.com/vi/oQF8rQaIjUE/hqdefault.jpg)](https://www.youtube.com/watch?v=oQF8rQaIjUE&t=11s)

*Third ball locked. Several stories in play at once, each in its own slot.*\
*Clip: [Futurama, "Fear of a Bot Planet" (S1E5, 1999): Best Of Blernsball](https://www.youtube.com/watch?v=oQF8rQaIjUE&t=11s), official upload by SYFY.*

MULTIBALL runs several Claude Code sessions at once on one machine, one story each, without them stepping on each other.
Each runs against a full, isolated copy of your system: its own worktrees, containers, database and browser sign-in.
One hub session plans the work, launches the slots, checks every hand-back against the acceptance criteria, and fixes
its own tooling from what each slot reports. You rule on direction and use the product.

It comes as one file an agent boots from, `MULTIBALL.ai.md`, plus a Claude Code plugin with the skills that go with it.
The plugin ships instructions, specs and templates only: Claude builds each tool for your stack from them, so there is
no code to trust or keep in sync.

## Install

```
/plugin marketplace add pburkindine/multiball
/plugin install multiball@multiball
```

Then, in the repo you want to run it on:

```
/multiball:multiball
```

The hub reads `MULTIBALL.ai.md`, checks it's running in WezTerm, asks you one set of setup questions, and builds the
setup step by step, each step ending with a check.

## What you get

| | |
|---|---|
| **Slots** | Git worktrees for code. A container network per slot with a "pod" that keeps every hardcoded `localhost` address meaning "this slot", so no app config changes. A copy-on-write clone of a production-shaped database: 13 GB in under a second on btrfs |
| **A guard** | A PreToolUse hook that keeps each spoke inside its slot: no history rewrites, no PR edits, no writes to your own checkouts, no cloud writes |
| **Hand-backs that improve the harness** | Every story ends with `## Durable facts` (folded into the knowledge base) and `## Harness and automation` (what cost time, and the fix). The hub acts on both |
| **Knowledge that checks itself** | Concept notes where every fact cites `path:line` ~ `symbol`, and a script fails when a citation drifts. Generated maps of routes, permissions and enums. One ranked search across code, specs, notes, meetings and stories |
| **Your voice, not an AI's** | Commit messages, PR text, code comments and tickets calibrated against your team's own pre-AI writing, then confirmed by a quiz you answer in a few minutes (`voice-calibrate`). Placeholder commits and agent-flavoured PR text cost people credibility |
| **Tickets from a one-line note** | `ticket-from-note` turns "need X" into a summary and description in your org's own ticket shape, with acceptance criteria and QA checks, after it has measured that shape |
| **Video** | `watch-video` turns a YouTube link or a file into captions or a Whisper transcript, plus contact sheets Claude reads |
| **The choir, used sparingly** | Other model CLIs review blind only on architecture, or where one session would be a mistake |

## Status

v0.1: the method and the skills. The slot CLI (`mb`), the guard and the knowledge tools are described in
`MULTIBALL.ai.md` precisely enough to build, and the boot sequence builds them for your stack. Generic reference
implementations of those tools come next.

## Requirements

macOS or Linux, Claude Code, Docker (OrbStack recommended on macOS), WezTerm (or `MULTIBALL_FLAT=1` to run inside VS
Code or Cursor terminals), git. Optional: yt-dlp, ffmpeg and whisper-cpp for `watch-video`; Obsidian for reading the
knowledge base.

## License

MIT. See [LICENSE](LICENSE).

## Credits

The name and the chant come from the blernsball game in *Futurama*, "Fear of a Bot Planet" (Season 1, Episode 5,
1999), created by Matt Groening. The thumbnail links to SYFY's official clip on YouTube; no footage is included in this
repo.
