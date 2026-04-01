# Project Context Sync Checklist

Use this as the final quick validator.

## Contract Check

- Is `project root` explicit?
- Is `current repo` explicit?
- If references exist, is reference scope explicit?
- If references exist, are they listed with type + identifier/link?
- Is one canonical context path selected?
- Are related repos resolved to actual paths or marked as open questions?

## Execution Check

- Was local context read before deep repo scanning?
- Were `working targets` used as first navigation targets?
- Was external reference recheck done only when needed?
- Was context updated in the same session as code/policy change?

## Handoff Check

- Are confirmed facts separated from open questions?
- If references exist, is reference sync status updated?
- If references exist, are reference deltas (external docs vs local context) captured?
- Does next-session handoff note provide a clear restart point?

## Final Question

- If this workflow continues tomorrow, can the next session start from context directly without rediscovering the same scope?
