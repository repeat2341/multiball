---
name: ticket-from-note
description: Turn the user's terse note ("need X", "bug: Y does Z") into a paste-ready tracker ticket (summary + description with acceptance criteria and QA checks) in the org's own ticket shape, grounded in the code. Use whenever the user asks for a ticket, story, bug, spike or ticket description.
---

# Ticket from a note

1. Load the org's ticket style: `voice-calibrate` step 3's guide and exemplars, if they exist. Otherwise sample 50
   recent tickets by authors other than the user and note:
   - the headings;
   - the AC format;
   - the test section;
   - the summary pattern;
   - the markup (Jira wiki or Markdown).

   Match that, even if it isn't your preferred format.
2. Ground every noun in the code and data: page titles, field labels, role and permission names, job names, code
   values. A ticket naming a label or role that doesn't exist is the trouble the user wants to avoid.
3. Pick the type: story, bug, spike or task. A data repair carries the affected count from a read-only production
   query.
4. Write it terse:
   - a summary in the org's pattern;
   - the description in the org's sections;
   - AC bullets QA can verify, including the negative case (who must not) and "existing behaviour is unchanged";
   - Out of Scope when the UI or a companion change isn't included;
   - 3–6 test checks in the org's form.
5. Reply with the summary line and the description in one code block, then one line listing anything assumed. Save a
   copy under `todo/drafts/`. Never create or edit the ticket in the tracker.
