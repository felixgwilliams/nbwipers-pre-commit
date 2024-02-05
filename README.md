# nbwipers-pre-commit

[![License:MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This mirror repository allows using [nbwipers](https://github.com/felixgwilliams/nbwipers) in [pre-commit](https://pre-commit.com/) without the need to compile with rust.

You can add the following to your `pre-commit-config.yaml` file to ensure that `nbwipers` or `nbstripout` is installed in your repo, in order to prevent Jupyter notebook outputs from being committed to version control.

```yaml
  - repo: https://github.com/felixgwilliams/nbwipers-pre-commit
    rev: v0.3.3
    hooks:
      - id: nbwipers-check-install
```
