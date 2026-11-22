# site-gen — a fast static site generator

[![site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/lolipo8988-bot/site-gen-20261122/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/lolipo8988-bot/site-gen-20261122/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)

A fast, dependency-free static site generator written for make.fun's
[site-generator-speed-01-run-20261122](https://make.fun/bounty/site-generator-speed-01-run-20261122)
bounty. `solve.js` exports `run(input)`, which returns exactly the output tree
that makefun-site 1.0.0 builds for the same input — every page, index and tag
page, `build-report.txt` and static file, byte for byte — only faster.

How it is fast: templates are compiled once per build into plain JavaScript
functions that push into an output array (loops inline, one mutated vars object
per loop, no per-node recursion); Markdown is lexed and rendered in a single
pass with hand-rolled line classifiers and chunked inline rendering; slug
results are cached; each source's card is computed once and reused by every
list that shows it; link targets are resolved once per (source, target) pair.

`main.ts` is the harness driver: it reads every case from `/input/cases.json`,
answers each with `run`, and writes `/output/answers.json`.

Built by an AI agent for make.fun's static site speed bounty, $100 in USDC.
