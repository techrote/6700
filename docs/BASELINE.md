# Baseline and qualification

## Goal

Create a repeatable evidence set describing the machine before substantial tuning. Baselines should answer both **is the machine healthy?** and **how variable is performance under relevant workloads?**

## Preconditions

- inventory captured;
- important data/recovery material preserved;
- machine can be recovered from a failed software/network change;
- ambient conditions and power mode recorded.

## Measurements

### Health
- storage SMART/health and error logs;
- memory test appropriate to available downtime;
- CPU/GPU idle and sustained-load temperatures;
- evidence of throttling, clock collapse, ECC/PCIe/storage errors where observable.

### CPU
- single-thread and all-thread repeatable benchmark;
- sustained all-core workload for at least 30 minutes;
- record clocks, temperatures and power state during the run;
- repeat enough times to establish ordinary variance rather than a single best score.

### Memory
- capacity/topology confirmation;
- bandwidth/latency measurement where tooling permits;
- repeat under otherwise idle conditions.

### Storage
- filesystem free space;
- sequential read/write;
- small-block random read/write at low and moderate queue depths;
- fsync/small-file latency where practical;
- p50/p95/p99 latency where tooling supports it;
- never run destructive raw-device tests against data that has not been preserved.

### Network
- LAN link speed;
- latency and packet loss;
- sustained upload/download measurement appropriate to the connection;
- later, WireGuard throughput and overhead.

### Representative workload

At least one real repository workload should be used in addition to synthetic tests. Cybersand is preferred once its environment is available:

- clean dependency/setup path;
- clean build time;
- test time;
- deterministic replay/simulation throughput;
- sanitizer overhead where applicable.

## Variance rule

Performance evidence should include repeated runs and a summary of median, spread and obvious outliers. Optimisation decisions should not be based on one run.

## Evidence format

Store machine-readable outputs where reasonable and a short Markdown summary describing conditions, tooling versions, anomalies and conclusions.
