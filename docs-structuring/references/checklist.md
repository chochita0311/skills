# Checklist

Use this as the final quick validator after a documentation cleanup.

## Final Validation
- Does each active document have one clear responsibility?
- Is the entrance layer acting as a map rather than an encyclopedia?
- If multiple AI entrance docs exist, are they aligned to the same ownership model?
- If multiple AI entrance docs exist, do overview/docs-map files point to that entrance layer clearly enough?
- Were higher-severity ownership and entrance issues prioritized before minor cleanup?
- Is each repeated instruction owned in one place?
- Were duplicated blocks removed or replaced with pointers instead of lightly rewritten?
- Was useful preexisting content preserved and re-homed instead of discarded?
- Is package-specific or subsystem-specific guidance located near its real owner when that improves clarity?
- Was the pass handled incrementally where appropriate instead of creating unnecessary churn?
- Were low-confidence changes suggested instead of silently applied?
- Is the operating mode used explicit?
- Is the severity summary explicit but still lightweight?
- Is the doc-role map reported in a consistent shape?
- Is there a clear `before -> after` summary of what changed?
- Are suggested-only restructures clearly separated from applied changes?
- Did the pass avoid aesthetic-only restructuring of already-stable docs?
- Can a reader follow context across the layers without guessing where to go next?
- Were optional larger restructures proposed before being applied?
- Is the resulting doc tree cleaner and easier to maintain than before?

## Final Question
- If this skill runs again on a similar repo, is the same document-ownership cleanup unlikely to be needed again?
