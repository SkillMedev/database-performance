# Database Performance & Administration

**For backend engineers: make slow queries fast and keep production Postgres healthy.** — built in-house by [Skill&nbsp;Me](https://skillme.dev).

Reach for this when a production database is slow or strained and you need a verifiable fix, not folklore. It walks the real diagnose-to-resolve path: catch N+1s in your ORM, read an EXPLAIN plan down to the bottleneck node, advise the right index, rewrite pathological SQL, decide when to partition, size connection pools, ship migrations with zero-downtime locking, and chase down stale reads from replica lag. Every fix is EXPLAIN-checkable, so you ship the change knowing it actually moved the number.

⭐ **If this is useful, star the repo** — it's how we gauge what to build next.

## Install

- **From the catalog:** [skillme.dev/pack/database-performance](https://skillme.dev/pack/database-performance) — install the whole pack into Claude in one step.
- **With the skills CLI:** `npx skills add aouellets/database-performance`
- **Manually:** copy any `skills/<slug>/SKILL.md` into your Claude skills directory.

## Skills in this pack

- **[N+1 Query Hunter](skills/n-plus-one-hunter/SKILL.md)** — Detect ORM loop-of-queries (N+1) patterns from query logs and eliminate them with batched eager loading, keeping the N+1s that are cheap.
- **[EXPLAIN Plan Reader](skills/explain-plan-reader/SKILL.md)** — Read a captured EXPLAIN ANALYZE plan, name the single bottleneck node, and prescribe a targeted fix for it.
- **[Index Advisor](skills/index-advisor/SKILL.md)** — Recommends, orders, and prunes indexes for a specific query or table — composite column order, partial and covering indexes, duplicate/unused cleanup, and write-cost tradeoffs.
- **[SQL Query Rewriter](skills/query-rewriter/SKILL.md)** — Rewrites a structurally inefficient SQL query into a faster equivalent that returns byte-identical results — correlated subqueries to joins or LATERAL, accidental cross joins to explicit ON predicates, OR-across-columns to UNION, SELECT * to projected columns, and deep OFFSET pagination to keyset.
- **[Table Partition Planner](skills/partition-planner/SKILL.md)** — Produces a partitioning or sharding plan for an oversized table — range/list/hash strategy, partition-key choice, composite-key and pruning constraints, and a verdict on whether to partition at all.
- **[Connection Pool Tuner](skills/connection-pool-tuner/SKILL.md)** — Diagnoses connection pool exhaustion from captured evidence and sets correct pool sizes and timeouts across app pools and PgBouncer.
- **[Migration Safety Checker](skills/migration-safety-checker/SKILL.md)** — Rewrite a schema migration into independently deployable, zero-downtime steps that never take a long-held blocking lock on a live table.
- **[Replication Lag Debugger](skills/replication-lag-debugger/SKILL.md)** — Diagnoses read-replica lag and the stale-read bugs it causes, then applies read-after-write consistency strategies to fix them.

## License

MIT — see [LICENSE](LICENSE). Skills are portable `SKILL.md` files; the canonical
copies live in the [Skill&nbsp;Me catalog](https://skillme.dev).
