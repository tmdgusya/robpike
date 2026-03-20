# Agent Skills

Thinking disciplines for AI coding agents. Skills that enforce good engineering habits — not tooling workflows, but decision frameworks.

## Install

```bash
# Install all skills
npx skills add tmdgusya/robpike

# Install a specific skill
npx skills add tmdgusya/robpike --skill rob-pike
npx skills add tmdgusya/robpike --skill systematic-debugging
```

## Skills

### rob-pike

Rob Pike's 5 Rules of Programming — prevents premature optimization by enforcing measurement-driven development.

**Triggers on:** "optimize", "slow", "performance", "bottleneck", "speed up", "make faster", "too slow"

The 5 Rules:

1. **You can't tell where a program is going to spend its time.** Bottlenecks occur in surprising places. Don't guess — prove it.
2. **Measure.** Don't tune for speed until you've measured. Even then, don't unless one part of the code overwhelms the rest.
3. **Fancy algorithms are slow when n is small, and n is usually small.** Big-O doesn't matter when constants dominate.
4. **Fancy algorithms are buggier than simple ones.** Use simple algorithms and simple data structures.
5. **Data dominates.** Choose the right data structures and the algorithms become self-evident. "Write stupid code that uses smart objects."

> Pike's rules 1 and 2 restate Tony Hoare's famous maxim "Premature optimization is the root of all evil." Ken Thompson rephrased rules 3 and 4 as "When in doubt, use brute force." Rule 5 was previously stated by Fred Brooks in *The Mythical Man-Month*.

### systematic-debugging

Enforces a strict reproduce-first, root-cause-first, failing-test-first debugging workflow. No guessing, no shotgun fixes.

**Triggers on:** any bug, test failure, or unexpected behavior

Hard gates — no exceptions:

1. Reproduce or make observable before fixing
2. State a root-cause hypothesis before fixing
3. Create a failing test before fixing
4. Verify one hypothesis at a time
5. No "while I'm here" refactoring during fixes
6. Three failed fix attempts → suspect structural issues

Includes reference guides for root-cause tracing, defense-in-depth validation, condition-based waiting (flaky test elimination), and a test polluter bisection script.

## License

[MIT](LICENSE)
