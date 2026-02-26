# Twitter/X Monitor for Japa Genie - COMPLETE SETUP

## Research Summary: Twitter/X Integration Options

### Option 1: OpenTweet Bridge (RECOMMENDED) ✅
**Cost:** $5.99/month (7-day free trial)  
**Difficulty:** Low  
**Risk:** Minimal  
**Setup Time:** 3 minutes  
**Capability:** Post tweets, threads, schedule content  
**URL:** https://opentweet.io

**How it works:**
- Connects your Twitter/X to OpenClaw via bridge API
- Your agent gets simple REST endpoint
- Never sees your Twitter credentials
- Single API key (starts with `ot_`)

**Commands:**
```bash
# Install skill
clawhub install opentweet/x-poster

# Set API key
export OPENTWEET_API_KEY="ot_your_key_here"
```

**Pros:**
- No Twitter App registration
- No OAuth complexity
- Can revoke instantly
- Cheaper than Twitter API ($5.99 vs $100/month)

**Cons:**
- Monthly cost
- Dependency on third-party service
- Not free

---

### Option 2: Twitter Free API Tier (BASIC) ⚠️
**Cost:** FREE  
**Difficulty:** Medium  
**Risk:** Medium (OAuth, rate limits)  
**Setup Time:** 1-2 hours  
**Capability:** Post ONLY (500 tweets/month), NO READ access  
**Limits:** 500 posts/month, no timeline reading, no search

**Setup:**
1. Create Twitter Developer account
2. Create App
3. Get Bearer Token + API keys
4. Configure OAuth
5. Implement rate limiting

**API Pricing:**
| Tier | Cost | Posts/Month | Read Access |
|------|------|-------------|-------------|
| Free | $0 | 500 | Write only |
| Basic | $100 | 3,000 | Limited read |
| Pro | $5,000 | 300,000 | Full access |

**NOT RECOMMENDED** - Free tier only allows posting, can't monitor or engage with existing content.

---

### Option 3: FireCrawl Monitoring (FREE) ✅
**Cost:** FREE (using your FireCrawl key)  
**Difficulty:** Low  
**Risk:** None  
**Setup Time:** 15 minutes  
**Capability:** Monitor, draft, alert only  
**Action:** You post manually

**How it works:**
- FireCrawl searches Twitter/X for relevant conversations
- Agent drafts responses
- Saves to memory files
- Telegram alerts you
- You copy/paste to post

**Pros:**
- 100% free
- No ban risk (you post manually)
- Can monitor unlimited accounts
- No API complexity

**Cons:**
- Manual posting (not automated)
- Slightly slower than API

---

### Option 4: CamoFox Browser (TECHNICAL)
**Cost:** FREE (+ VPS if needed)  
**Difficulty:** High  
**Risk:** Medium (Twitter can ban accounts)  
**Setup Time:** 2-4 hours  
**Capability:** Full automation - browse, post, engage like human  

**How it works:**
- Uses anti-detection Firefox browser
- Navigates Twitter like human
- Posts via browser interaction
- Bypasses API entirely

**Command:**
```bash
openclaw plugins install @askjo/camofox-browser
```

**Pros:**
- Full automation possible
- No API limits
- Can access features not in API

**Cons:**
- Complex setup
- Requires 300MB download
- Account ban risk if overused
- Needs technical management

---

## MY RECOMMENDATION FOR JAPA GENIE

### Tier 1: FireCrawl Monitoring (START HERE) 📊 
**Immediate:** Setup today, zero cost, low risk
**Use for:** Finding conversations, drafting content
**Timeline:** 15 minutes

### Tier 2: OpenTweet Bridge (WHEN READY) 🚀
**Upgrade:** When you want automated posting
**Cost:** $5.99/month
**Use for:** Scheduled content, consistent presence
**Timeline:** 3 minutes to setup after subscribing

### SKIP: Twitter Free API
Why? Can't monitor/search, only post. You need both.

