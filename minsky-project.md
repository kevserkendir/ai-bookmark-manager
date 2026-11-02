# Recall: project (Team Minsky)

## Product
- Product name: Recall
- One line: Recall is an AI bookmark manager that keeps why you saved something and
  uses it to find the right sources when you get an assignment.
- Target user: graduate students who save articles for coursework. We start with our own
  workflows and classmates. Paolo gives another view.
- Problem: people save things but lose why they mattered, so they reopen everything when
  an assignment arrives.
- Platform: Lovable (hosting, database, sign-up). Confirmed.

## What the AI does inside the app (not builders)
1. Capture help: helps the user write a short reason for saving an item. User edits or confirms.
2. Match: compares saved items with an assignment description.
3. Explain: says why each item fits, using the source text and the user's reason.
4. Use corrections later: Recall stores a user's corrections and uses them to adjust later matching and ranking for that user's items. This is application-level personalization, with no model training or fine-tuning. Test: correct a match, rerun the same assignment, check that suggestions change as they should.
5. Chatbot (proposed): user can ask why an item matched, correct it, ask follow-ups.
6. Reasons on/off switch (proposed): lets us compare suggestions with and without reasons.

## Team roster (proposed until each owner confirms)
| Class | Name | Human owner | Agents | Core job | Folded in |
|---|---|---|---|---|---|
| PM | Product manager | Kevser | PM-CLAUDE | Scope, backlog, milestones, evaluation design, cost ledger, rules | Cost tracking |
| CM | Code manager | Tianyao | CM-LOVABLE, CM-CLAUDE | App code, database, deploy | Sign-up and email, security, event logging, AI steps and chatbot |
| EM | Experience manager | Charlene | EM-CLAUDE, EM-GEMINI | Capture experience, usability | Landing page, help guide, visuals and images |
| RM | Research manager | Vincent | RM-CHATGPT | User discovery, interviews, what a useful connection is | Analysis of user corrections |

Tools: Kevser uses Claude. Vincent uses ChatGPT. Charlene and Tianyao use Claude and Gemini.
Lovable is the build platform and is also used for image creation.

## Waiting on a trigger
| Function | Status | Trigger |
|---|---|---|
| Pricing and business model | unowned on purpose | Until we have evidence that people would pay |
| Usage analytics | reserved | After the prototype has real users |
| Final presentation | gated (shared human task) | Prototype review on November 23 |
