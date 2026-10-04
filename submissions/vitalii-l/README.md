# Likedex — Agentic Engineering Capstone

## Author

Vitalii Levinton (GitHub: [vitali1024](https://github.com/vitali1024)).

## Project

Likedex is a Chrome extension that builds a local, read-only mirror of a user's YouTube Liked Videos for fast browsing, search, filtering, sorting, and details. Options and Side Panel browse the local mirror without querying YouTube for normal library interactions.

## Code

[Public Likedex repository](https://github.com/vitali1024/likedex) · [Submitted snapshot](https://github.com/vitali1024/likedex/tree/3ec9f5143df135ae194e98db9c5810274aec042a)

## Demo

Demo video: pending — link will be added to the submission PR.

## Agentic Engineering Evidence

| Practice | Evidence | What it demonstrates |
|---|---|---|
| Context engineering | [Committed AGENTS.md](https://github.com/vitali1024/likedex/blob/aa46ad8c8487d02a33965999943cec3212b489be/AGENTS.md); [human-approved gate amendment](https://github.com/vitali1024/likedex/commit/a70f972b6ca784cf4f457f58131188b19c2336a6); [runtime implementation](https://github.com/vitali1024/likedex/commit/826f546a86c67fa633df1bb9e2694eaf54709537) | Ownership and fail-closed pruning rules shaped implementation; production Sync waited for live evidence and explicit human approval. |
| Specifications before code (SDD) | [Initial spec commit](https://github.com/vitali1024/likedex/commit/aa46ad8c8487d02a33965999943cec3212b489be), before [scaffolding](https://github.com/vitali1024/likedex/commit/6ca6bc2861b4e23cf7d975b842c24633895a3bbe); [Phase 3 boundary amendment](https://github.com/vitali1024/likedex/commit/754fc5028fb6b251d600e07a0e5b3b66ca523c70) | Specs preceded code; preparation stopped when phase boundaries contradicted each other, and resumed after a human-approved amendment. |
| Verification | [RED pruning regression](https://github.com/vitali1024/likedex/commit/b02dd363897aa7ef08fbd0140026372ac885af8a); [GREEN implementation](https://github.com/vitali1024/likedex/commit/85745b4b217083ccbf970edc050586b77649ea04); [final command/output](https://github.com/vitali1024/likedex/blob/3ec9f5143df135ae194e98db9c5810274aec042a/docs/agentic/capstone-verification.md#final-agent-run-verification) | Safety regression before implementation; final `npm run verify` passed 541 unit tests and 13 Chromium tests, plus lint/types/build inspections. |
| Loop engineering | [Actual bounded sync loop](https://github.com/vitali1024/likedex/blob/85745b4b217083ccbf970edc050586b77649ea04/docs/agentic/loops/sync-loop.md) | First implementation: 55 failures from a refined-schema operation; narrow correction; second iteration: all 225 tests passed and the loop stopped. |

[Human-reported live smoke and scope limits](https://github.com/vitali1024/likedex/blob/3ec9f5143df135ae194e98db9c5810274aec042a/docs/agentic/capstone-verification.md#human-reported-live-results): 71 accepted pages, 3,547 mirrored memberships, approximately 3,403 available in primary browsing. No personal provider data is published.

No committed independent checker report was found, so maker ≠ checker is not claimed. Export/Clear/complete Disconnect controls, independent release review, exact-package acceptance, Store submission, and public OAuth verification remain unfinished.
