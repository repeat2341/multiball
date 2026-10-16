---
name: voice-calibrate
description: Learn the team's real writing voice for commit messages, code comments, PR text and tickets from its own pre-AI history, then confirm it with a short y/n quiz the user answers. Use when the user wants commits/comments/PRs/tickets that don't read as AI-written, or complains about placeholder commit messages.
---

# Voice calibration

Writing that sounds generated costs the user credibility with reviewers. Measure the team's voice and copy it; never
use taste.

1. **Commits.** `git log --all --no-merges --format='%an%x09%s'` across every team repo. Drop bots and placeholders,
   then measure:
   - median length and word count;
   - share starting lowercase, share ending with a period;
   - ticket-key and `feat:`-style prefixes;
   - the top first words.

   Read samples from the user's own non-placeholder commits and from the three most prolific clear writers. Add 10–20
   well-run OSS repos in the same stack for contrast.
2. **Comments.** Pull only comment lines added before agents arrived (`git log --before=<year>-01-01 -p`, the `+//`
   and `+#` lines). Drop commented-out code. Measure case, period, contractions and length, and read about a hundred
   that explain a why ("since", "because", "otherwise", "so we").
3. **Tickets.** If the tracker is readable, pull a few thousand tickets by the org's prolific authors who are not the
   user. Measure the section headings, the AC format (count Given/When/Then; don't assume it), the test section and
   the summary pattern. Keep about ten exemplars.
4. **Draft rules** with the numbers beside them. Then write 100 real examples: rewrite the user's placeholder commits
   from their diffs, stratified by repo.
5. **Quiz.** Build a page that shows each example with a one-line description of the diff, links, y/n and a note, and
   stores the verdicts where you can read them back. The user stops when satisfied. Fold every n and every note into
   the rules.
6. **Install the rules:**
   - a memory with the rules, the user's quoted rulings and approved examples;
   - a line in `CLAUDE.md`;
   - the slot template;
   - the commit helper takes a message (`gcom "<msg>"`), and agents always pass one;
   - the PR helper writes only the title line and the ticket link, placed per repo template, and refuses a body
     without the link.

   Never add AI attribution anywhere.
