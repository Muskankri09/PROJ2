# Node.js Backend Practice Suite — Scalable Server Patterns

A collection of standalone Node.js scripts demonstrating core backend
concepts: asynchronous programming patterns, the Streams API, the Cluster
module, and classic software design patterns.

## Contents

| File | Concept |
|---|---|
| `async-patterns.js` | Callbacks vs Promises vs async/await, `Promise.all` for concurrency |
| `streams-demo.js` | Readable → Transform → Writable stream pipeline |
| `cluster-demo.js` | Multi-core load distribution using the Cluster module + HTTP server |
| `patterns/singleton.js` | Singleton pattern (shared DB connection) |
| `patterns/factory.js` | Factory pattern (notification service creation) |
| `patterns/observer.js` | Observer pattern via Node's `EventEmitter` |
| `patterns/run-all.js` | Runs all three design pattern demos together |

## Running the demos

No external dependencies needed — pure Node.js core modules.

```bash
node async-patterns.js
node streams-demo.js
node cluster-demo.js       # open http://localhost:3000 and refresh a few times
node patterns/run-all.js
```

Or via npm scripts:
```bash
npm run async
npm run streams
npm run cluster
npm run patterns
```

## Notes
- `cluster-demo.js` forks up to 4 worker processes (capped for demo
  purposes) and load-balances an HTTP server across them — refreshing
  `http://localhost:3000` repeatedly shows different worker PIDs handling
  the request.
- Design patterns are intentionally kept dependency-free so the underlying
  mechanics (prototypes, closures, `EventEmitter`) are visible.
