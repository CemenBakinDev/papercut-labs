# Decisions Log

Append-only. Never edit or delete history.

---

## [2026-09-01] Cold start — scaffolded Papercut Labs as its own repo
**Type:** strategy
**Decision:** Created `/home/icarus/papercut-labs/` as a dedicated git repo for this business, rather than putting `state/`, `experiments/`, etc. directly in `/home/icarus`. Copied `CHARTER.md` and `CONSTITUTION.md` in verbatim per §11 Session 1, initialized all state files with real (non-placeholder) content.
**Because:** The home directory already holds several unrelated live projects (leadbot, study-hub, time-heist, Blurt, course-promo). Mixing Papercut Labs' state files into that root would make `state/decisions.md`, `state/journal/`, etc. ambiguous about which project they belong to, and would make it harder to ever hand this repo a life of its own (its own remote, its own domain-adjacent tooling) later.
**Alternatives rejected:** Putting state/ directly under `/home/icarus` as the charter's literal repo-layout diagram implies — rejected because the diagram is illustrative of *what a Papercut Labs repo contains*, not an instruction to use the home directory itself as that repo.
**Falsifier:** If the Operator says they wanted this at `/home/icarus` root directly, or wanted it inside an existing project directory, this was the wrong call — cheap to fix, just `mv`.
**Reversibility:** cheap

---

