## ModelSphere: Production-Grade Infrastructure for LLM Inference

ModelSphere is an open-source LLM inference infrastructure designed to make production-grade model serving simple, efficient, and continuously optimized. It provides instant deployment across heterogeneous accelerators, stays ready for the latest models through a flexible inference architecture, and continuously improves serving performance based on real-world workloads.

**Start here:** [modelsphere/modelsphere](https://github.com/modelsphere/modelsphere) —
the deployment repository, with the install guide and the architecture.

| Area | Repository | What it does |
|---|---|---|
| Install | [modelsphere](https://github.com/modelsphere/modelsphere) | Installs the whole stack: Ansible, helmfile, offline bundle |
| | [helm-charts](https://github.com/modelsphere/helm-charts) | Helm charts for the sglang and vllm engines and the routing components |
| | [model-catalog](https://github.com/modelsphere/model-catalog) | The models swiss can deploy, and how to serve each one: engine, image, flags, GPUs, tuned variants |
| Routing | [llm-openresty](https://github.com/modelsphere/llm-openresty) | Session-affinity router, request logging and metrics |
| | [cache_aware_router](https://github.com/modelsphere/cache_aware_router) | Routes to the replica holding the longest matching prompt prefix |
| | [autoconfig](https://github.com/modelsphere/autoconfig) | Keeps the routing layer's config in sync with the model backends |
| Scaling and health | [llm-operator](https://github.com/modelsphere/llm-operator) | Autoscales on KV-cache utilization, queue depth and TPM |
| | [slo-scaler-decision-gen](https://github.com/modelsphere/slo-scaler-decision-gen) | Turns SLO targets and live signals into replica decisions |
| | [slo-api](https://github.com/modelsphere/slo-api) | HTTP API to read and change a service's SLO |
| | [hang-watcher](https://github.com/modelsphere/hang-watcher) | Restarts an engine that stopped making progress |
| | [continuation_gateway](https://github.com/modelsphere/continuation_gateway) | Resumes a streamed completion that stalls or drops mid-generation, so the client gets one complete stream |
| Operate | [swiss](https://github.com/modelsphere/swiss) | Deploy control plane for the engine charts |
| | [console](https://github.com/modelsphere/console) | Web console: users and roles, model deployment, playground |
| Tune and measure | [llm-autotune](https://github.com/modelsphere/llm-autotune) | Searches serving configurations on idle GPUs |
| | [llm-autotune-policies](https://github.com/modelsphere/llm-autotune-policies) | Search policies and the policy SDK for llm-autotune |
| | [llm-bench](https://github.com/modelsphere/llm-bench) | Benchmark platform for LLM serving endpoints |

Everything here is licensed under Apache-2.0.
[Contributing](https://github.com/modelsphere/.github/blob/main/CONTRIBUTING.md) ·
[Code of Conduct](https://github.com/modelsphere/.github/blob/main/CODE_OF_CONDUCT.md) ·
[Security](https://github.com/modelsphere/.github/blob/main/SECURITY.md)
