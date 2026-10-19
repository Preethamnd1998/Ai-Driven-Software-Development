# Problem Statement — Task and Approval Management System

## Status
Draft for validation. This is a synthetic educational project, not a production business requirement.

## Problem
A small team needs a lightweight way to create tasks, assign responsibility, submit tasks for approval, approve or reject submissions, and track current status with a clear history of decisions.

## Intended users
- **Requester:** creates and edits eligible tasks and submits them for approval.
- **Approver:** reviews submitted tasks and approves or rejects them with a comment.
- **Administrator:** manages users/roles and can inspect system activity.
- **Viewer (optional):** can view tasks they are authorized to see.

## Initial scope
1. Create, view, update, and list tasks.
2. Assign a requester and an approver.
3. Move a task through a defined status workflow.
4. Submit a task for approval.
5. Approve or reject a submitted task; rejection requires a reason.
6. Record who performed each workflow action and when.
7. Validate permissions on the server, not only in the UI.
8. Provide automated tests for business rules and complete user workflows.

## Proposed workflow
`DRAFT → SUBMITTED → APPROVED`
`DRAFT → SUBMITTED → REJECTED → DRAFT`

Only authorized users may perform each transition. Exact permissions and whether an approved task can be reopened must be decided in the requirements phase.

## Non-goals for the first version
- AI features embedded inside the application.
- Real patient, employee, or customer data.
- Complex organization hierarchy or multi-tenant SaaS.
- Payments, notifications to external systems, or advanced reporting.
- Public deployment as a requirement for lifecycle proof.

## Quality and security requirements
- Enforce authorization at the API/service layer.
- Validate inputs and reject invalid state transitions.
- Store an audit/history record for approval decisions.
- Keep secrets in environment configuration, never source control.
- Use synthetic seed data only.
- Provide reproducible build and test instructions.
- Document known limitations and threat-model assumptions.

## Open questions to resolve before implementation
- Should authentication be included, or should the first slice use a controlled local demo identity?
- Can the requester edit a rejected task, and can it be resubmitted?
- Can approvers approve their own requests?
- Which task fields are mandatory?
- Is the first release single-user/local or multi-user?
- Which database and hosting constraints apply?
- Which Java and Angular versions will be selected?

Do not silently invent answers. Record decisions and rationale in an architecture decision record.
