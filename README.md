## Exercises

Each exercise has a `README.md` explaining the fixes applied.

---

## 🚀 Testing Procedure

### Local Testing

For each exercise, you can launch the stack locally and verify its functionality.

Hint : Do not bother to launch it manually, check [Automated Tests (GitHub Actions)](#automated-tests-github-actions) to see how it is automatically tested on GitHub.

**Prerequisites**:

- Docker and Docker Compose installed.

**Launch an exercise**:

```bash
cd exoN

cp .env.example .env        # create the .env file with environment variables

docker compose up -d        # start the stack in detached mode

docker compose ps           # check that all services are up and healthy
docker compose logs         # check for any errors during startup

curl http://localhost:XXXX  # test the main application endpoint (replace XXXX with the correct port)

docker compose down -v      # stop the stack and remove volumes
```

---

## Automated Tests (GitHub Actions)

Each exercise has a GitHub Actions workflow that automatically tests the stack on every push to `main`.

### Workflow Structure

Each workflow (`exo1.yml`, `exo2.yml`, `exo3.yml`):

1. **Checkout**: Retrieves the code.
2. **Prepare .env**: Creates the configuration file with environment variables.
3. **Bring up compose**: Launches the stack in detached mode.
4. **Healthcheck**: Waits for services to be ready, then tests HTTP endpoints.
5. **Shutdown**: Stops and cleans up the stack.

### View Results

1. Access: **GitHub** → **Actions** → select the workflow (Exercise 1, 2, or 3).
2. Logs display:
   - Image downloads.
   - Network and volume creation.
   - Container startup status.
   - HTTP test results (curl).
3. **Success**: All tests pass (exit code 0).
4. **Failure**: A test fails (exit code 1) → check logs for debugging.

### Manually Trigger a Test

1. Access: **GitHub** → **Actions**.
2. Select the workflow (e.g., "Exercise 1").
3. Click **"Run workflow"** → **"Run workflow"**.
4. Wait for completion and check the logs.

---

## Project Structure

```
alt-devops/
├── README.md
├── .github/
│   └── workflows/
│       ├── exo1.yml         # CI test for exercise 1
│       ├── exo2.yml         # CI test for exercise 2
│       └── exo3.yml         # CI test for exercise 3
├── exo1/
│   ├── compose.yml          # Docker Compose configuration
│   ├── .env                 # Environment variables
│   └── README.md            # Details of corrections
├── exo2/
│   ├── compose.yml
│   ├── .env
│   └── README.md
└── exo3/
    ├── compose.yml
    ├── .env
    └── README.md
```
