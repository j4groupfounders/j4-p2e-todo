# p2-13-todo — GREEN

Django 5.2.12 → 6.0.4. Source shacker/django-todo @ 95e3a022d239ebaa8771376c838a4d36590ab9b1.
Preregistration: https://github.com/j4groupfounders/j4-upgrades-harness/commit/6cf87daccde1910714fe47fd0c9b552f9302fae1
Baseline: 054bd58dbd1b8c084afe6d71bbffab985b8c8c48; upgraded: 525a5d8f5e370c1e4dd9ec3420c10089437c0405.

- Project tests: **43 passed, 0 pre-existing skips** before and after; exact collected IDs/skips match: True. No removed/newly skipped tests. Helpdesk subtests additionally retained by original assertions.
- Boot/HTTP: five fixed real-server GET snapshots match: True; model fixture snapshots match: True. No unexplained drift or framework behavior exception.
- Independent seeded faults: project-only **1/5**, combined **5/5**. One fresh-checkout matrix job per mutation, no build state shared. Combined miss-rate halving: True.
- **4 workflow runs**, **9.57 actual job-minutes**, including screening failures and all five matrix jobs. Cap 12. Standard public Ubuntu runners, $0 paid API/service calls. Session token cost is not exposed/measured.
- Zero human app/test edits. Permanent agent app/test logic edits: zero (only the preregistered temporary fault injections). Framework upgrade only changes two pinned dependency files; exact diff preserved as upgrade.patch.

## Repairs and limits
No baseline app/test/harness repair after the initial source screening; added model probes and exact locks in the second screening run.
Harness baseline HTTP boot settings use disposable SQLite, DEBUG=False, local-only allowed hosts and in-memory email. Original app/test source untouched. Original upstream workflows replaced on pilot branches with bounded verification; no upstream modifications/contact.
These are three new Django applications, not three new stacks. Current upstream already advertises compatible framework ranges, so the result supports controlled dependency-upgrade compatibility, not arbitrary legacy migration success.
HTTP remains empty-DB unauthenticated; model probes use fixed unsaved objects. Todo's old due-date fixture is not full clock freezing. Wiki's 3 opt-in browser tests and Helpdesk's 2 upstream skipped attachment tests remain skipped. No authenticated frozen HTTP replay, full route/line coverage, external integrations or production certification.
Seed targets are preregistered measured business/permission surfaces; not an unbiased whole-app mutation score. The extra model checks catch faults beyond the project's suite where applicable.

## Evidence runs
- [37620112672](https://github.com/j4groupfounders/j4-p2e-todo/actions/runs/37620112672) — j4/p2e-baseline, success, 0.78 job-min
- [37620445103](https://github.com/j4groupfounders/j4-p2e-todo/actions/runs/37620445103) — j4/p2e-baseline, success, 1.12 job-min
- [37621131097](https://github.com/j4groupfounders/j4-p2e-todo/actions/runs/37621131097) — j4/p2e-upgrade, success, 1.10 job-min
- [37621364253](https://github.com/j4groupfounders/j4-p2e-todo/actions/runs/37621364253) — j4/p2e-seeds, success, 6.57 job-min

## Seed detections

```json
[
  {
    "mutation": 0,
    "tests": 43,
    "skipped": 0,
    "project_detected": true,
    "harness_detected": true,
    "combined": true
  },
  {
    "mutation": 1,
    "tests": 43,
    "skipped": 0,
    "project_detected": false,
    "harness_detected": true,
    "combined": true
  },
  {
    "mutation": 2,
    "tests": 43,
    "skipped": 0,
    "project_detected": false,
    "harness_detected": true,
    "combined": true
  },
  {
    "mutation": 3,
    "tests": 43,
    "skipped": 0,
    "project_detected": false,
    "harness_detected": true,
    "combined": true
  },
  {
    "mutation": 4,
    "tests": 43,
    "skipped": 0,
    "project_detected": false,
    "harness_detected": true,
    "combined": true
  }
]
```
