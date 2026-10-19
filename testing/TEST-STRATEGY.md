# Test Strategy

## Test layers
- Unit: domain rules, validation, state transitions.
- Integration: persistence and service interactions.
- API: request validation, response contracts, authorization.
- End-to-end: user-visible workflows across the application.
- Regression: previously failing cases remain fixed.

## Core workflow scenarios
1. Authorized requester creates a draft task.
2. Requester submits a valid task.
3. Unauthorized user cannot submit or approve it.
4. Assigned approver approves a submitted task.
5. Assigned approver rejects a submitted task with a reason.
6. Invalid transitions are rejected.
7. Status and decision history remain consistent.
8. A rejected task can be edited/resubmitted only according to the approved rule.
9. API errors do not expose secrets or stack traces.
10. UI state reflects the verified server result, not an optimistic assumption alone.

## Evidence
Record exact commands, environment, commit SHA, test counts, pass/fail totals, skipped tests, and known limitations. Coverage alone does not prove correctness. Review whether tests assert meaningful behavior and can detect a deliberately introduced defect.
