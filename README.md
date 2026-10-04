# Ariadys workflow portfolio

Eighteen n8n workflows I built and run for my own outbound system and practice labs. None is client work. This repo describes what each one does and what it does not do. It holds no workflow files, credentials or account IDs.

## Finding and checking emails

**Email finder.** Finds a business email by trying several finder services in order, then checks the address with a verifier. It finds some emails, not all. First version May 2026, reshaped over about three months. On a 25-lead test it found emails for 16, with a median machine time of 72 seconds over 13 runs.

**Website email scraper.** Opens a prospect's website and pulls a listed contact email. It does not guess addresses and does not verify them. Built May 2026.

**Email verification.** Re-checks each new address before sending and suppresses the ones that fail. It does not find emails. Built August 2026. A recent run checked 18 addresses: 14 valid, 4 suppressed.

## Lead data

**Lead sheet sync and de-duplication.** Merges new leads into one tracker sheet, skips duplicates and anyone on the unsubscribe list, and revives a dead lead with its next contact. It sends nothing. Built July 2026. A recent run merged 1,463 rows from 4 sources and added 50 new ones in 10 seconds.

**Sheet-to-sheet domain sync.** Copies newly added company domains from the tracker to the research sheet. It does not research them. Built July 2026.

**Clinic social-profile harvester.** Opens each clinic website and collects the clinic's and team members' Instagram and LinkedIn links with name and role. It messages no one. Built October 2026. One pass covered 690 domains in 34 minutes and wrote 1,466 rows.

## Writing and drafting

**AI icebreaker generator.** Reads a prospect's site, reviews and social pages and writes a personal opening line with a language model. If it finds nothing it flags "nothing found" and does not invent a fact. Built July 2026. A recent batch of 30 domains gave 23 icebreakers and 7 flags.

**Follow-up email drafter.** Picks who is due for the next touch and builds the draft from approved templates plus the icebreaker, then runs a quality gate. Rule-based, no language model. It sends nothing; a person approves every draft. Built July 2026. A recent run read 867 rows and built 244 drafts.

## Replies and safety

**Reply sorter and daily digest.** Reads replies and sorts them with keyword and regex rules (interested, not interested, opt-out, noise), then emails a digest. It is not AI classification. Built July 2026. It ran 320 inbox checks in 18.6 seconds.

**Bounce catcher.** Watches the inbox for bounce notices, marks the address as bounced in the tracker and adds it to the suppression list. Runs hourly. Built July 2026.

**One-click unsubscribe handler.** A web link in each email adds the person to the suppression list and stops their sequence. The endpoint is header-protected and refuses calls without the secret. It does not delete data. Built May 2026.

## Monitoring

**Error alert.** Fires on any workflow failure and posts the workflow name, failing step and error to a Discord channel. It does not retry or fix, and it does not catch every failure: nodes set to continue on error swallow theirs first. Built April 2026.

**Daily sheet backup.** Exports five tracked sheets and a suppression list to a private GitHub repository every day. It does not restore automatically. Built August 2026. Median run 15 seconds.

**Daily send reconciliation.** Counts sends against the send log each night, posts a weekly tally and flags mismatches. Built September 2026.

## Job alerts

**Freelance job-board alert.** Checks the n8n, Make and Bubble job boards every 10 minutes and posts new jobs to a channel with a reply draft and a speed rank. It does not apply to jobs. Built September 2026. It passed all 6 planned stress cases.

## Demos and practice labs

**Missed-call text-back (demo).** A form stands in for a missed call and the workflow texts the caller back through Telegram. A demo of the idea, not a live client system, and it uses no real SMS carrier. Built September 2026.

**Inbound AI reception (practice lab).** Reads a customer message on Telegram, classifies it, drafts a short reply with a language model and logs a lead if it is one. WhatsApp is not built yet. Built October 2026. In a stress run, 10 parallel messages all finished in under 3.4 seconds.

**Outbound prospecting pipeline (practice lab).** Picks a test lead, finds or checks its email, sends one email only to my own addresses, creates the lead in a CRM and logs each step. It has not run against real prospects. Mid-build, October 2026.

## Contact

Open to n8n and Make fixes and builds through Upwork.
