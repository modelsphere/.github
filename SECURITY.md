# Security policy

This policy covers every repository in the
[ModelSphere organization](https://github.com/modelsphere) that does not have a
`SECURITY.md` of its own. A repository's own policy takes precedence.

## Reporting a vulnerability

Report privately, never as a public issue, pull request or discussion.

1. Open the affected repository on GitHub, go to **Security → Report a
   vulnerability**, and use GitHub's
   [private vulnerability reporting](https://docs.github.com/en/code-security/security-advisories/guidance-on-reporting-and-writing-information-about-vulnerabilities/privately-reporting-a-security-vulnerability).
   It is enabled on every public repository in the organization.
2. If that is unavailable to you, open an issue saying only that you have a
   report and how to reach you — no details — and a maintainer will arrange a
   private channel.

Include what you can of:

| Field | |
|---|---|
| Title | one line, e.g. "router: a request without a key reaches the backend" |
| Overview | what an attacker can do, and from where (network, a tenant, a pod in the cluster) |
| Affected versions | component and version(s); Helm chart version and values if relevant |
| Reproduction | steps or a proof of concept |
| CVE | if one is already assigned |
| Contact | how to reach you for follow-up |

If you are not sure which repository is affected, report it on the one you
found it in; maintainers will move it.

## What happens next

```
report ──▶ acknowledged (≤ 7 days) ──▶ assessed, plan shared
       ──▶ fix on the default branch + release ──▶ advisory published, reporter credited
```

- Please keep the report confidential until a fix is released.
- We credit reporters in the advisory unless you ask us not to.
- Where a fix needs an intrusive change and a workaround exists, we may ship
  the fix in the next regular release and publish the workaround in the
  advisory.

## Supported versions

Security fixes land on each repository's default branch and ship in its next
release. Upgrade to the latest release to get them; older releases get fixes on
a best-effort basis only.

## Out of scope

- Vulnerabilities in upstream projects ModelSphere deploys or builds on
  (Kubernetes, SGLang, vLLM, OpenResty, and others) — report those upstream.
  Tell us too if the way ModelSphere uses them makes things worse.
- Attacks that require cluster-admin, or root on a node, to begin with.
