# RAG index

**Purpose:** retrieval-oriented index for agents working on `techrote/6700`.

Use the smallest relevant document set rather than loading the whole repository.

| Document | Retrieve when the task concerns | Key terms |
|---|---|---|
| `AGENT_CONTEXT.md` | programme intent, non-negotiables, current phase | i7-6700, M620, known-good, automation node |
| `HARDWARE_INVENTORY.md` | hardware facts, unknowns, inspection | CPU, RAM, SSD, NIC, BIOS, M620, SMART |
| `ARCHITECTURE.md` | target system roles and boundaries | worker, controller, VPN, FTTP, trust domain |
| `SECURITY_MODEL.md` | network/security decisions | WireGuard, isolation, firewall, least privilege |
| `BASELINE.md` | qualification and benchmark methodology | thermals, power, fio, stress, compile, variance |
| `PROVISIONING.md` | OS/setup/reproducibility | Linux, packages, bootstrap, idempotent |
| `OPERATIONS.md` | monitoring, backups, recovery, maintenance | logs, SMART, updates, restore, runbook |
| `EVIDENCE.md` | what evidence must be retained | commands, versions, logs, measurements |
| `VERIFY.md` | final acceptance gates | verification, security, benchmark, recovery |
| `DECISIONS.md` | accepted architectural choices and deferred choices | ADR, decision, rationale, revisit |
| `ROADMAP.md` | human-readable programme phases and sequencing | phase, prerequisite, milestone, dependency |
| `PLAN_REVIEW.md` | pre-implementation critique and corrections | omission, risk, review, correction, deferred |
| `workflow.json` | machine-readable issue dependency graph | issue, depends_on, phase, parallelism, conditional |

## Retrieval rules

- Treat repository evidence as more authoritative than assumptions from prior chats.
- Treat `HARDWARE_INVENTORY.md` fields marked `UNKNOWN` as unresolved; do not infer them.
- Do not include the second suspect i7-6700 machine in implementation unless a future issue explicitly changes scope.
- Measurements are machine-specific. Do not generalise one benchmark into a universal hardware claim.
- Security changes must preserve the rule that the automation network does not gain a route into the household LAN.
- Prefer evidence-producing tasks before optimisation or hardware purchasing decisions.
- For task selection, consult `workflow.json` before opening a large set of issues; then retrieve only the selected issue and the narrow documents it names.
