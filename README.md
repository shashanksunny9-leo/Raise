# Escalation Portal (prototype)
Next.js 14 on Vercel, code on GitHub, ServiceNow via adapter (SERVICENOW_MODE=mock|live).
## Run
`npm install && cp .env.example .env.local && npm run dev` then open http://localhost:3000, sign in (mock), try the demo incidents.
Tests: `npm test`. Build: `npm run build`.
## Deploy
1. Push to GitHub. 2. Import the repo in Vercel (previews per PR are automatic). 3. Set env vars from `.env.example`.
4. Cron in `vercel.json` runs every 15 min (needs Vercel Pro; on Hobby change the schedule to daily).
5. Branch protection: require CI + 1 review on main.
## Demo script
Sign in as colleague > INC0012345 (past 48h): tick "Only I am affected" > Escalate now > task created.
INC0012346 (recent): Low/Medium shows "after" date > Nudge support team > chaser recorded. Sign in as team > /team to acknowledge, reassign, override.
## Docs
docs/ARCHITECTURE.md, docs/RULES.md, servicenow/IMPORT_GUIDE.md
**Colleague guide:** open the Escalate button from your incident, answer the questions, submit, track on My escalations.
**Admin guide:** use /team to acknowledge, reassign, add notes, close, or override (reason required, audited).
