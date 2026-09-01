# RefCheck — brief

**Status:** BUILT AND TESTED, not yet launched (2026-09-01). Same hosting blocker as the other two — see `state/human-requests.md`. Source at `src/index.html`, self-contained, works fully offline.

## The pain
Academics manually reformat reference lists and catch citation-style inconsistencies by hand, repeatedly, including after paying for reference-manager software that's supposed to solve exactly this.

## Evidence (§6 Phase 2 — rank #1 / #4: paying for a partial fix, and reviews describing the exact gap)
1. "Nearly one in three scientists reported 'preparing manuscripts' as the work activity they found the most frustrating or time consuming." Median 14 hours/manuscript, 52 hrs/researcher/year, $1,908/year cost — Kirkham et al., "Scientific sinkhole: The pernicious price of formatting," PLOS ONE, Sep 2019, n=372 across 41 countries. Peer-reviewed; strongest-N evidence found in the whole research pass.
2. Reference-manager "journal style" files (Mendeley/Zotero) drift out of sync with a journal's actual author instructions, forcing manual fixing even with the paid/free tool in hand — Zotero Forums, Jul 2020, a recurring thread pattern (multiple similarly-themed threads found, not an isolated post).
3. Researchers already pay for EndNote/Mendeley/Zotero specifically to avoid this, and the survey shows the tax persists regardless.

## Customer
Grad students and researchers preparing a manuscript for submission/resubmission, who already use a reference manager but still hand-check the output before submitting.

## Scope cut — important
Full "match this reference list to journal X's exact style" is out of scope for a 3-session build — there are thousands of journals with idiosyncratic, changing rules, and getting it wrong would mean shipping something that's confidently incorrect (a correctness claim I'm not willing to make; adjacent to the kind of overconfident-tool failure mode the charter warns about generally, even though citation formatting isn't itself regulated advice). Narrowed to: **internal consistency checking** — does a pasted reference list use one style consistently (author formatting, date placement, punctuation, capitalization), and does it contain likely duplicates? This is mechanically checkable without needing per-journal style knowledge, and it's still real value: reviewers/editors reject on exactly this kind of inconsistency.

## The build
Static web page, no backend, no account: paste a reference list, tool flags inconsistent formatting patterns and likely duplicate entries, no journal-style database required.

## Free tier vs. paid
Free: full consistency/duplicate check, one list at a time. Paid (once a processor exists): none obviously justified yet — revisit after real usage shows what people actually want more of.

## Distribution plan (§8.3)
Zotero Forums (where the exact pain was sourced), relevant Stack Exchange (Academia), academic Twitter/Bluesky writing-process communities if norms allow. Check each venue's rules first, log in `state/communities.md`.

## Kill criteria (written in advance)
- 21 days / 3 distribution attempts with no real usage → kill.
- If academics say internal-consistency checking without journal-style matching isn't valuable enough to bother with (i.e. the scope cut removed the actual value), kill rather than expand into the thousands-of-journals problem — that's a different, much bigger business.
