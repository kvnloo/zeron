<!-- oss-factory:v1
{"id":"20261016-zeron-canonical-promotion-owner","kind":"state","project":"zeron","from":"chatgpt","to":["factory"],"status":"working","dedupe_key":"promotion-queue:zeronsh/zeron","civ":{"city_id":"oss:zeron"}}
-->

# Zeron · single upstream-promotion queue

**Source:** [zeronsh/zeron](https://github.com/zeronsh/zeron). **Writable coordination fork:** [kvnloo/zeron](https://github.com/kvnloo/zeron). Issues are disabled on the fork, so this **single fork-owned document and its draft PR** replace the old factory-hosted issue [#140](https://github.com/kvnloo/oss-factory/issues/140). Keep implementation reviews, tests and credit in original PRs; update the **promotion status here**. The factory [#14](https://github.com/kvnloo/oss-factory/issues/14) is just a repository directory.

Snapshot: October 16, 2026. No new candidate has independently passed native CI or obtained upstream publication approval.

| Origin / original credit | Existing implementation / exact head | Disposition and next gate |
| --- | --- | --- |
| [#892 macOS Markdown link-range crash](https://github.com/zeronsh/zeron/issues/892), reported and source-isolated by **jsgrrchg** | [Fork draft #1](https://github.com/kvnloo/zeron/pull/1), `fix/markdown-link-label-range-892`, `172732fd8c8ddf57bd1209611820da3122046540` | **LIMITED.** Checked string slicing and tests drafted. Run `cargo test --locked -p zeron-ui --lib`, formatting/Clippy and actual UI reproduction. **NOT RUN / no CI**. No upstream PR yet. |
| [#905 Loro panic permanently poisons chat sync](https://github.com/zeronsh/zeron/issues/905), production failure documented by **woosal1337** | [Fork draft #2](https://github.com/kvnloo/zeron/pull/2), `fix/chat-snapshot-panic-loop-905`, `829c64388958ae76746c9bbf90e0b47ce4f4c8d4` | **LIMITED.** One-file fail-closed worker panic guard and injected-panic regression drafted. Run `cargo test --locked -p zeron-engine panicked_snapshot_stops_retries_without_acknowledging_dirty_data`, adjacent suite, fmt/Clippy, CI. **NOT RUN**. Stops panic retries, **does not recover sync or repair Loro**. |
| [#893 failed subagent spawn remains running](https://github.com/zeronsh/zeron/issues/893) | Existing [katulevskiy origin PR #769](https://github.com/zeronsh/zeron/pull/769) | **ORIGIN_LIVE / OWNER_COVERED.** Support current author review/CI; do not duplicate. |
| [#915 Claude-in-Chrome](https://github.com/zeronsh/zeron/issues/915) | Existing [katulevskiy origin PR #928](https://github.com/zeronsh/zeron/pull/928), stacked on [#926](https://github.com/zeronsh/zeron/pull/926) and [#927](https://github.com/zeronsh/zeron/pull/927) | **ORIGIN_LIVE / SECURITY REVIEW.** Existing Claude control handler automatically approves non-question tool requests; a per-device Chrome toggle can expose signed-in browser actions. Resolve the permission/consent boundary on the owner's PR; no competing patch, no live exploit claimed. |

## Promotion rule

Review current owner feedback and CI first. For each **unique** change: record supported user requirement separately from tests, current source and fork SHAs, actual native checks and limitations, overlaps, policy, original contributor credit, and explicit scoped human approval. `READY` does **not** itself grant origin-write permission. When published, link the existing/new origin PR; when merged, record the actual merge SHA. Never merge an upstream default branch or issue unsupported impact claims.

This queue is a downstream work index only; all implementation is in original source PR branches. The Zeron registration proposal [factory #129](https://github.com/kvnloo/oss-factory/pull/129) is still under review and not assumed merged.
