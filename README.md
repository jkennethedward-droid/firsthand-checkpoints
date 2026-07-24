# firsthand-checkpoints

Public, append-only anchors of the Firsthand `audit_log` hash chain.

This is **not** the product codebase. Each file under `checkpoints/` is a
JSON tip snapshot `{ seq, payload_hash, prev_hash, created_at }` committed
by the Firsthand API on a short interval (Certificate Transparency seed —
technical skeleton §14).

Anyone can fetch these without credentials. Verifying a tip means recomputing
the chain in Postgres (or an export) and checking that `payload_hash` /
`prev_hash` match an anchored file.