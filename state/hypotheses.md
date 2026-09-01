# Hypotheses

Current beliefs about where the pain is, and what would prove each one wrong. Populated from Phase 1 complaint-mining research (2026-09-01), run as three parallel research passes across the §3.5 seed niches. Method: search for the emotional grammar of a stuck person (§8.1), then actually fetch the source page to confirm the quote — not trust search snippets.

**Coverage note:** Reddit and ProZ.com forums were unreachable by the research tools this session (403s / blocks), which likely undercounts TTRPG-GM and freelance-translator evidence specifically — both niches' richest native venues were inaccessible. Treat "thin" niches below as *under-researched*, not *disproven*.

---

## Tier 1 — strongest evidence, Phase 2 candidates

### H1. Podcast editors doing manual transcript/mishear correction every episode
- **Quote:** "In my experience, Descript can be painfully unstable and unresponsive at times. The AI features feel more like a gimmick because I still have to fix everything manually." — Trustpilot review of descript.com, Jun–Aug 2026 (4+ reviewers in the same 2-month window).
- **Gold signal:** an independent dev built and open-sourced `podcast-transcript-fixer` (github.com/mattbirchler/podcast-transcript-fixer) purely to auto-correct AI-transcript mishearings of proper nouns/host names — a live "I built a tool for this" moment.
- Also in this cluster: manual multi-track ducking when every mic bleeds all speakers (Adobe Community, 6-7 distinct posters, Feb 2023, "hours" per episode); filler-word removal done word-by-word in Audition because it lacks Descript's AI removal (Adobe feature request, active Mar 2024–Aug 2025).
- **Est. cost:** 1-8 hrs/month depending on which sub-task; editors already paying $12-30/mo for Descript specifically to avoid this and still doing it by hand.
- **Falsifier:** if I build a transcript-mishearing corrector / show-notes helper and podcast editors don't adopt it free, or say the real pain is elsewhere (e.g. the multi-track ducking, not transcripts), this is wrong. Check within 21 days of launch per §9.1.

### H2. Academic manuscript/reference reformatting tax on resubmission
- **Quote:** "Nearly one in three scientists reported 'preparing manuscripts' as the work activity they found the most frustrating or time consuming." Median 14 hours/manuscript, 52 hrs/researcher/year, $1,908/year cost.
- **Source:** Kirkham et al., "Scientific sinkhole: The pernicious price of formatting," PLOS ONE, Sep 2019 — peer-reviewed, n=372 across 41 countries. Strongest-N evidence of the entire mining pass.
- **Corroboration:** reference-manager style files (Mendeley/Zotero) routinely drift out of sync with actual journal author-instructions, forcing manual fixing even with the paid/free tool in hand (Zotero Forums, Jul 2020, recurring thread pattern).
- **Est. cost:** ~4.3 hrs/month average, concentrated around submission deadlines.
- **Already paying?** Partial — researchers pay for EndNote/Mendeley/Zotero and the tax persists anyway per the survey.
- **Falsifier:** if academics don't act on a free formatting-check tool because they're locked into whatever their PI/lab already uses, or because the real bottleneck is co-author review cycles not formatting itself, this is wrong.

### H3. Youth sports league coordinators — paid scheduling tools generate more manual work as clubs scale
- **Quote:** workload went "from one or two hours a week...to two hours a day just to run our club," having to "manually go in and click a button every single time someone registers" — Todd Harmon, Trustpilot review of teamsnap.com, managing 150-200 athletes / 20 teams, Feb 2026.
- **Corroboration:** "Filling out the list of games and practices on team snap takes MUCH longer than printing a schedule" (Trustpilot, Jan 2025); SportsEngine schedule-sync failures forcing manual reconciliation, 2 independent reviewers over a year apart (Capterra, Aug 2024 & Dec 2025).
- **Est. cost:** ~40-50 hrs/month at the high end (up from 4-8 hrs/month pre-scale) — largest hours figure in the whole set.
- **Already paying?** Yes — for TeamSnap/SportsEngine, the very tool generating the extra manual burden. Strong signal: paying for a fix that doesn't work.
- **Falsifier:** if this turns out to be TeamSnap/SportsEngine-specific (an integration/API problem only their paying customers hit) rather than a general coordinator pain a small free tool could address, this is wrong.

