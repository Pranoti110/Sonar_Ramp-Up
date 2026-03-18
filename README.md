
# SonarQube Cloud (SonarCloud) – Node.js sample with GitHub Actions

This is a minimal Node.js repo you can push to GitHub to **demonstrate SonarQube Cloud analysis** via **GitHub Actions**. It includes:

- A tiny code sample (`src/`) and a Jest test (`tests/`) that produces coverage.
- `sonar-project.properties` configured for SonarQube Cloud.
- A ready-to-run workflow in `.github/workflows/sonar.yml` using the official **SonarQube Scan** GitHub Action.

## Quick start

1. **Create a project on SonarQube Cloud** (aka SonarCloud) and note your **organization key** and **project key**.
2. In this repo, edit `sonar-project.properties` and replace the placeholders for `sonar.organization` and `sonar.projectKey`.
3. Commit & push to GitHub.
4. In your GitHub repository: **Settings → Secrets and variables → Actions → New repository secret**:
   - Name: `SONAR_TOKEN`  
   - Value: your token from SonarQube Cloud.
5. Trigger the workflow by pushing a commit or opening a PR. After it runs, visit your project in SonarQube Cloud to see the results.

> If you use a self‑hosted runner, ensure `unzip` and `curl` or `wget` are installed.

## Local development

```bash
nvm use 20  # or Node.js 20+
npm ci
npm test -- --coverage
```

## Notes
- The workflow runs tests, collects coverage (`coverage/lcov.info`), then runs the Sonar scan.
- Update the action version in `.github/workflows/sonar.yml` to the latest stable if needed.
