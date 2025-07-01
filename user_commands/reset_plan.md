Think hard about resynchronizing with the plan: $ARGUMENTS

Perform a comprehensive plan-to-reality audit:

## 1. Progress Assessment
Review the implementation plan and determine:
- Which steps are marked complete (✅) in the plan
- Which unmarked steps appear to be actually implemented
- Use grep/ag to verify each claimed implementation exists
- Check git log to understand recent work outside the plan

## 2. Codebase Scan
For each repository involved:
- Run tests to establish current working state
- Run lint_fix to identify quality issues
- Use subagents to deep-dive any complex divergences
- Check for uncommitted changes that affect the plan

## 3. Divergence Analysis
For each difference between plan and reality:
- **What**: Describe the divergence precisely
- **Why**: Likely reason it happened (if discoverable from git history)
- **Impact**: How it affects remaining plan steps
- **Recommendation**: 
  - ✅ Keep divergence (it's an improvement)
  - ⚠️  Refactor to match plan
  - 🔄 Update plan to reflect new approach

## 4. Pre-continuation Checklist
- [ ] Critical fixes needed before continuing
- [ ] Plan updates required
- [ ] Tests that need updating
- [ ] Documentation gaps to fill

## 5. Recommended Next Steps
Based on the audit, suggest:
1. Immediate fixes (if any)
2. Plan modifications (if needed)
3. Best step to resume from

Output a clear status report with actionable recommendations.
