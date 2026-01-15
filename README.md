# drift-config

Central configuration for [repo-drift](https://github.com/chrismlittle123/repo-drift) scanning across the `chrismlittle123-testing` organization.

## Usage

Scan all repos in the org:

```bash
drift scan --org chrismlittle123-testing
```

Scan a single repo:

```bash
drift scan --org chrismlittle123-testing --repo cmt-ts-code-test
```

## Configuration

See [drift.config.yaml](./drift.config.yaml) for:

- **Integrity checks**: Files that must match approved versions
- **Discovery patterns**: Find new files that may need protection
- **Scans**: Commands to run against each repo

## Adding Protected Files

To protect a file across all repos:

1. Add the golden version to `approved/` folder
2. Add an entry to `drift.config.yaml`:

```yaml
integrity:
  protected:
    - file: .github/workflows/ci.yml
      approved: approved/ci.yml
      severity: high
```
