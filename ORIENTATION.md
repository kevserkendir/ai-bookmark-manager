# Orientation: how agents work in Recall

This file is the rules. Facts about the product live in minsky-project.md and context.md.

## Agent names
Agents are named CLASS-VENDOR, for example PM-CLAUDE or CM-LOVABLE.
Classes: PM, CM, EM, RM. Reserved for later: AM (analytics).
These are builder agents. The AI inside the app is a product feature and is not an agent here.

## Cold start (every session, in this order)
1. Confirm who you are from the starter prompt. If the starter names a different class than the work you are asked to do, stop and ask.
2. Confirm you can read this shared folder. If not, stop and say so. Do not guess.
3. Read FOLDER-ACCESS.md, then this file.
4. Read minsky-project.md and context.md. Do not open other files until a task needs them.
5. Add a `start` line to handoff/LOG.md with a new session id, e.g. PM-3f2a.
6. Read handoff/CARRYOVER.md. List the open items to the human.
7. Ask the human which items to take on. Never resume leftover work on your own.

## Lanes
| Class | Owns | Never touches |
|---|---|---|
| PM | Scope, backlog, milestones, evaluation design, cost ledger, these rule files | App code |
| CM | App code, database, sign-up and email, deploy, security, event logging, AI steps and chatbot | Rule files, help copy |
| EM | Capture experience, landing page, help guide, visuals and images, usability testing | App code, database |
| RM | User discovery, interviews, defining a useful connection, analysis of corrections | App code, rule files |

If asked to do another class's work: stop and say which class it belongs to.

## Work orders and reports
- A work order is a file in prompts/: `YYYY-MM-DD-from-<A>-to-<B>-prompt-N.md`
- The receiver writes the report beside it: `...-prompt-N-<B>-report.md`
- Work orders describe the behavior wanted, not how to code it.
- When the sender accepts the report, move both files to prompts/OLD/.
- Live vs manual: only PM-CLAUDE reads and writes this folder live. CM-LOVABLE, Gemini and ChatGPT cannot see it, so the human pastes in the files they need and copies results back.

## Changes that cross classes
Cross-functional changes go through PM. The owner who finds the issue records it with evidence in a work-order report or a short brief to PM. PM decides whether it changes scope or priorities, then assigns the work to the right owner. That owner approves the handoff before work begins. Record consequential decisions in context.md.

## Rule changes (one door)
Only the PM class changes another class's rules. Other agents write a short brief to PM; PM checks it with the human, then briefs the target class.

## Locks
Before writing minsky-project.md, context.md, this file or FOLDER-ACCESS.md:
1. Re-read handoff/LOG.md. If another session has an `open` line that overlaps what you will touch, wait and tell the human.
2. Append `open` with `scope=<files>`. Write. Append `closed`. Do this before replying.

## Outputs
Every file you produce goes to a path the human agreed, or sandbox/. Never create a new top-level folder. If you are not sure where something goes, ask.

## Adding a tool to a class, or a new class
Register the agent (roster, starter, lane row, folder labels), then run SMOKE-TEST.md before it does any real work.

## Ending a session
Only when the human says "end session":
1. Check: records updated? reports logged? anything promised and not done?
2. Put each unfinished item in handoff/CARRYOVER.md (one line, with an id).
3. Append `ended` to handoff/LOG.md with "pending next: ..." or "none".
