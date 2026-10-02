# Contributing to ModelSphere

Thanks for helping. This guide applies to every repository in the
[ModelSphere organization](https://github.com/modelsphere). A repository's own
`CONTRIBUTING.md` adds to it and wins where they differ — it says how to build,
test and run that component.

```
issue ──▶ triage ──▶ branch ──▶ pull request ──▶ CI + review ──▶ merge ──▶ next release
```

## Code of conduct

Everyone taking part — issues, pull requests, reviews, chat — follows the
[Code of Conduct](CODE_OF_CONDUCT.md).

## Where a change belongs

ModelSphere is several repositories. Put the change where the code lives:

| You want to change | Repository |
|---|---|
| How the stack is installed (Ansible, helmfile, offline bundle) | [modelsphere](https://github.com/modelsphere/modelsphere) |
| The sglang / vllm / CART Helm charts | [helm-charts](https://github.com/modelsphere/helm-charts) |
| A model's tuned deployment config | [model-catalog](https://github.com/modelsphere/model-catalog) |
| Routing | [llm-openresty](https://github.com/modelsphere/llm-openresty), [cache_aware_router](https://github.com/modelsphere/cache_aware_router), [autoconfig](https://github.com/modelsphere/autoconfig) |
| Scaling, SLOs, health | [llm-operator](https://github.com/modelsphere/llm-operator), [slo-scaler-decision-gen](https://github.com/modelsphere/slo-scaler-decision-gen), [slo-api](https://github.com/modelsphere/slo-api), [hang-watcher](https://github.com/modelsphere/hang-watcher) |
| Deploying models, the web console | [swiss](https://github.com/modelsphere/swiss), [console](https://github.com/modelsphere/console) |
| Tuning and benchmarking | [llm-autotune](https://github.com/modelsphere/llm-autotune), [llm-autotune-policies](https://github.com/modelsphere/llm-autotune-policies), [llm-bench](https://github.com/modelsphere/llm-bench) |

Not sure? Open the issue in [modelsphere](https://github.com/modelsphere/modelsphere);
it will be moved.

## Ways to contribute

| You want to | Start here |
|---|---|
| Report a bug | An issue in the right repository, using the bug template |
| Ask for a feature | A feature request issue; for anything large, describe the problem first and agree on the approach before writing code |
| Report a vulnerability | **Not** a public issue — see [SECURITY.md](SECURITY.md) |
| Fix or build something | Comment on the issue so nobody duplicates the work, then a pull request |
| Improve the docs | Same as code: a branch and a pull request, `docs:` commits |

New here? Look for issues labelled `good first issue` or `help wanted`.

## Issues

- Search existing issues first, open *and* closed.
- One problem per issue. Say what you did, what you expected, what happened,
  and the versions involved.
- Redact hostnames, IPs, tokens, API keys and passwords from everything you
  paste.

## Pull requests

- Fork the repository (or, if you are a member, push a branch), and open the
  pull request against the default branch.
- Link the issue it fixes (`Fixes #123`). Trivial fixes may skip the issue.
- One self-contained change per pull request; refactors separate from behaviour
  changes; tests in the same pull request as the code.
- Title and commits follow [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/):
  `feat(router): …`, `fix(chart): …`, `docs: …`.
- Fill in the pull request template, including how you tested the change.
- CI must be green. A maintainer reviews and merges with a merge commit.

**Say why, not what.** The diff says what changed. The description should say
what was wrong before, and how you know the new behaviour is right — the
command you ran and what it printed.

**A check that cannot fail is not a check.** If you add a test or a guard, make
sure it fails on the broken input as well as passing on the good one.

## Language

Code, comments, commit messages and primary documentation are in English. A
translation may sit next to the English file with a language suffix, e.g.
`README.zh-CN.md`.

## Never commit

- Credentials of any kind: API keys, tokens, kubeconfigs, private keys,
  `.env` files.
- Internal hostnames, IP addresses, registry paths or cluster names. Examples
  use `example.com`, `registry.example.com` and the documentation IP ranges.

Secret scanning with push protection is on for every public repository; if it
blocks a push, remove the secret rather than bypassing the check, and rotate it
if it was real.

## License

Every repository is licensed under the [Apache License 2.0](LICENSE). By
contributing you agree that your contribution is licensed under the same terms
(Apache-2.0, section 5).
