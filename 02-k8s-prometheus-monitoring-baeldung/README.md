# Monitoring Kubernetes Pods with Prometheus — Baeldung

**Published:** Baeldung on Ops · **Role:** Author

[Read the published article →](https://www.baeldung.com/ops/prometheus-cpu-memory-kubernetes)

---

## The brief

Baeldung asked for a hands-on guide to monitoring pod-level CPU and memory on Kubernetes using Prometheus, aimed at engineers who have deployed workloads but have not yet stood up observability. The piece had to be runnable end-to-end on a local cluster, not a vendor walkthrough.

## What made this hard

Three things trip readers up, and a good article has to address all of them:

- **The metrics stack is a maze.** metrics-server, kube-state-metrics, node-exporter, and Prometheus itself all look similar on the surface. Readers pick the wrong one and their queries silently return nothing.
- **PromQL's mental model is unfamiliar** to engineers coming from Datadog, CloudWatch, or New Relic. Explaining it without drowning the reader in label theory is a real constraint.
- **The happy-path guide already exists a hundred times.** The value add had to be the part that saves readers when their metrics are missing.

## My approach

- Opened with a short **mental-model map** — metrics-server vs. kube-state-metrics vs. node-exporter — before touching a single query, so readers would know which component produces which signal.
- Wrote every PromQL example with a one-line "how to read it" annotation rather than a wall of queries.
- Tested the full flow on a real cluster (kind plus the Prometheus community chart) and captured actual output — no hypothetical YAML.
- Included a short **"your metrics aren't showing up — here's why"** troubleshooting section, because that's the actual moment readers reach for an article like this.

## Outcome

- Passed editorial review on first submission.
- Continues to drive steady organic traffic on head terms for pod-level Prometheus monitoring.
- Cross-linked from related Baeldung DevOps articles as the canonical reference for this topic.

## Why this matters for AI/ML clients

If you're documenting a product that runs inference workloads on Kubernetes — LLM serving, RAG pipelines, agent infrastructure — your readers need exactly this kind of observability grounding before they can reason about latency, cost, or reliability. This piece demonstrates I can document the *infrastructure underneath the model*, not just the model itself.
