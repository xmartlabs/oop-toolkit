# Python Toolkit

## What is it

Python Toolkit is a code-first companion for teams building on top of VytalLink. Instead of exposing health data directly to an AI client, it packages the workflow as a Python library, CLI, and notebooks so you can fetch wearable data, compute recovery signals, and plug the results into your own backend, automation, or demo.

The current implementation lives in the [`xmartlabs/vytallink-health-kit`](https://github.com/xmartlabs/vytallink-health-kit) repository.

## How it works

The toolkit sits downstream from VytalLink. It authenticates against a VytalLink deployment, fetches a health data window, normalizes sleep, heart rate, and activity payloads into Python domain models, and then runs application use cases on top of that data.

It currently supports three main usage modes:

- installable Python package
- command-line interface
- demo notebooks

## Why Python Toolkit?

Sometimes MCP is the fastest way to get health data into an assistant. But if you are building a custom backend, a scheduled job, a notebook-based prototype, or a product workflow that needs code-level control, you want something you can import, script, and extend.

Python Toolkit gives you that layer. It already knows how to talk to VytalLink, handles both legacy and newer metrics-based API shapes, computes readiness-related metrics, and can optionally enrich the result with an LLM narrative. That means your team can focus on the product logic instead of rebuilding health-data ingestion and normalization from scratch.

## Quickstart

The source repository targets Python 3.11+ and uses `uv` for setup.

```bash
git clone https://github.com/xmartlabs/vytallink-health-kit
cd vytallink-health-kit
make install
source .venv/bin/activate
cp .env.example .env
```

Minimum runtime configuration:

```bash
export VYTALLINK_BASE_URL="https://your-vytallink-host"
export VYTALLINK_WORD="your-word"
export VYTALLINK_CODE="your-code"
```

Run the readiness flow:

```bash
uv run vytallink-health-kit readiness --no-llm
```

## Practical Example

**Scenario**: You're building a hackathon prototype that needs a daily readiness summary plus structured data you can reuse in your app.

**Input** (CLI):

```bash
uv run vytallink-health-kit readiness --output json --no-llm
```

**Output**: The toolkit fetches a seven-day VytalLink window, computes signals like sleep efficiency, resting heart rate trend, load ratio, and readiness score, then returns the result as structured JSON or markdown.

**Another example**:

```bash
uv run vytallink-health-kit etl --days 30 --output-file health_data.csv
```

This exports a larger window of normalized wearable data into a tabular file you can analyze in notebooks, dashboards, or internal pipelines.

## Quick Reference

| Aspect | Details |
|--------|---------|
| **Consumption modes** | Python package, CLI, notebooks |
| **Core use cases** | Readiness report, ETL export, health-data chat |
| **Supported data** | Sleep, resting heart rate, activity |
| **Output formats** | Markdown, JSON, CSV, Parquet |
| **Architecture** | Clean split between `domain`, `application`, and `infrastructure` |
| **VytalLink compatibility** | Legacy REST endpoints and newer metrics API via direct login |
| **Optional AI layer** | Anthropic/OpenAI-backed narrative generation with deterministic fallback |
| **Observability** | Grafana, Jaeger, Loki, Promtail, LangSmith |

## Limitations and Considerations

- **Depends on VytalLink**: This toolkit is not a replacement for VytalLink. It consumes VytalLink data after the mobile app and backend session are already in place
- **Live session constraints still apply**: If the phone session is unavailable or expires, the toolkit cannot fetch fresh data
- **Repository scope is intentionally narrow**: The default workflow is centered on readiness-style analysis, not a full clinical analytics platform
- **Backend contracts can vary**: Different VytalLink environments may expose different endpoint shapes, so some configuration overrides may be needed
- **Wellness, not diagnosis**: These signals are useful for recovery and product experimentation, but they are not clinical-grade medical recommendations

## Resources

- [GitHub Repository](https://github.com/xmartlabs/vytallink-health-kit)
- [Configuration Guide](https://github.com/xmartlabs/vytallink-health-kit/blob/main/docs/configuration.md)
- [Domain Notes](https://github.com/xmartlabs/vytallink-health-kit/blob/main/docs/domain.md)
- [Observability Guide](https://github.com/xmartlabs/vytallink-health-kit/blob/main/docs/observability.md)
- [VytalLink Integration Guide](https://github.com/xmartlabs/vytallink-health-kit/blob/main/docs/vytallink-integration-guide.md)
