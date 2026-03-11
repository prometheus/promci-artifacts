# promci-artifacts

GitHub Actions for artifact persistence between jobs

## Usage

```yaml
jobs:
  build:
    steps:
      ...
      - run: make build
      - uses: prometheus/promci-artifacts/save@<hash> # v0.1.0
  publish:
    needs: [build]
    steps:
      ...
      - uses: prometheus/promci-artifacts/restore@<hash> # v0.1.0
      - run: make publish
```
