# How this knowledge base works

Every record is one markdown file with a header block at the top. The header is what lets a person, or an AI, tell which record to trust.

## Header fields

```yaml
---
title: Customer onboarding policy
owner: Head of Operations
status: approved
effective_date: 2026-09-01
review_by: 2027-03-01
supersedes: policies/customer-onboarding-policy-2025.md
superseded_by:
sensitivity: internal
---
```

| Field | Required | Meaning |
| --- | --- | --- |
| `title` | Yes | Plain name of the record |
| `owner` | Yes | A role, not just a person, so it survives people moving on |
| `status` | Yes | One of the values below |
| `effective_date` | Yes | The date this version starts to apply (YYYY-MM-DD) |
| `review_by` | Yes | The date the owner must check it is still right |
| `supersedes` | If any | Path of the record this one replaced |
| `superseded_by` | If any | Path of the record that replaced this one |
| `sensitivity` | Yes | `public`, `internal` or `confidential` |

## Status values

| Status | Meaning | Can it be followed? |
| --- | --- | --- |
| `approved` | The current instruction, agreed by the owner | Yes |
| `draft` | Being written or reviewed | No |
| `working-note` | Useful context, ideas or history | No, background only |
| `superseded` | Replaced by a newer record | No, follow `superseded_by` |
| `archived` | No longer relevant | No |

## Rules

1. One topic has one `approved` record at a time.
2. When a record is replaced, set its `status` to `superseded` and fill in `superseded_by`. Don't delete it; the history is useful.
3. A record past its `review_by` date is still approved, but flag it to the owner.
4. File names describe the content, in lowercase with hyphens: `client-report-procedure.md`.
5. `confidential` records only go into an AI service that has been approved for that data.

## Folders

- `policies/`: rules the business has decided
- `procedures/`: how a task is done, step by step
- `working-notes/`: background and context, never instructions
- `templates/`: blank records to copy
- `sources.md`: which record is authoritative for each topic