---

## TARGET ACCOUNTS TO MONITOR

### High-Value Accounts Found:

**@LordPrimuss** - Primus
- Topic: Side gigs, remote work, tech opportunities
- Relevance: High - your target audience
- Japa Angle: How to access remote work from Nigeria

**@QoseemAdepoju** - Olalekan Adepoju
- Topic: Skilled Worker visas, alignment
- Relevance: Very High - specifically visa advice
- Japa Angle: Reply with Global Talent alternative

**@Emeeks_Uba** - Emeka Ubah
- Topic: Sponsorship, remote worker issues
- Relevance: High - infrastructure for remote workers
- Japa Angle: VPN/data solutions for remote workers

**@0xKimberly** 
- Topic: Digital nations, talent statelessness
- Relevance: Medium - philosophical alignment
- Japa Angle: Comment on practical "digital nomad" pathways

**@EngrEana**
- Topic: Skilled Worker visa changes
- Relevance: Very High - UK immigration expert
- Japa Angle: Reply with Global Talent comparison

---

## MONITORING QUERIES (Rotate These)

```
from:QoseemAdepoju visa Nigeria
from:EngrEana skilled worker UK
from:LordPrimuss remote work Nigeria
"Nigerian tech" visa OR migration OR relocate
site:twitter.com Nigerian developer remote job Europe
UK Global Talent visa Nigerian success story
```

---

## DRAFT TEMPLATES

### Template A: Reply to Visa Expert
```
Strong points on the Skilled Worker route. 

One thing people miss: Global Talent visa doesn't need employer sponsorship and gives immediate settlement path. 

For senior devs with 5+ years, it's often faster than Skilled Worker + ILR route.

I mapped the decision framework here if helpful: japagenie.com
```

### Template B: Reply to Remote Worker
```
This is exactly why I built a tool to help Nigerians navigate this.

The UK tech visa game changed in 2024. Three pathways most people don't know:
1. Global Talent (5+ years exp)
2. Scale-up (fast-growing companies)
3. Innovator (for founders)

All three are cheaper/faster than the MSc → PSW → Skilled Worker route everyone takes.

DM me your tech stack - I can tell you which one fits.
```

### Template C: Thread Participation
```
Nigerian dev here who made this move. 

The "tech" routes are real but underutilized. 

UK Global Talent: £1,623 (visa fee only), decision in 3 weeks, no job offer needed.

Most Nigerians never hear about it because it's not advertised.

Source: japagenie.com/visa-pathways
```

---

## SETUP CHECKLIST

### Option A: FireCrawl (Free - RIGHT NOW)
- [x] FireCrawl API key configured ✅
- [ ] Create monitoring cron job
- [ ] Setup Telegram alerts
- [ ] First search run
- [ ] Draft responses for top opportunities

### Option B: OpenTweet (Paid - WHEN READY)
- [ ] Create OpenTweet account (opentweet.io)
- [ ] Connect Twitter/X account
- [ ] Generate API key
- [ ] Install: `clawhub install opentweet/x-poster`
- [ ] Set env variable
- [ ] Test post

---

## PERFORMANCE TRACKING

Track these metrics weekly:

| Metric | Baseline | Target |
|--------|----------|--------|
| Opportunities found/week | 0 | 10+ |
| Replies drafted/week | 0 | 5+ |
| Your posts manual | 0 | 2-3 |
| Profile visits from Twitter | 0 | +20% |
| Site clicks from Twitter | 0 | +10% |
| DMs/conversations started | 0 | 2+ |

---

## NEXT ACTION

**Your move:**

**A) FireCrawl Setup (Free)**
I create monitoring pipeline now. Runs every 6 hours. Telegram alerts you. You post manually.

**B) OpenTweet Setup ($5.99/month)**
You create account, give me API key, I configure full automation.

**C) Both**
Start with FireCrawl (monitor what works), then upgrade to OpenTweet when you see ROI.

**What do you want?**
