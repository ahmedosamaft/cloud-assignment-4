# Cloud Computing — Task 4: CI/CD with Jenkins

Simple Python calculator with unit tests, wired up to a Jenkins pipeline.

## Project structure

- `calculator.py` — `Calculator` class (`add`, `subtract`, `multiply`, `divide`, `power`).
- `test_calculator.py` — unit tests using `unittest`.
- `requirements.txt` — Python dependencies (`pytest`).
- `Jenkinsfile` — declarative Jenkins pipeline.

## Run tests locally

With `unittest`:

```bash
python -m unittest -v
```

With `pytest`:

```bash
pip install -r requirements.txt
python -m pytest -v
```

## Jenkins pipeline

The `Jenkinsfile` defines a declarative pipeline that runs inside a `python:3.11-slim` Docker container with the following stages:

1. **Checkout** — clones the repository.
2. **Install Dependencies** — installs `pytest`.
3. **Run Unit Tests** — runs the test suite and produces a JUnit report (`test-results.xml`), which is published to Jenkins via the `junit` post step.

## Repository

https://github.com/ahmedosamaft/cloud-assignment-4
