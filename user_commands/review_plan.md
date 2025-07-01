Think hard about reviewing and refining: $ARGUMENTS

Perform a comprehensive review:

1. **Code Alignment Check**
   - Compare the plan against the actual codebase
   - Verify all referenced files, functions, and dependencies exist
   - Use grep or ag to confirm assumptions about current implementation

2. **Issue Detection**
   - Identify potential conflicts or breaking changes
   - Flag any outdated patterns or deprecated APIs
   - Check for ripple effects - how each change impacts others

3. **Pre-implementation Verification**
   - List any setup steps needed before implementation
   - Confirm all required tools/libraries are available
   - Consider using subagents to verify complex integrations

4. **Plan Refinement**
   - Update the plan to address all findings
   - Ensure each change supports the overall vision
   - Reorder steps if needed to minimize risk

Output:
- A "Findings" section with any issues discovered
- An "Updated Plan" incorporating all improvements
- A "Pre-implementation Checklist" if setup is needed

Focus on making the implementation as smooth as possible.
