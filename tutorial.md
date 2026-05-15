Fork, clone

```Bash
mkdir -p .github/workflows
touch .github/workflows/security-pipeline.yml
```

```YAML
name: Security Pipeline

on:
  push:
  pull_request:

jobs:
  semgrep:
    name: Semgrep Scan
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Run Semgrep
        uses: returntocorp/semgrep-action@v1
        with:
          config: p/security-audit
```
```Bash
git add .
git commit -m "Add Semgrep security pipeline"
git push
```

```YAML
name: Security Pipeline

on:
  push:
  pull_request:

jobs:
  semgrep:
    name: Semgrep Scan
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Run Semgrep
        uses: returntocorp/semgrep-action@v1
        with:
          config: >
            p/javascript
            p/typescript
            p/nodejs
            p/owasp-top-ten
```