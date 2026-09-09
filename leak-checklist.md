# The 12-point lead-intake leak checklist (from the $750 audit)
Status: OFFLINE DRAFT 2026-09-09 – not posted. Test data only, no client claims.
Post to: r/agency value post + gist (per channel plan), only where rules allow; no DMs.

Score each 0 (broken/missing), 1 (partial/manual), 2 (automated + logged). Max 24.

## Speed
1. New web-form lead reaches a human or queue in under 5 minutes, nights/weekends included.
2. Lead-ad (Facebook/Google) leads flow automatically – no CSV download + import step.
3. Slowest source identified: you can name which channel lags and by how long.

## Assignment & routing
4. Every lead gets an owner automatically (round-robin, territory, or intent rule) – none sit unassigned.
5. Hot leads (explicit intent + fit) trigger an instant alert (Slack/SMS), not just a CRM row.
6. After-hours/weekend leads have a defined path, not "we'll see it Monday".

## Data quality
7. Duplicates impossible by construction (search-before-create on email) – not "we merge weekly".
8. Invalid emails rejected at intake with an error log – not silently dropped, not silently stored.
9. Every record carries source + timestamp + consent basis.

## Follow-through
10. Untouched-lead SLA exists (e.g. 2h) with escalation when breached.
11. No-reply sequences are templated + human-approved, never fully auto-sent.
12. One dashboard answers: received / contacted / qualified / lost + where each loss happened.

## Scoring yourself
- 20–24: tight operation; audit buys you the error-branch + scoring layer only.
- 12–19: 1–2 recovered deals/month typically pay for a $998–$4,500 build. This is the audit's sweet spot.
- 0–11: fix assignment + SLA before buying any AI scoring – scoring a leaking funnel wastes money. (I'll tell you this on the call instead of selling you a build.)

## Worked example
Run the same 3 test leads through the public demo: https://ghostcoder6969.github.io/lead-intake-automation-demo/ – good lead created + scored, bad email rejected with error log, repeat submit merged not duplicated. Fictitious data; the rules are the real ones from the workflow file in that repo.

## CTA
Want this scored against YOUR funnel? The $750 audit maps your top 3–5 automations with hours/mo + dollar math, credited toward a build within 14 days. Ask via GitHub Issues on the demo repo. If the math doesn't clear 2× build price in 90 days, the deliverable is "don't build" – that's what the fee buys.
