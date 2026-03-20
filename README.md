# Rob Pike's 5 Rules of Programming

An agent skill that prevents premature optimization by enforcing measurement-driven development.

## Install

```bash
npx skills add tmdgusya/robpike
```

## What This Does

This skill acts as a **circuit breaker** for AI coding agents. When the agent is about to optimize code without measurement data, the skill intercepts and redirects to Pike's discipline: measure first, then decide.

It is a thinking discipline, not a tooling workflow. No specific profiler or benchmark tool is prescribed — only the questions you must answer before changing code for performance.

## The 5 Rules

1. **You can't tell where a program is going to spend its time.** Bottlenecks occur in surprising places. Don't guess — prove it.
2. **Measure.** Don't tune for speed until you've measured. Even then, don't unless one part of the code overwhelms the rest.
3. **Fancy algorithms are slow when n is small, and n is usually small.** Big-O doesn't matter when constants dominate.
4. **Fancy algorithms are buggier than simple ones.** Use simple algorithms and simple data structures.
5. **Data dominates.** Choose the right data structures and the algorithms become self-evident. "Write stupid code that uses smart objects."

> Pike's rules 1 and 2 restate Tony Hoare's famous maxim "Premature optimization is the root of all evil."
>
> Ken Thompson rephrased Pike's rules 3 and 4 as "When in doubt, use brute force."
>
> Rule 5 was previously stated by Fred Brooks in *The Mythical Man-Month*, often shortened to "write stupid code that uses smart objects."

## When It Triggers

The skill activates when the agent encounters words like "optimize", "slow", "bottleneck", "speed up", "make faster", "too slow", or "performance" — or when the agent is about to suggest a performance optimization without evidence.

### Example Situations

**"This API is slow, fix it"** → The agent asks: which endpoint? what's the latency? is it the handler, the DB query, or the network?

**Agent spots an O(n²) loop** → Instead of rewriting with a hash map: what's n? If it's 20 items, the simple version is clearer and likely faster.

**"Should I add Redis for caching?"** → Does this path actually dominate runtime? Measure without the cache first.

**Agent is about to suggest a trie / skip list / bloom filter** → Is a simple array enough? What's n?

## License

[MIT](LICENSE)