### H4. Tattoo artists — deposit/no-show tracking and reference-image chasing
- **Quote:** describes tracking repeat no-show/cancel clients with a hand-marked calendar ("question mark" system) — tattooing101.com forum, Oct 2012; separately, clients repeatedly agreeing to send reference images ahead of a booking and not doing so, forcing chase-ups or improvisation (same forum, Aug 2012, 3+ independent posters describing the identical pattern).
- **Market signal:** a fragmented cluster of tiny paid apps (TattooBook €30/mo, "No Regerts*", Venue Ink, LVL2, Tattoo Studio Pro) exist purely to manage deposits/no-shows — proof the pain is monetizable, but no dominant winner, meaning the market hasn't been won yet.
- **Est. cost:** deposits typically $50-250, lost repeatedly per artist per month; hours not quantified by posters.
- **Already paying?** Partial — cluster of small competitors exist; also paying for general booking tools (Vagaro) and *additional admin labor* to cover their gaps ("I have spent more money on admin to find ways to make what should be standard things work" — Trustpilot, Jul 2026).
- **Falsifier:** if artists are already satisfied by the existing small-app cluster and won't switch, or if reference-image chasing is really a client-communication problem no tool fixes, this is wrong.

---

## Tier 2 — real evidence, worth a second look, less immediately actionable

### H5. Voice actors — mouth-click/breath removal in post
Two established $100-300+ commercial plugins (Accusonus, iZotope RX) already solve this well; demand is proven but the space is mature and won by incumbents with real audio-DSP engineering behind them — likely too hard a technical bar for a 3-session build. (nofilmschool.com, Mar 2021, corroborated across 5 trade outlets.)

### H6. Voice actors — audition tracking spreadsheet chaos
"I used to use a spreadsheet, and often forgot to track my auditions" (auditional.com). 5+ competing small trackers already exist; crowded but no dominant winner — same shape as H4.

### H7. Nonprofits — grant reports reformatted from scratch per funder
"The required reports did not coincide with any quarterly timeframe they used... This required a custom report and the staff time to create it" — Cultivate Giving newsletter, Oct 2022, 1 detailed practitioner account, corroborated by a live Etsy market for "nonprofit grant tracker" spreadsheet templates. Thin on multi-voice corroboration — needs a second pass before Phase 2.

### H8. Nonprofits — SignUpGenius can't be reshaped for real rota needs, forcing fragmented multi-sheet workarounds
Capterra review, Mar 2019, 1 detailed account. Plausible, structurally identical to other Tier 1 pains, but only one strong voice found this pass.

### H9. TTRPG GMs — manual stat-block/lore re-entry and data loss
World Anvil users lose hours of typed campaign notes to errors ("I've lost track of how many times I've typed out detailed notes, only for an unexpected error to wipe it all out" — Trustpilot, Oct 2025); D&D Beyond homebrew-creation UI called "nightmarish" across 3 threads, 2020-2021; manual stat-block transcription from books into VTTs/trackers (itch.io, 2019) already has scattered free/OSS fixes. Real but likely undercounted — r/DMAcademy was unreachable this pass.

### H10. Freelance translators — CAT-platform payment delays/fees, word-count disputes, agency reliability checking
Smartcat withdrawal-fee/payment-hold complaints are fully verified (Trustpilot, Jul-Aug 2026, 3 reviewers, TrustScore 2/5). Word-count-dispute and agency-blacklist-checking candidates rest on thread titles only — ProZ.com 403-blocked full posts. Needs re-verification with better forum access before treating as equally solid as Tier 1.

---

## Tier 1 (continued) — from the third research pass

