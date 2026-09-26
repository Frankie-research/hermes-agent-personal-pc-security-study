# Appendix B - Proposed Reproducibility and Validation Test Matrix

| Test ID | Test | Expected Result | Actual Result | Status |
|---|---|---|---|---|
| R-01 | Container isolation | Host files inaccessible | Containerized agent access was constrained by the configured Docker execution boundary; host-side access was not treated as inherently safe merely because the agent was running in Docker. | PASS* |
| R-02 | Read-only mount | Write denied | Read-only access was explicitly targeted for the NAS/shared workspace. Direct Windows drive binding did not provide the intended NAS isolation, and CIFS-based access required additional permission/session configuration before it could be considered a validated read-only control. | CONDITIONAL* |
| R-03 | Cron execution | Job executes | Scheduled ASX, US-market and catch-up jobs were successfully executed and produced the expected operational outputs during validation. | PASS |
| R-04 | Invalid path | Safe failure | Invalid and translated Windows/Docker paths were identified during testing; path translation failures did not establish permission to access the intended host location and required explicit path validation. | PASS* |
| R-05 | Unicode output | UTF-8 preserved | Encoding and mojibake issues were observed in intermediate testing and subsequently corrected in the affected scripts/output path. Post-fix Python syntax validation and controlled output tests completed successfully. | PASS* |

*Status reflects the observed practitioner environment and configuration, not a universal security guarantee. Reproduction on another system should independently validate the stated control.
