This is a backup of home lab tick scripts.

## Current status (as of 2026-09-04)

Live on the kapacitor container running on billdozer:

- `1x_deadman_batch` — **enabled**, the active host-liveness deadman check (per-host, low overhead — one `last()` query/host/minute).
- `1x_deadman` — **disabled**. Same purpose as `1x_deadman_batch` but processes the raw high-frequency `cpu` stream directly, much noisier for no added benefit now that `1x_deadman_batch`'s per-host alert identification is confirmed working. Kept in this repo for reference, not deployed.
- `disk_check`, `mem_check`, `swap_check`, `docker_restart_check` — enabled, unchanged.
- `chronograf-v1-plugin_check` — removed from kapacitor entirely (old Rust game-server plugin check, unrelated to fleet monitoring). Kept in this repo (`chronograf-v1-plugin_check.tick`) as an archival copy only, not deployed. 
