# Lily's Digest Rules

These rules override defaults in SKILL.md. Follow these exactly.

## Schedule

- **Feed generation:** 7:00 AM PT daily (cron: `0 14 * * *` UTC)
- **Digest delivery:** 7:15 AM PT (cron triggers Jackie to post)
- **Time window:** Yesterday 7am PT → Today 7am PT (24h lookback)

## Discord Delivery

- **Channel:** `1485075381613760603` (#daily-digest)
- **Format:** Thread-based — one header in the main channel, all details inside the thread

### Step 1: Post header in main channel
```
🌅 Builder Digest — {Mon DD-1} 7am → {Mon DD} 7am PT
```
Example: `🌅 Builder Digest — Mar 21 7am → Mar 22 7am PT`

**This format is mandatory.** Always include:
- The emoji 🌅
- "Builder Digest" (not "Daily Digest")
- Both dates with "7am" and "PT"
- The arrow →

### Step 2: Create thread from header message
Thread name should match the header text.

### Step 3: Post digest sections inside the thread
Keep each message under 2000 chars. Wrap all URLs in `<>` to suppress embeds.

Group by category:
1. Agent Infra & Product
2. Community & Growth
3. Research & Dev Tools
4. Podcasts

### Step 4: Post polls inside the thread
One poll per section. Use `target: "channel:{threadId}"` for polls (NOT `threadId` parameter).

## Taste Filter

**Prioritize (put first):**
- Builders sharing real work and shipping (e.g. Garry Tan, Steipete, Cat Wu)
- Novel research/technical content with new information
- Specific opinions from community voices

**Deprioritize (put last or skip):**
- Insights Lily already knows (obvious takes)
- Drama / platform disputes
- "Why did this go viral" analysis
- Self-promotional content
- Frameworks outside Lily's stack (e.g. Next.js)

## Language

Mixed Chinese/English (bilingual). Summarize in Chinese, keep original quotes in English.

## Feed Source

Fetch from Lily's fork (includes extra accounts like @deedydas):
```
https://raw.githubusercontent.com/lilyzhng/follow-builders/main/feed-x.json
https://raw.githubusercontent.com/lilyzhng/follow-builders/main/feed-podcasts.json
```

## Important

- **Do NOT re-run the feed workflow multiple times per day.** The dedup state marks tweets as seen — re-runs produce empty feeds.
- Every tweet entry MUST have its clickable URL
- Do not fabricate skip reasons for taste notes — ask Lily
- After Lily votes on polls, update digest file with ✅/❌ marks
- Save digest to vault: `/data/vault/Build_My_Tribe/Following_Builders/YYYYMMDD.md`
