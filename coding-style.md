Embed this into CLAUDE.md when starting new project to ensure it adheres to your coding style. 

## 1. Think Before Coding  

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**  
- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- Consolidate rather than proliferate — when two things do the same job, remove one.
- If you write 200 lines and it could be 50, rewrite it.
- Maximise code readability. Do not use one liner unless it is massively improve efficiency.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you find unrelated dead code, mention it, ask the user whether it should be removed, and follow what they said.
- If you find any imports that are not used, remove them.
- Always first check whether the code has been updated by user before updating. Do not work based on just memory. 
  
When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.

---  
**These guidelines are working if:** fewer unnecessary changes in diffs, fewer rewrites due to overcomplication, and clarifying questions come before implementation rather than after mistakes.
  
## Code style
  
- Prioritise readability over efficiency — clear variable names, straightforward control flow, no clever one-liners that obscure intent.
  
- Name variables after what they contain, not how they were derived or what type they carry.
  
- Comment code to explain what each logical block does. When writing or editing comments, run `/humanizer` to make them sound natural rather than AI-generated.
  
- Prefer well-established public APIs over custom implementations (e.g. `tempfile.TemporaryDirectory` over manual cleanup). Only use a library if it is widely used and actively maintained — avoid packages that solve one narrow problem.
  
- **Lean on the standard library.** Use `pathlib`, `hashlib`, `tempfile`, `argparse` rather than third-party wrappers for things Python already does well.

- Only import libraries that are used in the scripts. 
  
### Testing

- **Prefer real dependencies over mocks** when the one-off setup cost is modest. A real model that downloads once and caches locally is more reliable than a mock that hides real failure modes. Only mock at genuine system boundaries where real calls are expensive, non-deterministic, or have side effects (e.g. a live LLM API that bills per token).
- 
- **All changes must pass the unit test suite.** Run `.venv/bin/pytest code/` before considering a change done. If a change breaks a test, fix the code or update the test to reflect the new intended behaviour — do not skip or delete tests to make them pass.