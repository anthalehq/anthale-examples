# How to Contribute

Thank you for improving `anthale-examples`.

This repository is the canonical source of truth for Anthale example code. Documentation should reference this repository and copy code from here, not the other way around.

## Before You Start

1. Follow our [`Code of Conduct`](./.github/CODE_OF_CONDUCT.md).
2. Search existing issues and pull requests before opening a new one.
3. Report vulnerabilities privately using our [`Security Policy`](./.github/SECURITY.md).
4. Keep examples realistic: every example should explain the attack path and the defended path, not only the happy path.
5. Put language-agnostic assets in `examples/<slug>/shared/` and runnable implementations in `examples/<slug>/variants/<language>-<framework>/`.

## Quick-Start Workflow

1. Fork the repository.
2. Clone your fork.

```bash
git clone git@github.com:<your-username>/anthale-examples.git
cd anthale-examples
```

3. Install the root tooling.

```bash
make install
```

4. Create a branch from the default branch.

```bash
git checkout -b feat/<short-name>
```

5. Make your changes.
6. Run the repository checks from the root of the project.

```bash
make format
make lint
make test
```

7. If you changed a runnable variant, also run that variant's local install and test commands and update its `README.md` and `.env.example` as needed.
8. Commit your changes with a descriptive conventional commit message.

```bash
git add .
git commit -m "feat(secure-chatbot): add audited refusal example"
```

10. Push your branch and open a pull request using the repository template.

## Repository Rules

- Each example should document: what it builds, the attack, the insecure flow, the secure flow, the Anthale controls used, how to run it, and how to test the attack.
- Shared diagrams, datasets, threat models, screenshots, and attack transcripts belong in the example's `shared/` directory.
- Each variant should be runnable and should include code, a local README, `.env.example`, install and run commands, a test command, Anthale integration config, and variant-specific notes.
- Use sortable variant names in the form `<language>-<framework>`.

## Commit Message Guidelines

This repository follows [Conventional Commits](https://www.conventionalcommits.org).

- Use a clear type such as `feat`, `fix`, `docs`, `refactor`, `test`, `build`, `ci`, or `security`.
- Use a scope when it helps identify the affected example or package, for example `feat(secure-rag-assistant): add provenance labels`.
- Write the description in the imperative mood, for example `add`, `update`, or `fix`.
- Mark incompatible behavior changes with `!` or a `BREAKING CHANGE:` note in the commit body.

## Pull Request Guidelines

- Keep pull requests focused. One logical change is easier to review and safer to merge.
- Use the pull request template and fill in the scope, related issues, and checklist.
- Reference related issues with `Closes #123` or `Related to #123` where appropriate.
- Update docs, shared assets, tests, and generated index files when the change affects them.
- For new examples or variants, include the full security narrative: system goal, attack, insecure flow, secure flow, controls used, and test instructions.
- Do not merge documentation-only copies of code that is not already present in this repository.

## Tooling

The root project exposes `make` wrappers for the core repository checks.

- `make install`: installs root repository tooling.
- `make format`: formats Markdown, YAML, JSON, and other Prettier-managed files.
- `make lint`: checks formatting without modifying files.
- `make test`: validates repository structure and example expectations.

Thank you for keeping Anthale examples accurate, runnable, and safe to reuse.
