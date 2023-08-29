---
sidebar_position: 1
---

# Standard

## Configuration

Our default configuration of Postgres. 

The following configurations automatically scale based on the size of cpu, memory, and storage for the instance: 

- `shared_buffers`
- `max_connections`
- `work_mem`
- `bgwriter_delay`
- `effective_cache_size`
- `maintenance_work_mem`
- `max_wal_size`

## Extensions

- `pg_stat_statements` comes pre-installed and enabled.
- Extensions from [Trunk](https://pgt.dev) can be installed on-demand.