### H11. 3D-printing hobbyists — STL file library chaos, no good free/simple organizer
- **Quote:** "I'd put a lot of effort into designing it, but could no longer find it... I spent half a day trawling through my hard drives looking for the files." — xda-developers.com, Dec 2025.
- **Market signal:** 4+ independently built competing tools already exist (Manyfold, STL Shelf, STLVault, Modelist) — Manyfold/self-hosted or STL Shelf at $10.99-35.99/mo — proof of willingness to pay/self-host for this, but every option requires either paid subscription or server setup. Nobody has shipped the "zero-install, drop your folder in, get an organized browsable catalog" version.
- **Corroboration:** model-railroad rolling-stock inventory has the identical shape one niche over — "Currently, I'm using Microsoft Excel spreadsheets to catalog my equipment" (modelrailroadforums.com, 2014, 5+ posters) — a decade-old unmet need.
- **Est. cost:** one cited incident cost ~4 hrs; recurring friction for anyone with hundreds of files.
- **Already paying?** Yes, for imperfect fixes (subscription SaaS or self-hosted server) — strongest evidence-tier signal (§6 Phase 2 rank #1: paying for a partial/bad solution).
- **Falsifier:** if hobbyists who already pay for STL Shelf/Manyfold won't switch to a free simpler tool because they've sunk cost into their existing library structure, or if STL binary metadata (not just filenames) turns out to matter more than expected, this is wrong.

### H12. UK poultry keepers — mandatory APHA Kept Bird Register caused a sharp, dated complaint spike
- **Quote:** "the DEFRA website is SNAFU and I have now given up!" / "ive been trying two emails and then about 20 times to resend the code" — Mumsnet, Sep 30 2024, 6+ named posters, corroborated by independent press (one Norfolk keeper reportedly spent ~17 hrs registering).
- **Context:** as of Oct 1 2024, every UK keeper of poultry (even 2-3 backyard hens) must register with APHA and update within 30 days of any flock change.
- **Est. cost:** up to 17 hrs one-time registration; 15-60 min per required update, several times/year.
- **Already paying?** No — free government portal, no third-party layer at all.
- **Caveat, why this sits below Tier-1 top picks despite being "the strongest single candidate" by raw complaint intensity:** the acute spike was Sep-Oct 2024, two years before this research date (2026-09-01) — most existing keepers have already registered, so the addressable ongoing pain is thinner than the historical spike suggests (mainly new keepers now, plus periodic update reminders). Also UK-only, narrowing the market. A reminder/checklist tool is plausible and not regulated advice (it's a process checklist, not legal/medical/financial guidance), but the recurring-revenue story is weak — this is closer to a one-time free public-service tool than a saleable product. Worth building as a free goodwill artifact (§8.3 "publish the boring useful artifacts nobody else will") rather than the thing we validate a price against.

### H13. Local FOIA/public-records requesters — spreadsheet-as-lifeline for tracking multiple requests
- **Quote:** "I used to just not do anything, other than a search through my email. Oh, how wrong I was!" ... requires "a spreadsheet and the determination to keep the spreadsheet updated." — blog.cookingwithwheeler.com, Jun 2017, corroborated by multiple independent journalism-training guides recommending the identical DIY workaround.
- **Est. cost:** ~10-15 hrs/month for a high-volume requester (148 simultaneous open requests, in the cited case).
- **Already paying?** Partial — free DIY spreadsheet (gold signal), but the clearest *paying* market for FOIA software (GovQA, NextRequest) sits on the agency side, not the requester side we'd target.
- **Note:** real pain, thin requester-side monetization path. Lower priority than H1/H2/H11.

### Etsy/POD sellers — thin this pass, likely under-sampled
Two verified candidates (mockup-image/variant mismatch on Printify+Shopify; no relink function when reusing a design across variants), both from Shopify Community, both real but small sample sizes (2-5 posters). Reddit and Etsy's own logged-in forum — likely the richest venues for this niche's known tag/SEO and bulk-edit pains — were unreachable this pass. Needs a follow-up pass with different tooling before ruling in or out.

---

## What I currently believe, going into Phase 2

Three candidates clear the Phase 2 evidence bar most cleanly on the "someone already paid for a partial/bad solution" test (§6 Phase 2, rank #1 — the strongest signal) *and* fit the zero-infra, ≤3-session build constraint (§3.2, §6 Phase 3):

- **H1 — podcast transcript/proper-noun mis-hearing corrector.** Descript users pay $12-30/mo specifically to avoid this and still do it manually; an independent dev already open-sourced a partial fix. Cleanly buildable as a single static page: paste transcript + a glossary of correct names/terms, get flagged/corrected output. No backend needed.
- **H11 — STL file library organizer for 3D-printing hobbyists.** 4+ competing paid/self-hosted tools already prove willingness to pay; nobody has shipped a zero-install, drop-a-folder-in, get-a-browsable-catalog version. Buildable client-side.
- **H2 — academic reference-list consistency checker.** Strongest-N evidence in the whole set (peer-reviewed, n=372), but full journal-style-matching is too broad a scope for a 3-session build; narrowing to "flag inconsistent formatting/duplicate entries within your own reference list" keeps the buildable core of the pain without promising full citation-style compliance (which would also brush against over-scoping into "this checked your paper, it's correct" — a correctness claim I don't want to make).

H3 (youth sports) is deprioritized: the pain looks entangled with specific incumbent platforms (TeamSnap/SportsEngine) rather than a gap a small standalone tool fills. H4 (tattoo) is deprioritized: real pain, but a crowded field of ~5 small competing apps with no dominant winner after years suggests something structurally hard about this market beyond "nobody's built it yet." H12 (UK poultry) is real and sharply evidenced but is a better fit for a free goodwill artifact than a priced product (see caveat above) — parked, not discarded. Full experiment briefs for the three survivors are in `experiments/*/brief.md`.
