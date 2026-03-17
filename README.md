# TraceRedis

A Redis-like database that visualizes how commands execute internally.

## Project Vision

TraceRedis is an in-memory key-value store built entirely from scratch with an emphasis on **Execution Tracing**. The core philosophy of this project is *Everything is traceable*.

Every command execution step—from parsing the protocol, routing the command, looking up keys in memory, to registering TTLs—emits telemetry data. This enables you to understand exactly what happens under the hood when a command is executed.

## Core Features

- **Redis-Compatible Protocol**: Understands standard RESP (Redis Serialization Protocol), so you can use standard Redis clients like `redis-cli`.
- **In-Memory Storage**: Fast key-value store with basic operations (`SET`, `GET`, `DEL`, `EXPIRE`, `KEYS`).
- **Trace Engine**: Every execution step is recorded with timestamps and metadata.
- **Trace Visualization** *(Coming in v1.0)*: A built-in web dashboard showing timeline and waterfall charts of command executions.

## Example

```
Client: SET name lin
Server: +OK

Trace Output:
parse_command     0.02ms
hash_lookup       0.03ms (key=name)
write_value       0.01ms (size=3)
response_send     0.01ms
```

## Setup & Roadmap

See [開發計畫.md](./planing/開發計畫.md) for detailed implementation milestones.
