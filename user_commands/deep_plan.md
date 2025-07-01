Think hard about creating an implementation plan for: $ARGUMENTS

Structure the plan as follows:
1. Order tasks to enable incremental testing - each step should be verifiable before proceeding
2. Group changes into logical commits (aim for focused, atomic commits rather than line counts)
3. Include a one-line commit message for each commit
4. Add validation steps after each significant change

For any unclear implementations:
- First outline your approach
- Use web_search to verify best practices and syntax
- For complex implementation details, consider using subagents to explore specific aspects
- Integrate findings into the plan

After creating the initial plan, review it to:
- Ensure each step sets up the next for success
- Verify all library functions and APIs exist
- Confirm the sequence minimizes dependencies
- Check alignment with any project conventions in CLAUDE.md

Output the plan in a clear, numbered format.

Note: For long implementation sessions, I may suggest using /compact between major phases to maintain context clarity.
