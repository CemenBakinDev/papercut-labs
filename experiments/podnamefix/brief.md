# PodNameFix — brief

**Status:** BUILT AND TESTED, not yet launched (2026-09-01). Blocked on having a place to host it publicly — see `state/human-requests.md`. Source at `src/index.html`, a single self-contained file, works fully offline once loaded.

## The pain
Podcast editors correct AI-transcript mis-hearings of proper nouns (guest names, brand names, recurring jargon) by hand, every episode, even when already paying for a transcription tool. It's boring, repetitive, and the same wrong words tend to get mis-heard the same way episode after episode.

## Evidence (§6 Phase 2 — rank #1: already paying for a partial/bad fix)
1. "In my experience, Descript can be painfully unstable and unresponsive at times. The AI features feel more like a gimmick because I still have to fix everything manually." — Trustpilot review of descript.com, Jun–Aug 2026 (4+ reviewers in a 2-month window). Descript is a paid product ($12-30/mo) bought specifically to avoid manual transcript work.
2. An independent developer built and open-sourced `podcast-transcript-fixer` (github.com/mattbirchler/podcast-transcript-fixer) specifically to auto-correct AI mis-hearings of proper nouns/host names — the §8.1 "I built a tool for this" gold signal.
3. "one of the most boring and time consuming tasks is to remove the uhmms and aaahhs one by one in the waveform view" and adjacent complaints about manual correction work — Adobe Audition feature-request thread, active Mar 2024–Aug 2025, 3+ distinct commenters.

## Customer
Independent/small-team podcast editors and hosts who self-edit — specifically people using a transcription tool (Descript, Otter, Whisper-based tools) whose output still needs manual proper-noun cleanup. Not targeting big studio post houses.

## The build
A single static web page, no backend, no account:
- User pastes/uploads a transcript (plain text or SRT/VTT).
- User maintains a glossary of correct terms (guest names, recurring jargon) — persisted in browser localStorage, so it carries over between episodes of the same show without an account.
- Tool flags words in the transcript that are phonetically close to a glossary term but don't match exactly (fuzzy/phonetic matching — e.g. Soundex/Metaphone + edit distance), and lets the user batch-accept corrections.
- Output: corrected transcript, downloadable in the same format it came in (so SRT timing stays intact).

## Free tier vs. paid
- **Free:** everything above, one file at a time, glossary saved locally in-browser.
- **Later paid idea (not live yet — no payment processor exists per `state/human-requests.md` #1):** batch mode for multiple files at once. Not implemented until a processor exists; free tier ships complete and useful on its own regardless.

## Pricing (when payment exists)
$19-29 one-time for batch mode, per §8.2 ladder (one-time beats subscription below $50, and there's no ongoing hosting cost to justify a subscription).

## Distribution plan (§8.3)
Reply to the actual Adobe Community / relevant threads found during research, and post in the GitHub issue/discussion on `podcast-transcript-fixer` if appropriate, framed as "saw this problem, built a free web version, here it is" — not a launch post. Check each venue's self-promo rules first and log them in `state/communities.md` before posting.

## Kill criteria (written in advance, per §6 Phase 3)
- 21 days or 3 distribution attempts with no real usage (not views — actual people running a transcript through it) → kill, per §9.1.
- If, once used, editors report the phonetic-matching approach produces too many false positives/negatives to be trustworthy, and a fix isn't obvious within one iteration → kill rather than over-invest in NLP tuning (out of scope per §3.2 — no ML infra).
