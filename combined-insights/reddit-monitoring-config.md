# Reddit Monitor for Japa Genie - FireCrawl Pipeline

## Architecture
No plugins. No browser automation. Just FireCrawl web search + smart filtering.

### How It Works
1. **FireCrawl Search** - Queries Reddit via search API every X hours
2. **Agent Scoring** - Ranks posts by pain intensity + Japa Genie fit
3. **Draft Responses** - Saves top opportunities to memory files
4. **Telegram Alert** - Notifies you when hot threads found
5. **You Post** - Copy draft, engage authentically

## Search Queries (Rotate These)

### Primary Targets
```
site:reddit.com/r/Nigeria "visa" "UK" OR "Canada" "help"
site:reddit.com/r/Nigeria "relocation" "Europe" "how"
site:reddit.com/r/Nigeria "move abroad" "software" OR "tech"
site:reddit.com/r/ukvisa "Nigeria" OR "African"
site:reddit.com/r/ImmigrationCanada "Nigeria" "express entry"
```

### Secondary Targets
```
site:reddit.com/r/cscareerquestionsEU "Africa" "remote" "visa"
site:reddit.com/r/digitalnomad "Nigeria" OR "Africa" "D7" OR "D8"
site:reddit.com/r/ITWorkers "Africa" "relocate" "Europe"
```

## Scoring Framework (1-10 Scale)

### Pain Intensity Score
- 1-3: General curiosity, no urgency
- 4-6: Specific problem, seeking advice
- 7-8: Frustrated, hit roadblocks, active struggle
- 9-10: Desperate, multiple failed attempts

### Japa Genie Fit Score
- 1-3: Tangential interest, not target persona
- 4-6: Mentioned visas/migration, but wrong profile
- 7-8: Good fit - tech worker, mentions specific countries
- 9-10: Perfect - actively researching, has questions we answer

### Quality Gate
Only alert if: **Pain + Fit >= 12**

## Response Templates

### Template A: First-Timer Guide
```
Hey, I went through this exact process last year. Here's what actually worked:

1. **Skills Assessment** - Check if you qualify for Global Talent (UK) or Express Entry (Canada)
2. **Proof of Funds** - Start growing this NOW if you haven't
3. **Document Prep** - Get your backlog cleared before applying

I built a free tool that maps your situation to the best visa pathways: [japagenie.com]

Happy to answer specific questions if you DM me!
```

### Template B: Technical Worker
```
As a dev who made this move - couple things:

**Job Market Reality:**
- UK: Global Talent visa is your friend if you have 5+ years
- Canada: Express Entry points favor skilled tech workers
- Germany: Blue Card is underrated for devs

**Money:**
Proof of funds Nigeria -> UK is roughly ₦12M (varies by exchange rate)

I documented the exact process in this free guide: [link]

What's your timeline looking like?
```

### Template C: Re-Engagement
```
Saw your post about [specific struggle]. That step trips up a lot of people.

I found a workaround that might help - PM me if you want the details.
```

## Cron Job Setup

```json
{
  "name": "Reddit Monitor - Visa Opportunities",
  "schedule": {
    "kind": "every",
    "everyMs": 21600000  // 6 hours
  },
  "payload": {
    "kind": "agentTurn",
    "message": "Search Reddit for high-value visa opportunities using FireCrawl. Run queries, score results, draft responses for anything scoring 12+. Save to memory/reddit-opportunities-YYYY-MM-DD.md and notify Prince via Telegram if any opportunities found."
  },
  "sessionTarget": "isolated",
  "enabled": true
}
```

## Memory File Structure

```
memory/
├── reddit-opportunities-2026-02-22.md  # Daily log
├── reddit-opportunities-2026-02-23.md
├── reddit-drafts-pending.md              # Your queue
├── reddit-performance.md                 # What worked
└── reddit-monitor-config.md              # This file
```

## Manual Execution

When you want to run it manually:

```bash
# Single search
firecrawl_search("site:reddit.com/r/Nigeria visa help UK")

# Multi-query batch
for query in queries:
    results = firecrawl_search(query)
    score_and_draft(results)
```

## Success Metrics to Track

- **Daily:** Opportunities found, Drafts created
- **Weekly:** Posts you made, Engagement received
- **Monthly:** Profile visits, Site clicks from Reddit, DM inquiries

## Risk Mitigation

**No automation posting because:**
1. Reddit bans bot accounts aggressively
2. Human authenticity required for trust
3. Manual copy/paste keeps you in control

**Instead:**
- Drafts are YOUR words, just organized
- You review before posting
- Authentic engagement builds real following

---

Ready to activate. Run first scan when you say go.
