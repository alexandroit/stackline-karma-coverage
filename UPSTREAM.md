# Upstream review

Based on karma-coverage@2.2.1, source [55eb8a85f8243af3ae9cf75460a780fc5c71761f](https://github.com/karma-runner/karma-coverage/commit/55eb8a85f8243af3ae9cf75460a780fc5c71761f). The registry gitHead source manifest contains the previous semantic-release version, but every upstream published runtime file matches this commit byte-for-byte. Only package metadata differs in the upstream tarball, whose integrity was checked independently.

## Issue triage (2026-09-29)

- [#490: includeAllSources behavior](https://github.com/karma-runner/karma-coverage/issues/490): Execute original preprocessor/reporter/coverage-map assertions and instrument a packed-consumer module.
- [#496: Memory and browser disconnect](https://github.com/karma-runner/karma-coverage/issues/496): Retain original coverage behavior and avoid an unsupported blanket memory-fix claim.

No upstream maintainer was contacted. Runtime files and original license/authorship are retained. Development tooling uses Node24; package engine declarations remain unchanged.

## Verification

`npm ci --ignore-scripts`, `npm test`, `npm run test:package`, `npm audit --audit-level=low`. Packed tests install the actual archive and exercise the exported plugin. Publication uses the exact CI tarball only after CI and CodeQL succeed.
