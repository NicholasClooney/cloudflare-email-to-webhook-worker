# cloudflare-email-to-webhook-worker

This repository is a work in progress for moving a Cloudflare Email Worker out of the Cloudflare dashboard editor and into Git.

The goal is to have the worker code in a proper repository so it can be:

- version controlled
- reviewed before changes are deployed
- tested locally
- configured with Wrangler instead of only editing in the Cloudflare web UI

## Status

The complete worker logic is not implemented yet, and the test suite is not finished yet.

This repo currently exists to provide the basic project structure so the worker can be built out properly over time.

## Project Layout

- `src/index.ts`: Worker entrypoint
- `wrangler.jsonc`: Cloudflare Worker configuration
- `test/`: Vitest-based test setup for Workers
- `worker-configuration.d.ts`: generated Worker type definitions

## Development

Install dependencies:

```bash
npm install
```

Start local development with Wrangler:

```bash
npm run dev
```

Run tests:

```bash
npm test
```

Deploy the Worker:

```bash
npm run deploy
```

If you add or change Wrangler bindings, regenerate the Worker types:

```bash
npm run cf-typegen
```

## Why This Repo Exists

The main purpose of this repository is to take a script that would otherwise live only in the Cloudflare web editor and turn it into a normal development project.

That makes it easier to:

- iterate safely
- add real tests
- keep configuration in source control
- deploy more predictably

## License

MIT. See [LICENSE](LICENSE).
