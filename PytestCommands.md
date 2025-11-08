# Pytest Commands and Aspects Documentation

This document summarizes **Pytest commands** organized into **10 aspects** of software development and testing.  
Each aspect includes **5 common commands** with their purpose or notes.

---

## 1. Basic Test Execution

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest` | Run all tests recursively (default). |
| `pytest test_app.py` | Run tests in a specific file. |
| `pytest -k "login"` | Run tests matching keyword “login”. |
| `pytest tests/unit/` | Run only tests under `tests/unit` folder. |
| `pytest -x` | Stop after the first test failure. |

---

## 2. Test Selection & Filtering

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest -k "not slow"` | Skip tests with “slow” in name. |
| `pytest -m "api"` | Run tests marked with `@pytest.mark.api`. |
| `pytest -m "not integration"` | Exclude marked tests. |
| `pytest -q` | Quiet mode (minimal output). |
| `pytest --maxfail=2` | Stop after 2 failures. |

---

## 3. Assertions & Failures Debugging

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest -v` | Verbose mode (show full test names). |
| `pytest --tb=short` | Short traceback on failure. |
| `pytest --tb=long` | Full detailed traceback. |
| `pytest --pdb` | Drop into interactive debugger on failure. |
| `pytest --maxfail=1 --disable-warnings` | Fail fast and ignore warnings. |

---

## 4. Fixtures & Parametrization

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest --fixtures` | List all available fixtures. |
| `pytest -k "fixture_name"` | Run tests using a specific fixture. |
| `pytest tests/ --setup-show` | Show fixture setup/teardown. |
| `pytest --setup-only` | Only show which fixtures would run. |
| `pytest --fixture-names` | Print all fixture names. |

---

## 5. Coverage & Reporting

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest --cov=app` | Measure test coverage for “app” folder. |
| `pytest --cov=app --cov-report=term-missing` | Show missing lines in terminal. |
| `pytest --cov-report=html` | Generate HTML coverage report. |
| `pytest --cov-append` | Append to previous coverage data. |
| `pytest --junitxml=report.xml` | Output results in JUnit XML (for CI). |

---

## 6. Performance & Parallel Testing

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest -n auto` | Run tests in parallel (needs `pytest-xdist`). |
| `pytest -n 4` | Run tests in 4 parallel workers. |
| `pytest --dist=loadscope` | Group tests by scope for faster runs. |
| `pytest --durations=10` | Show 10 slowest tests. |
| `pytest --max-worker-restart=1` | Limit restarts for flaky tests. |

---

## 7. Skipping, Expected Failures & Custom Marks

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest -m "not smoke"` | Skip tests marked “smoke”. |
| `pytest --strict-markers` | Enforce marker validation. |
| `pytest -k "xfail"` | Run tests marked `@pytest.mark.xfail`. |
| `pytest -rs` | Show summary of skipped/xfailed tests. |
| `pytest --markers` | List all custom markers. |

---

## 8. Configuration & Customization

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest -c pytest.ini` | Use a specific config file. |
| `pytest --rootdir=project/` | Define custom root directory. |
| `pytest --confcutdir=src/` | Limit conftest.py search to folder. |
| `pytest --basetemp=tmp/` | Use a custom temp directory. |
| `pytest --import-mode=importlib` | Control import mechanism for tests. |

---

## 9. Plugin Management & Extensibility

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest --trace-config` | Show plugin configuration tracing. |
| `pytest --trace` | Debug plugin or hook calls. |
| `pytest --help` | List all available plugin options. |
| `pytest --version` | Verify installed plugin versions. |
| `pytest --pdbcls=IPython.terminal.debugger:TerminalPdb` | Use IPython as debugger. |

---

## 10. CI/CD Integration & Automation

| Command | Purpose / Notes |
|----------|-----------------|
| `pytest --maxfail=1 --disable-warnings -q` | Minimal CI-friendly run. |
| `pytest --junitxml=results.xml` | Generate XML for Jenkins/GitHub Actions. |
| `pytest --cov --cov-report=xml` | Coverage report in XML for CI upload. |
| `pytest -n auto --dist=loadfile` | Parallelize in CI runners. |
| `pytest --color=yes --durations=10` | Pretty output + timing stats. |

---

## Configuration Files

### pytest.ini

```ini
[pytest]
addopts = -v --tb=short --strict-markers
testpaths = tests
markers =
    smoke: quick smoke tests
    regression: regression suite
    integration: integration tests
