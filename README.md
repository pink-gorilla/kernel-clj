# Clojurescript Kernel used in pink gorilla notebook.

# manual tests

- You need to have clj installed.
- run ./test.sh and wait for the figwheel terminal window to appear
- copy expressions from test.md and eval them for testing

## Unit Tests
```bash
clj  -A:figwheel -C:test  --build test --repl
```

## Tests - CI

```bash
clj -A:figwheel -m klipse.test-runner-ci
```
