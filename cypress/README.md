Cypress tests for ChurchCRM

Overview
- `cypress/e2e/` — test specs; group by feature (e.g., `auth/`, `family/`, `donations/`).
- `cypress/fixtures/` — static test data (move from `cypress/data/`).
- `cypress/support/` — global support files and custom commands.
- `cypress/configs/` — environment-specific config files (e.g., `ci.config.ts`, `docker.config.ts`).
- `cypress/videos/`, `cypress/screenshots/`, `cypress/downloads/` — runtime artifacts (gitignored).

Running tests (recommended)
- Open interactive runner (local):
  ```bash
  npm run cypress:open
  ```
- Run headless (local):
  ```bash
  npm run cypress:run
  ```
- Run CI (headless, CI config):
  ```bash
  npm run cypress:run:ci
  ```
- Run using Docker-specific config:
  ```bash
  npm run cypress:run:docker
  ```

Quick migration notes
- Move `cypress/data/` → `cypress/fixtures/` and update usages of `cy.fixture()` accordingly.
- Consolidate Docker/CI variants under `cypress/configs/` (use `--config-file` to point to them).
- Remove the legacy `cypress.json` file in favor of `cypress.config.ts` (Cypress v10+).

Best practices
- Group specs by feature and add tags (e.g., `@smoke`) to allow fast subset runs.
- Keep secrets out of repo; use `cypress.env.json` or CI environment variables.
- Ensure `cypress/videos/`, `cypress/screenshots/`, and `cypress/downloads/` are in `.gitignore`.

Contact
If you need help migrating or reorganizing tests, open an issue or contact the QA maintainer.
