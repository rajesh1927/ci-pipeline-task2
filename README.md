# Simple Github CI Pipeline Task

A simple Node.js application demonstrating a basic Continuous Integration (CI) pipeline using GitHub Actions.

## Technologies Used

* Node.js
* JavaScript
* Jest
* GitHub Actions

## Project Structure

```text
nodejs-demo-app/
├── .github/
│   └── workflows/
│       └── ci.yml
├── app.js
├── package.json
├── package-lock.json
├── test/
│   └── app.test.js
├── Dockerfile
├── .dockerignore
└── README.md
```

## Run Locally

Install dependencies:

```bash
npm install
```

Start the application:

```bash
npm start
```

## Run Tests

Run the test suite using:

```bash
npm test
```

## CI Pipeline

This project uses GitHub Actions for Continuous Integration.

The workflow is located at:

```text
.github/workflows/ci.yml
```

The CI pipeline runs automatically when:

* Code is pushed to the `main` branch
* Code is pushed to the `develop` branch
* A pull request is created or updated against `main`
* A pull request is created or updated against `develop`

## CI Pipeline Steps

The GitHub Actions workflow performs the following steps:

1. Checks out the source code.
2. Sets up Node.js 20.
3. Installs dependencies using `npm ci`.
4. Runs the automated tests using `npm test`.

If the tests pass, the GitHub Actions workflow completes successfully. If a test fails, the CI pipeline fails and the developer can investigate the issue before merging the code.

## CI Workflow

```yaml
name: Node.js CI

on:
  push:
    branches:
      - main
      - develop
  pull_request:
    branches:
      - main
      - develop

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: npm

      - name: Install dependencies
        run: npm ci

      - name: Run tests
        run: npm test
```

## Expected Result

A successful GitHub Actions run should show all tests passing.

## Repository

GitHub Repository:

`https://github.com/rajesh1927/ci-pipeline-task2`

