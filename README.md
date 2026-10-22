# dependency-security-audit

Dependency security audit findings

## Audit overview

Dependency risk review of the third-party projects tracked via GitHub stars. The five most recently starred repositories were examined, and GitHub's security advisory database was checked for the ecosystems identified (pip, detected from the starred projects) plus the npm and pip baseline stack.

### Starred repositories examined

| # | Repository | Latest tag | Ecosystem / language | Detection method | CI status |
|---|------------|-----------|----------------------|-----------------|-----------|
| 1 | [OpenBMB/AgentCPM](https://github.com/OpenBMB/AgentCPM) | none | Python (pip ecosystem) | Primary-language fallback — no package manifest at the repository root | No GitHub Actions workflows are configured; there are no CI runs to check |
| 2 | [PaddlePaddle/ERNIE](https://github.com/PaddlePaddle/ERNIE) | `ernie-4.5` | pip | Repository root (`setup.py`, `pyproject.toml`, `requirements/`) | Latest runs: **Test** success, **Docs** success, **Dependabot Updates** success, **Codestyle** cancelled (not a failure) |
| 3 | [FudanNLP/fastNLP](https://github.com/FudanNLP/fastNLP) | `1.0.0beta2` (most recent tagged commit, 2022-08-23; latest formal release is `v0.6.0`) | pip | Repository root (`setup.py`, `requirements.txt`) | Not checked |
| 4 | [maplezzz/NTU_ML2017_Hung-yi-Lee_HW](https://github.com/maplezzz/NTU_ML2017_Hung-yi-Lee_HW) | none | Jupyter Notebook (no package ecosystem) | Primary-language fallback — repository root contains only homework directories and a README | Not checked |
| 5 | [fighting41love/funNLP](https://github.com/fighting41love/funNLP) | none | Python (pip ecosystem) | Primary-language fallback — no package manifest at the repository root | Not checked |

CI was checked for the two most recently starred repositories (AgentCPM and ERNIE). No failed CI runs were found, so no failed-job logs needed to be pulled.

### Advisory review

Ecosystems checked against GitHub's security advisory database: **npm** and **pip**. The three most severe advisories found (all **critical**) are filed as sub-issues of the parent issue "Dependency security audit", numbered SEC-1 … SEC-3, sorted most-severe-first.
