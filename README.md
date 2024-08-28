# nbwipers-pre-commit

[![License:MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This mirror repository allows using [nbwipers](https://github.com/felixgwilliams/nbwipers) in [pre-commit](https://pre-commit.com/) without the need to compile with rust.

You can add the following to your `pre-commit-config.yaml` file to ensure that `nbwipers` or `nbstripout` is installed in your repo, in order to prevent Jupyter notebook outputs from being committed to version control.

```yaml
  - repo: https://github.com/felixgwilliams/nbwipers-pre-commit
    rev: v0.4.0
    hooks:
      - id: nbwipers-check-install
```

If you want to check that your notebooks are clean in your working directory, you can use the `nbwipers-check-wd` hook.
This is probably overkill.

```yaml
  - repo: https://github.com/felixgwilliams/nbwipers-pre-commit
    rev: v0.4.0
    hooks:
      - id: nbwipers-check-wd
```

If use the `check-large-files` hook from [pre-commit](https://github.com/pre-commit/pre-commit-hooks), you may get "false positives", since it checks the sizes not-clean notebook files in the working directory. You can use the version included in this repository, which cleans notebooks before checking their size.

```yaml
  - repo: https://github.com/felixgwilliams/nbwipers-pre-commit
    rev: v0.4.0
    hooks:
      - id: nbwipers-large-files
```
