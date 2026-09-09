# Same test lead in Zapier vs Make vs n8n: what actually differs
Status: FACT-CHECKED 2026-09-10 against live sources (URLs below). Test lead fictitious; n8n path measured locally; Zapier/Make/CRM figures cited from official docs as noted. Re-verify prices at post time – SaaS pricing moves.

## Setup (identical test lead, fictitious)
`{name: Jane, email: jane.test@example.com, message: "Need follow-up for 40 open-house leads/mo", source: web-form}`
Flow: webhook → validate → dedupe by email → CRM create → score → Slack alert → log. Success = CRM record + P1 alert; failure = 400 + error log, nothing silent.

## Measured here (n8n, self-hosted, this VPS)
- Build time: ~1h for the 6-node skeleton (workflow.json in demo repo).
- Runtime cost at 1k leads/mo: $0 marginal (VPS already provisioned; log disk use to be measured after 30 days live – estimate until then).
- Failure behavior: demonstrated live in the demo (bad email → 400 + #errors-test; duplicate → merge).
- Maintenance surface: you own upgrades/backups/monitoring. Honest cost: ~1–2h/mo (GUESS – label as estimate when posting).

## Cited from public pricing/docs (verified 2026-09-10)
- Zapier (official machine-readable pricing ref, https://zapier.com/pricing, updated 2026-09-09): each successful action step = 1 task; triggers, polling, and built-ins (Filter/Paths/Formatter) = 0. Our flow ≈ trigger(0) + 4–5 actions ≈ **4–5 tasks/lead**. Free = 100 tasks/mo + two-step zaps only (our multi-step flow REQUIRES Pro). Pro 750 tasks = $19.99/mo annual ($29.99 monthly); Pro 5,000 = $89/mo annual. Polling 15 min Free / 2 min Pro. Per-1k math: 120 leads/mo ≈ 600 tasks → 750 tier; 1,000 leads/mo ≈ 5,000 tasks → $89/mo annual.
- Make (official page snippets via search 2026-09-10 – direct fetch 403'd; structure corroborated by 3 third-party 2026 guides, prices as reported band): billing unit is **credits** (renamed from operations Aug 2025); most actions = 1 credit. Free = 1,000 credits/mo, 2 scenarios, 15-min interval. Core/Pro/Teams all base 10,000 credits/mo (tiers add features, not volume) at ~$12 / ~$21 / ~$38 mo annual (monthly higher). Our flow ≈ 5–6 credits/lead → 1,000 leads ≈ 5–6k credits → Core tier suffices.
- CRM limits bind NONE of the three at SMB volume: HubSpot official docs (developers.hubspot.com, verified 2026-09-10) – private apps 100 req/10s burst (Free/Starter), 190 (Pro/Ent), daily 250k/625k/1M; public OAuth 110/10s. Pipedrive official docs – burst by plan (20–480 req/2s) + daily token budget. GoHighLevel V2 – 100/10s, 200k/day/location, no batch endpoints for most resources (secondary source: clonepartner.com 2026 comparison – treat as approximate). Practical edge: HubSpot batch endpoints (100 records/call) matter for migrations, not for per-lead intake.

## When I'd pick each (opinion, labeled as opinion)
- Zapier: team already lives there, <500 leads/mo, nobody wants to own infra. Pay per-run for zero maintenance.
- Make: visual routing + error handling matter, mid volume, some technical owner exists.
- n8n self-hosted: volume makes per-run pricing sting, you want the workflow file in git, and someone owns the VPS.

## Anti-claims (do NOT write these)
- No "10× cheaper" without the verified table. No uptime promises. No client results (none yet – say so).

## CTA
One table, three verified price rows, then the demo. Post to DEV + GitHub discussion + helpful answers in automation threads (rules-respecting, no DMs).

## Pre-post checklist
- [x] 3 price rows verified against live sources 2026-09-10 (Zapier official ref; Make official snippets + 3 corroborating guides, band-labeled; HubSpot/Pipedrive official docs, GHL secondary-labeled)
- [ ] n8n 30-day disk/log figure measured or labeled estimate (currently labeled GUESS – keep label)
- [x] No sentence claims a measured result that was actually cited (measured vs cited sections separated)
