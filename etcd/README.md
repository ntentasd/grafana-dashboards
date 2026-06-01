# etcd Dashboard

Monitors an etcd cluster across disk health, cluster health, and storage.

## Requirements

- etcd metrics scraped by Prometheus (`:2379`)

## Panels

### Disk Health

- WAL fsync P99 — write-ahead log flush latency per node. Should stay under 10ms.
- Backend commit P99 — bbolt commit latency. Should stay under 25ms.
- Fragmentation % — ratio of allocated vs used db pages. Above 40% warrants a defrag.

### Cluster Health

- Leader / Follower — which node is currently the Raft leader.
- Leader changes — how many times leadership changed in the last hour. Any value
  above 1 indicates instability.
- Proposals failed — failed Raft write proposals. Should always be zero.

### Storage

- DB size in use — actual data size vs quota limit (dashed red line).
- Quota used % — how much of the 2GB default quota is consumed.
