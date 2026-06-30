---
name: symphony-mq-validation
description: Use when validating or maintaining the public Symphony MQ validation repo, including demo branches, merge-queue checks, auto-merge label examples, and lightweight GitHub workflow smoke tests.
---

# Symphony MQ Validation

Use this skill for public-safe validation work in the `symphony-mq-validation` repo.

## Workflow

1. Treat the repo as a public merge-queue and automation smoke-test fixture.
2. Keep demo files synthetic and small.
3. Keep workflow examples free of private repository names, private issue text, tokens, and provider identifiers.
4. When changing GitHub Actions examples, verify the trigger, permissions, and token behavior from the file itself.
5. Prefer read-only checks unless the user explicitly asks for a workflow change.

## Validation

Run these checks when relevant:

```bash
git status --short
find . -maxdepth 3 -type f -not -path './.git/*' -print
```

For workflow edits, inspect:

```bash
sed -n '1,220p' .github/workflows/ci.yml
sed -n '1,220p' .github/workflows/auto-merge-on-label.yml
```
