# ⚠️ SCT-restored build context

This `8.6/` build context (Dockerfile + `prebuildfs` + `rootfs`) was **restored by SCT** from
this fork's own git history. Upstream Bitnami deleted it in commit
`abfbafcc7e4` ("redis 8.8 is the new latest branch", 2026-05-26) as part of its "latest-only"
policy, which broke our self-build CI (`No Dockerfiles found for redis-cluster`).

- Restored from: `abfbafcc7e4~1` (`cf1ba4ce234`, redis-cluster 8.6.3-debian-12-r3).
- Build inputs verified reachable on restore date (2026-06-01): `docker.io/bitnami/minideb:bookworm`
  and the `redis-8.6.3` / `wait-for-port` stacksmith tarballs all resolve.
- **This is a stopgap.** redis-cluster is the forcing function to migrate off Bitnami images
  (see INF ticket under epic INP-493). Treat this as temporary until that migration lands.
- Future upstream syncs will not re-delete this path (upstream no longer modifies it), so no merge
  guard is required; if upstream ever re-adds a redis-cluster build context, reconcile then.
