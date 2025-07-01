Create an executable implementation document for: $ARGUMENTS

Write the plan to `implementation-plan.md` with this structure:

# Implementation Plan: $ARGUMENTS

## Agent Instructions
**IMPORTANT: Read these before starting implementation**

1. **Quality Gates**: Before EVERY commit:
   - Run `lint_fix` and resolve all issues
   - Run tests and ensure they pass
   - Fix any issues found, even if pre-existing

2. **Progress Tracking**: 
   - Mark each step with ✅ when complete
   - Add notes in [brackets] for any deviations
   - Update the "Current Status" section after each work session

3. **Adaptation Protocol**:
   - Follow the plan but use judgment
   - Document any necessary modifications in [brackets]
   - Flag significant changes for retrospective

## Current Status
- Last updated: [timestamp]
- Last completed step: [none]
- Active agent: [agent name/session]
- Blocked by: [none]

## Implementation Steps
[Insert the refined plan here with checkboxes]
- [ ] Step 1: ...
  - Testing: ...
- [ ] Step 2: ...
  - Testing: ...

## Handoff Instructions
To continue this implementation:
1. Read the full plan and agent instructions
2. Check "Current Status" to see where we are
3. Find the first unchecked [ ] item
4. Begin implementation from that point
5. Update status when stopping work

## Retrospective Notes
[Track significant decisions and deviations here]

---
Remember: Quality over speed. Test thoroughly. Document changes.
