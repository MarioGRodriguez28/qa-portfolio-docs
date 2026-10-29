# QA Automation Portfolio

Mario Rodríguez, QA Automation Engineer (freelance).

[mariogrodriguez.com](https://mariogrodriguez.com) · [LinkedIn](https://linkedin.com/in/mariogrm) · mariog.rodriguezm@gmail.com · [Book a call](https://calendly.com/mariog-rodriguezm)

This repository is the index of my public QA work. Every project below is standalone: clone it, run `npm install && npm test`, and read the code.

## Projects

| Project | What it is | Stack |
|---|---|---|
| [playwright-e2e-framework](https://github.com/MarioGRodriguez28/playwright-e2e-framework) | End-to-end and API test framework: page objects, custom fixtures, tagged suites and a pipeline that runs smoke tests on pull requests and the full suite on `main` and nightly, with reports and traces as artifacts. | Playwright, TypeScript, GitHub Actions |
| [qa-audit-agent](https://github.com/MarioGRodriguez28/qa-audit-agent) | CLI that audits an API from its OpenAPI spec and a web page in a real browser, scores each from 0 to 100 and writes a client-readable report. The AI summary is optional and the checks do not depend on it. | Node.js, Playwright, axe-core, Jest |
| [qa-eval-bench](https://github.com/MarioGRodriguez28/qa-eval-bench) | Scores how many bugs a test suite catches by planting small bugs in correct code, one at a time, so tests written by people or by AI models can be compared on the same footing. | Node.js, mutation testing |
| [api-testing-suite](https://github.com/MarioGRodriguez28/api-testing-suite) | REST API test suite: CRUD, edge cases, error handling, response times and concurrent requests. | Jest, Supertest |
| [qa-test-helpers](https://github.com/MarioGRodriguez28/qa-test-helpers) | Small library of testing utilities: fluent request builder, fixture generators, validators and reporters. No runtime dependencies. | Node.js, Jest |
| [performance-load-tests](https://github.com/MarioGRodriguez28/performance-load-tests) | k6 scripts for smoke, load, stress, spike and soak scenarios with thresholds on p95, p99 and error rate, runnable on demand from CI. | k6 |

All of them run in GitHub Actions on every push.

## What each one shows

**qa-audit-agent** is the most complete piece. It turns QA checks into something a client can read: a score, a prioritised list of findings and a plain-language summary. It also treats the tool itself as a security surface: it refuses private addresses, validates every redirect hop, and sends the model only finding metadata. The redirect handling came from a bug I found by testing it, and there are regression tests for it.

**qa-eval-bench** answers a question I care about: a test that passes proves little, so how many bugs does it actually catch? On the included tasks, tests that only cover the happy path catch between 38% and 70% of the planted bugs and thorough ones between 90% and 100%. The scoring does not use a model, so it is a fair way to compare tests written by people or by AI models.

**playwright-e2e-framework** is the structure I use to start a suite for a team: selectors only in page objects, a signed-in session fixture so only the login tests use the login screen, `@smoke` tags for fast pull request feedback, and a pipeline that also runs the full suite every weekday morning. It ran five times in a row with no failures before I published it.

**api-testing-suite** is the baseline: what a solid automated API check looks like, with a coverage threshold enforced in CI.

**qa-test-helpers** shows design rather than test volume: small, composable pieces that other test code can reuse. Writing its unit tests also exposed two real bugs in the library, which are fixed.

**performance-load-tests** covers the non-functional side, with explicit pass or fail thresholds instead of just printing numbers.

## Working together

I take freelance QA automation work: API and end-to-end test suites, CI pipelines, and quality audits of existing products. The easiest way to start is a short call: [calendly.com/mariog-rodriguezm](https://calendly.com/mariog-rodriguezm).

## License

MIT
