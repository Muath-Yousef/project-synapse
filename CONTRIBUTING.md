# Contributing to Project Synapse

Thank you for helping improve Project Synapse. Contributions should strengthen reproducibility, safety, architecture clarity, or evidence quality.

## Good contribution areas

- correct or clarify architecture and data contracts;
- add sanitized, deterministic test fixtures;
- improve PSM setup and reproduction instructions;
- add versioned detection rules with positive and negative tests;
- improve benchmark scripts and machine-readable result output;
- document failure, replay, backup, restore, or rollback behavior;
- correct citations, limitations, or maturity labels.

## Before opening a change

1. Confirm that all data is synthetic, sanitized, or explicitly authorized for public use.
2. Do not include credentials, infrastructure addresses, client identifiers, findings, raw reports, or private evidence.
3. Label each capability as designed, implemented, integrated, measured, publicly reproducible, or future work.
4. Keep destructive or sensitive response logic dry-run-first and human-approved.
5. Add the input, expected output, acceptance criterion, and limitation for any new test or benchmark.

## Security and responsible use

Use Project Synapse only on systems you own or are explicitly authorized to test. Controlled exploitation belongs in an isolated lab. Do not submit offensive capability that lacks a defensive learning purpose, scope boundary, teardown procedure, and evidence plan.

For a vulnerability in Project Synapse itself, follow [SECURITY.md](SECURITY.md) instead of opening a public issue with sensitive details.

## Pull request checklist

- [ ] the change has a narrow, documented purpose;
- [ ] tests or review steps are included;
- [ ] examples use reserved domains/addresses and synthetic data;
- [ ] no secret or personal data is present in the current tree or patch;
- [ ] claims match the [evidence register](docs/evidence-register.md);
- [ ] safety, rollback, and failure behavior are documented where relevant;
- [ ] third-party licenses and attributions are preserved.

## License

By contributing, you agree that your contribution is licensed under the repository's [Apache License 2.0](LICENSE). Third-party components remain subject to their own licenses.
