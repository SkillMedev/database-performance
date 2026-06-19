# Database Performance & Administration

**Make slow queries fast and keep your database healthy under load.** — built in-house by [Skill&nbsp;Me](https://skillme.dev).

The DBA-grade toolkit backend engineers actually reach for: hunt N+1s, read EXPLAIN plans, advise indexes, rewrite pathological SQL, plan partitioning, tune connection pools, ship zero-downtime migrations, and debug replica lag. Built around verifiable, EXPLAIN-checkable work, not folklore.

⭐ **If this is useful, star the repo** — it's how we gauge what to build next.

## Install

- **From the catalog:** [skillme.dev/pack/database-performance](https://skillme.dev/pack/database-performance) — install the whole pack into Claude in one step.
- **With the skills CLI:** `npx skills add aouellets/database-performance`
- **Manually:** copy any `skills/<slug>/SKILL.md` into your Claude skills directory.

## Skills in this pack

- **[N+1 Query Hunter](skills/n-plus-one-hunter/SKILL.md)** — Finds and eliminates N+1 query patterns in ORM code (ActiveRecord, Prisma, SQLAlchemy, Hibernate) using eager loading, with judgment on when N+1 is acceptable; use when a request issues many similar queries, a list endpoint is slow, or query logs show repeated SELECTs in a loop.
- **[EXPLAIN Plan Reader](skills/explain-plan-reader/SKILL.md)** — Interprets Postgres and MySQL EXPLAIN ANALYZE output to pinpoint the bottleneck node — seq scans, bad row estimates, expensive sorts and joins — and prescribes a fix for each; use when a query is slow and you have or can capture its execution plan.
- **[Index Advisor](skills/index-advisor/SKILL.md)** — Recommends, orders, and removes indexes for a given slow query and schema — composite column order, partial and covering indexes, duplicate and unused index cleanup, and write-cost tradeoffs; use when a query needs an index, or when auditing a table's index set for bloat.
- **[SQL Query Rewriter](skills/query-rewriter/SKILL.md)** — Refactors slow SQL into efficient equivalents — correlated subqueries to joins, accidental cross joins, OR conditions to UNION, SELECT * to explicit columns, and OFFSET pagination to keyset; use when a query is structurally inefficient regardless of indexing.
- **[Table Partition Planner](skills/partition-planner/SKILL.md)** — Designs partitioning and sharding for a large table — range, list, or hash strategy, partition key choice, and the operational pitfalls — and decides when not to partition at all; use when a single table is too large to manage, vacuum, or query efficiently.
- **[Connection Pool Tuner](skills/connection-pool-tuner/SKILL.md)** — Diagnoses connection pool exhaustion and sets correct pool sizes and timeouts across app pools and PgBouncer, including serverless connection storms; use when you see connection-limit errors, checkout timeouts, or idle-connection pile-up.
- **[Migration Safety Checker](skills/migration-safety-checker/SKILL.md)** — Flags schema migrations that take blocking locks or run long, and rewrites them into zero-downtime steps — nullable-add-then-backfill, concurrent index builds, and expand-contract; use before running any ALTER TABLE or migration against a live production database.
- **[Replication Lag Debugger](skills/replication-lag-debugger/SKILL.md)** — Diagnoses read-replica lag and the stale-read bugs it causes, and applies read-after-write consistency strategies; use when reads return data older than a just-committed write, or when monitoring shows replica lag growing.
- **[SQL Query Optimizer](skills/sql-query-optimizer/SKILL.md)** — Explains and rewrites slow queries with index recommendations and execution-plan reasoning.
- **[Database Schema Designer](skills/database-schema/SKILL.md)** — Designs normalized relational schemas with indexes, constraints, and migration strategies.

## License

MIT — see [LICENSE](LICENSE). Skills are portable `SKILL.md` files; the canonical
copies live in the [Skill&nbsp;Me catalog](https://skillme.dev).
