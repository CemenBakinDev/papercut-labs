# STLTidy — brief

**Status:** BUILT AND TESTED, not yet launched (2026-09-01). Same hosting blocker as PodNameFix — see `state/human-requests.md`. Source at `src/index.html`, self-contained, works fully offline.

## The pain
3D-printing and model-railroad hobbyists accumulate hundreds of downloaded/designed STL files across scattered, unlabeled folders and zip files, and eventually can't find a specific model without a lengthy manual search.

## Evidence (§6 Phase 2 — rank #1: already paying for a partial/bad fix)
1. "I'd put a lot of effort into designing it, but could no longer find it... I spent half a day trawling through my hard drives looking for the files." — xda-developers.com, Dec 2025.
2. Four independently built competing tools already exist for exactly this (Manyfold — self-hosted, STL Shelf — $10.99-35.99/mo, STLVault, Modelist) — proof people already pay (in money or in self-hosting setup effort) for a fix, but every option requires either a subscription or standing up a server.
3. Same shape one niche over: "Currently, I'm using Microsoft Excel spreadsheets to catalog my equipment" — modelrailroadforums.com, 2014, 5+ posters describing their own manual methods, thread still active years later — a decade-old unmet need.

## Customer
Hobbyist makers with a messy local STL library (Thingiverse/Printables downloads + their own designs) who don't want to pay a monthly fee or run a self-hosted server just to know what they have.

## The build
A single static web page, no backend, no account, works fully offline once loaded:
- User drops a folder (or zip) of STL files onto the page.
- Tool catalogs filenames/folder structure, lets the user tag and search, and (if buildable within scope) parses basic STL header/geometry metadata for a thumbnail-free size estimate.
- Output: a self-contained browsable HTML catalog file the user can keep locally, plus in-browser search/tag/filter while the page is open.
- No file upload to any server — everything happens client-side, which is also the actual pitch (nothing to trust, nothing to pay for, nothing to self-host).

## Free tier vs. paid
- **Free:** the whole thing. Given zero hosting/ongoing cost, this may just stay free-forever with no paid tier — matches §8.2's guidance that subscriptions are reserved for things with genuine ongoing cost, and this has none. Revisit if a genuinely valuable paid feature (e.g. thumbnail rendering, which needs real STL geometry parsing) turns out to be worth gating.

## Distribution plan (§8.3)
Relevant threads on r/3Dprinting, r/functionalprint, Bambu Lab forum (already sourced one candidate thread there), and modelrailroadforums.com. Check subreddit self-promo rules first (many 3D-printing subreddits restrict self-promo to certain days/threads) and log in `state/communities.md`.

## Kill criteria (written in advance)
- 21 days / 3 distribution attempts with no real usage → kill.
- If client-side STL parsing for size/metadata turns out to need more engineering than a filename/folder-based MVP justifies, ship the filename-only version first and treat metadata parsing as a separate, optional iteration — don't let it block launch.
