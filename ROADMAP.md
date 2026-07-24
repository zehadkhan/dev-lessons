# The Dev Lessons Curriculum

The goal: a **book-sized, animated curriculum** covering networking, backend, database and DevOps engineering — the things you otherwise learn from production incidents.

**The quality bar (every chapter must pass all four — or it doesn't get built):**

1. **A mechanism that moves.** If animation doesn't make it clearer than text, it's not a lesson here.
2. **Failure-first.** Show what breaks and why, before the fix. No pattern without its incident.
3. **Real commands.** Every lesson doubles as a reference you can use at work the same day.
4. **Production-grounded.** Real scenarios, real numbers, real trade-offs — not toy examples.

Status: ✅ published · 🔜 next wave · 📋 planned

---

## Part I — Networking: how the internet actually works

| Ch | Lesson | Core mechanism to animate | Status |
|----|--------|---------------------------|--------|
| 1 | What happens when you type a URL | DNS → TCP → TLS → HTTP, the full journey as one animation | 🔜 |
| 2 | DNS, demystified | Resolver chain, record types, TTL caching — and why "propagation" is mostly a myth | 🔜 |
| 3 | TCP under the hood | Three-way handshake, retransmission, why packet loss makes apps *slow* not *broken* | 🔜 |
| 4 | TLS and the certificate that expired at 3am | The handshake, the chain of trust, and the outage every company has had | 🔜 |
| 5 | HTTP/1.1 → HTTP/2 → HTTP/3 | Head-of-line blocking visualized; multiplexing collapsing the waterfall | 📋 |
| 6 | Why your server is unreachable | IPs, ports, NAT and firewalls — debugging connection refused vs timeout | 📋 |
| 7 | CDNs and edge caching | Requests short-circuiting at the edge; cache keys; origin shield | 📋 |
| 8 | Real-time: polling vs SSE vs WebSockets | Connection lifetimes and message flow, side by side | 📋 |

## Part II — Backend mechanics

| Ch | Lesson | Core mechanism to animate | Status |
|----|--------|---------------------------|--------|
| 1 | Idempotent payment webhooks | Duplicate delivery → double charge → unique-constraint claim | ✅ [Lesson 02](lessons/02-idempotent-payment-webhooks/index.html) |
| 2 | The inventory race condition | Check-then-act interleaving → atomic UPDATE | ✅ [Lesson 04](lessons/04-inventory-race-condition/index.html) |
| 3 | The cache stampede | TTL expiry → thundering herd → lock + stale-while-revalidate | ✅ [Lesson 05](lessons/05-cache-stampede/index.html) |
| 4 | Rate limiting | Token bucket filling/draining live; burst vs sustained traffic | 📋 |
| 5 | Retries done right | Instant retries amplifying an outage vs exponential backoff + jitter | 📋 |
| 6 | Background jobs and queues | Blocking request vs worker; retry, poison messages, dead-letter | 📋 |
| 7 | Timeouts and circuit breakers | One slow dependency cascading into total outage — then the breaker tripping | 📋 |
| 8 | Connection pooling | "Too many connections": pool checkout, exhaustion, right-sizing | 📋 |
| 9 | Pagination that survives scale | OFFSET crawling past a million rows vs cursor seeking straight to them | 📋 |

## Part III — Databases

| Ch | Lesson | Core mechanism to animate | Status |
|----|--------|---------------------------|--------|
| 1 | The N+1 query, seen live | One loop → N round-trips → eager loading flat at 2 | ✅ [Lesson 03](lessons/03-n-plus-one-query/index.html) |
| 2 | What an index actually does | Full scan vs B-tree hops; reading EXPLAIN | ✅ [Lesson 06](lessons/06-what-an-index-does/index.html) |
| 3 | Read replicas and the vanishing write | Replication lag; read-your-writes routing | ✅ [Lesson 08](lessons/08-read-replicas/index.html) |
| 4 | Transactions and isolation levels | Dirty reads, non-repeatable reads, phantoms — interleaved and visualized | 📋 |
| 5 | Deadlocks | Two transactions locking in opposite order, frozen, one killed | 📋 |
| 6 | Backups that actually restore | Full dump + binlog point-in-time replay; the untested-backup incident | 📋 |
| 7 | Sharding and partitioning | One table splitting across nodes; the cross-shard query problem | 📋 |

## Part IV — DevOps and infrastructure

| Ch | Lesson | Core mechanism to animate | Status |
|----|--------|---------------------------|--------|
| 1 | Zero-downtime server migration | Bulk copy + live replication + minutes-long cutover | ✅ [Lesson 01](lessons/01-zero-downtime-migration/index.html) |
| 2 | Deploys that can't take the site down | Big-bang outage vs rolling deploy halted by a health check | ✅ [Lesson 07](lessons/07-rolling-deploys/index.html) |
| 3 | Surviving a server crash at peak traffic | Detection → rerouting → self-recovery vs waiting on a human | ✅ [Lesson 09](lessons/09-surviving-a-server-crash/index.html) |
| 4 | Anatomy of a Linux server | Processes, systemd, ports, logs — where to look when it's broken | 📋 |
| 5 | SSH beyond `ssh user@host` | Keys and agents, tunnels, bastions, port forwarding — animated end to end | 📋 |
| 6 | The reverse proxy | nginx as the front door: routing, TLS termination, buffering, gzip | 📋 |
| 7 | Containers, actually explained | Images as layers, containers vs VMs, why "works on my machine" dies here | 📋 |
| 8 | CI/CD: from `git push` to production | The pipeline as a conveyor belt: build, test, artifact, deploy, verify | 📋 |
| 9 | Monitoring: metrics, logs, traces | One slow request tracked through all three; alerting on symptoms not causes | 📋 |
| 10 | Scaling: vertical, horizontal, auto | Load rising against capacity; when each strategy wins | 📋 |
| 11 | Secrets management | The leaked `.env` incident; vaults, rotation, least privilege | 📋 |

## Part V — Deployment: the ladder from FTP to Kubernetes

Ordered from simplest to heaviest — each rung automates what you did by hand on the previous one.

| Ch | Lesson | Core mechanism to animate | Status |
|----|--------|---------------------------|--------|
| 1 | Deploying to a bare VPS, end to end | SSH → stack install → nginx → systemd service → certbot TLS → firewall → DNS, the whole first deploy | 📋 |
| 2 | File-manager and panel deploys (cPanel, FTP) | A partial upload breaking prod mid-transfer; no history, no rollback — and when panels are honestly fine | 📋 |
| 3 | Docker Compose on a VPS | App + db + proxy as one declared file; upgrade and rollback by image tag | 📋 |
| 4 | Self-hosted PaaS: Coolify (and Dokku, CapRover) | `git push` → build → deploy on your own server; the platform doing chapter 1's work automatically | 📋 |
| 5 | Managed platforms: Vercel and friends | Push → preview URL → promote; serverless functions spinning up per request; the control/convenience trade | 📋 |
| 6 | Kubernetes: why it exists | Pods rescheduling, services routing, ingress, rolling updates, self-healing — and when it's overkill | 📋 |
| 7 | Choosing your rung | The decision ladder animated: static vs app vs fleet, cost vs control vs complexity | 📋 |

## Part VI — Distributed systems (the hard stuff)

| Ch | Lesson | Core mechanism to animate | Status |
|----|--------|---------------------------|--------|
| 1 | The CAP theorem in action | A network partition splitting a cluster; choosing C or A live | 📋 |
| 2 | Eventual consistency | Writes propagating between nodes; conflict, convergence | 📋 |
| 3 | Leader election | A leader dying; the cluster voting; split-brain and how quorums prevent it | 📋 |
| 4 | Clocks lie | Clock skew reordering events; why "last write wins" loses writes | 📋 |
| 5 | Distributed tracing | One request fanning out across five services, reassembled as a trace | 📋 |

---

**Progress: 9 published / 47 chapters planned.**

Want to propose a chapter? Open an issue — but bring the failure story and the mechanism to animate, per the quality bar above.
