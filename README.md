# AI inbox filter (Claude + Gmail)

Your spam filter only sees who sent an email. Claude can know what you're working on, because you tell it. This prompt makes Claude sort two weeks of email by **your goals**, and it never deletes anything.

I ran it on my own inbox: 619 email threads in two weeks, 61 needed me, 396 were pure noise.

## 1. Connect Gmail (once, ~30 s)
claude.ai → Customize → Connectors → Gmail → Connect. It works on the free plan too.

## 2. Change this setting first
In the same Gmail connector page, every tool has three options: **Always allow / Needs approval / Block**.
Set these to **Block**:
- Send email message, Reply to email, Forward email
- Move message to Trash, Move thread to Trash
- Apply sensitive label (Trash or Spam), message and thread
- Delete draft email, Delete label

Leave "Add labels" on **Needs approval**, so Claude asks before it labels anything.

## 3. The prompt
Replace the three goals with yours.

```
Go through every email in my Gmail inbox from the last 14 days.

My three goals this month:
1) <goal 1, e.g. land a new job: recruiters, interviews, replies to applications>
2) <goal 2, e.g. deliver my client project on time>
3) <goal 3, e.g. grow my Instagram account>

Anything from a bank, a court, a tax office, or anything with an invoice always counts as NEEDS ME.

Sort every email into exactly one of three piles:
- NEEDS ME: I have to act or reply this week, or it moves one of my goals.
- READ LATER: useful, but no action needed.
- NOISE: newsletters, promos and notifications I won't miss.

Do not delete, archive or label anything yet. First show me:
1) how many emails you checked and the count in each pile,
2) a table of every NEEDS ME email with sender, subject and one line on why,
3) the NOISE senders grouped, with a count for each.

Only after I say "go", add the label AI-noise to the NOISE pile. Never delete anything.
```

Then open the `AI-noise` label in Gmail, glance at it, select all and press **Archive**. Archived is not deleted: everything stays in All Mail.

## Bonus: the same filter for X and Instagram
Instead of scrolling, ask an assistant that can search the platform (Grok for X, or Claude/ChatGPT with web search):

```
My goals this month: <goal 1>, <goal 2>, <goal 3>.
Find 5 people on <X / Instagram> who post useful, practical things about <topic> right now.
Skip anyone who mostly reposts, sells a course in every post, or posts engagement bait.
For each: handle, why they're worth following (one line), and one recent post that shows it.
```

---
Made for the @aipractically reel "Stop scrolling. Make AI your filter." Tested 01.11.2026 on claude.ai (Opus 5.5) with the Gmail connector.