## [2026-09-01] Phase 1→2: narrowed 13 researched candidates to 3 survivors
**Type:** strategy
**Decision:** Ran three parallel complaint-mining passes across all 12 §3.5 seed niches (plus whatever surfaced organically), producing 13 documented candidates in `state/hypotheses.md`. Applied the §6 Phase 2 evidence ranking (rank #1 = someone already paying for a partial/bad solution) crossed with the §3.2/§6 Phase 3 build constraint (ships in ≤3 sessions, no backend, no accounts). Three survive: H1 (podcast transcript/proper-noun corrector), H11 (STL file library organizer for 3D-printing hobbyists), H2-narrowed (academic reference-list consistency checker, scope-cut from full journal-style matching to internal-consistency checking).
**Because:** H1, H11, and H2 are the only candidates where evidence hits Phase 2 rank #1 (paying customers of an adjacent paid tool — Descript, STL Shelf/Manyfold, EndNote/Mendeley/Zotero — describe the exact pain persisting despite payment) AND the fix is a "check/transform a file against a spec" shape buildable as a static client-side page with zero ongoing infrastructure cost, matching my structural advantage (§3.2) and the maintenance-is-free argument for why an AI operator can win here.
**Alternatives rejected:** H3 (youth sports, TeamSnap/SportsEngine) — biggest hours-saved number in the whole set (~40-50 hrs/month) but the pain looks entangled with specific incumbent platform APIs/UX rather than a gap a standalone tool fills; would need real investigation of whether a third-party tool could even integrate before betting on it. H4 (tattoo deposits/no-shows) — real pain, narrow-customer story is clean, but ~5 small competing apps already exist with no dominant winner after years, suggesting a structural adoption problem (may be a market that resists tooling, e.g. because trust/personal-relationship dynamics matter more than software) rather than an open gap. H12 (UK poultry APHA registration) — sharply evidenced, dated regulatory spike, but the spike was Sep-Oct 2024 (two years stale) and the ongoing addressable pain is thin + UK-only + weak recurring-revenue shape; parked as a free goodwill artifact candidate, not a priced product. H13 (FOIA tracking) — real DIY-spreadsheet gold signal but the actual paying market (GovQA/NextRequest) is agency-side, not requester-side.
**Falsifier:** If, after building and shipping H1/H11/H2's free tiers into their respective complaint threads (§8.3), none get real usage within 21 days / 3 distribution attempts (§9.1), the "paying-for-a-partial-fix signal predicts a standalone-tool opportunity" belief is wrong, and the next cycle should weight rank #1 evidence less and investigate why (crowded market? wrong fix shape? distribution failure vs. product failure?).
**Reversibility:** cheap — no code written yet at decision time, briefs only.

---

## [2026-09-01] Built and tested PodNameFix (first shipped product)
**Type:** product
**Decision:** Built PodNameFix (`experiments/podnamefix/src/index.html`) — a single self-contained static HTML/JS page, no backend, no account, no external dependencies. User maintains a glossary of correct proper nouns/terms (saved to browser localStorage), pastes a transcript (plain text or SRT), and the tool flags words that are phonetically/edit-distance close to a glossary term but don't match exactly, lets the user accept/reject each, and outputs a corrected, downloadable transcript with formatting (including SRT timestamps) intact.
**Because:** H1 in `state/hypotheses.md` — Descript users pay $12-30/mo specifically to avoid this manual work and still do it by hand; an independent dev already open-sourced a partial fix, proving the mechanism is wanted. Verified the actual build works, not just that it compiles: wrote unit tests for the matching algorithm (Levenshtein + phonetic-key heuristic) covering true positives, exact-match suppression, and false-positive avoidance on common words, then ran a full Playwright browser test of the real UI flow (scan → accept → apply → download, plus an SRT-format round-trip). Testing caught one real bug: the localStorage autosave used a 400ms debounce with no immediate-save fallback, so a user who typed a glossary entry and clicked away within 400ms could lose it. Fixed by also saving on `blur` and `beforeunload`, verified by rerunning the failing test until it passed.
**Alternatives rejected:** Building STLTidy or RefCheck first instead — rejected per the Phase 2 narrowing decision above; PodNameFix judged marginally more differentiated (a genuinely free alternative to a paid tool's specific failure) and its build shape (text-in, text-out, single algorithm) was the most certain to fit in one session, leaving room to actually test it rather than just ship it.
**Falsifier:** stated in `experiments/podnamefix/brief.md` — 21 days / 3 distribution attempts with no real usage, or persistent false-positive/negative complaints with no easy fix, kills it.
**Reversibility:** cheap — static file, no infrastructure stood up yet, deletable/abandonable at zero cost.

---

## [2026-09-01] Identified the actual blocker to launch: no email inbox for the business
**Type:** strategy
**Decision:** Did not create any hosting or platform account (GitHub, Netlify, etc.) under the Operator's personal email without flagging it first. Filed a human-request instead (see `state/human-requests.md`) asking for a dedicated email alias for Papercut Labs account signups.
**Because:** Getting PodNameFix in front of real users (§Phase 4 LAUNCH) requires hosting it somewhere public, and essentially every free static-hosting option (GitHub Pages, Netlify, Cloudflare Pages, surge.sh) requires an account tied to *some* email inbox I can receive mail at. I don't have one. Using the Operator's personal email to sign up would tie a business-branded, publicly-posting account to their real inbox without them knowing — not explicitly listed as RED in §4, but it's the kind of thing §4's own test flags: "any decision you'd feel weird about the Operator reading in the log... that feeling is the trigger." A cheap email alias (2-minute setup, most providers support it free) resolves this cleanly without touching anything in §10.1's actual Operator-only list (banking, payment processors, domains, legal-identity accounts) — an alias isn't any of those.
**Alternatives rejected:** Proceeding to sign up for hosting using the Operator's real email anyway — rejected, see above. Waiting idly for a response before doing anything else — rejected; instead moved straight to Phase 1 research and Phase 3 build on the other two survivors' groundwork while this is pending, since it's genuinely non-blocking for everything except the actual public launch step.
**Falsifier:** if the Operator says "just use my email, I don't care," this caution was overcalibrated — cheap to correct, just proceed.
**Reversibility:** cheap — this is a request, not an action; nothing was done that needs undoing.

---

## [2026-09-01] Built and tested STLTidy (second shipped product)
**Type:** product
**Decision:** Built STLTidy (`experiments/stltidy/src/index.html`) — a single self-contained static HTML/JS page. User drops a folder of STL files in; the tool catalogs filenames, sizes, and (parsed directly from the binary STL header, no external library) triangle counts, lets the user tag/search, and exports a portable standalone HTML catalog file they can keep. All storage (tags) is browser localStorage, keyed by filename+size so re-selecting the same folder later restores prior tags.
**Because:** H11 in `state/hypotheses.md` — 4+ competing paid/self-hosted tools (Manyfold, STL Shelf, STLVault, Modelist) already prove people pay to solve this, but every option costs a subscription or a server; nothing ships as a genuinely free, zero-install, drop-a-folder-in tool. Built synthetic binary and ASCII STL test fixtures (Node script generating valid binary-STL headers with known triangle counts) and ran a full Playwright test: folder upload via a real directory path (not individual files — Playwright enforces this the same way a real browser's directory picker does), triangle-count parsing verified against known values (120 and 5,000 triangles came back exactly right), non-STL files correctly excluded, filename and tag search both verified, tag persistence verified by reloading the page and re-selecting the same folder, and the exported standalone catalog verified to load and search correctly on its own.
**One test-harness false alarm worth recording:** the exported-catalog test initially looked broken (blank page, no table) — turned out to be Playwright's `download.path()` stripping the `.html` extension from its temp copy, so Chromium served it as plain text instead of parsing it as HTML. Re-saved with `download.saveAs()` to a proper `.html` path and it worked correctly — confirms this was a test-tooling artifact, not a real bug (a real user's browser honors the `download="stl-catalog.html"` attribute correctly). Recording this so a future me doesn't waste time re-discovering the same false alarm, and because §13 says record what happened including the parts that turned out to be nothing.
**Alternatives rejected:** n/a — this was the second of the three pre-committed Phase 2 survivors, built per the queued order in the Phase 2 narrowing decision.
**Falsifier:** stated in `experiments/stltidy/brief.md` — 21 days / 3 distribution attempts with no real usage kills it.
**Reversibility:** cheap — static file, no infrastructure, deletable at zero cost.

---
