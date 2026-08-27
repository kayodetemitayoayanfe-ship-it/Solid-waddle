# solid-waddle

> Steady systems don't need to be graceful — they need to keep moving.

## What is this?

**solid-waddle** is a lightweight, dependency-light Python toolkit for building fault-tolerant scripts and services. It focuses on graceful degradation, sane retry behavior, and forgiving defaults — so your code keeps waddling forward even when something upstream wobbles.

The name is intentional: *solid* is the guarantee that small failures won't take the whole system down. *Waddle* is the honest acknowledgment that things will wobble — dependencies break, inputs surprise you, networks hiccup.

## Why

Most resilience libraries chase perfect uptime. solid-waddle optimizes for something more realistic: **forgiving failure**. Log what went wrong, recover where possible, and fail loudly only when it truly matters.

## Features (planned / in progress)

- 🔁 Configurable retry with backoff for flaky operations
- 🛡️ Safe-call wrappers that degrade gracefully instead of crashing
- 📋 Structured logging for failures, so nothing fails silently
- 🪶 Minimal dependencies — plays nicely in any Python project

## Installation

```bash
pip install solid-waddle
```

*(Not yet published — coming soon. For now, clone and install locally:)*

```bash
git clone https://github.com/YOUR_USERNAME/solid-waddle.git
cd solid-waddle
pip install -e .
```

## Quick example

```python
from solid_waddle import retry, safe_call

@retry(attempts=3, backoff=0.5)
def fetch_data():
    ...

result = safe_call(fetch_data, default=None)
```

## Status

This project is intentionally minimal at the start. It's meant to grow through real use rather than a big upfront design. Contributions, forks, and experiments are welcome — the waddle only gets steadier with more feet on the ground.

## License

MIT
