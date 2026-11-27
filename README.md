# reach-proto

Shared Protocol Buffers and gRPC service definitions for the **REACH** autonomous drone platform.

## Definitions

- `drone.proto` — `drone.DroneControl` gRPC service:
  - `StreamTelemetry(Empty) -> stream TelemetryData` (latitude, longitude, altitude, timestamp)
  - `Arm(Empty) -> CommandResult`
  - `Disarm(Empty) -> CommandResult`
  - `SendRCOverride(RCChannels) -> CommandResult` (roll, pitch, throttle, yaw PWM microseconds)

## Used By

- [`reach-core`](https://github.com/oc7o/reach-core) — Rust MAVLink ↔ gRPC bridge running on the companion computer
- [`reach-control`](https://github.com/oc7o/reach-control) — Ground station client
