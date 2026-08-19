# github-actions-lab

CSE233 Agile Software Engineering — Lab 9 (Introduction to GitHub Actions) and
Lab 10 (More on GitHub Actions).

**Meena Maged Abdo Mekhaiel — 1900694**

## What's here

```
.github/workflows/
  hello.yml      # Lab 9 — final state (Exercise 3: Action Basics Demo)
  pytest.yml     # Lab 10 — final state (Exercise 3: matrix + junit report artifact)
scripts/
  math_utils.py       # add / subtract
  test_math_utils.py  # pytest tests for both
_versions/       # every intermediate version, so each exercise can be replayed
  hello-ex1.yml  hello-ex2.yml  hello-ex3.yml
  pytest-ex1.yml pytest-ex2.yml pytest-ex3.yml
```

`_versions/` is a study aid, not part of the lab. Copy the version you need over the
file in `.github/workflows/`, then commit and push — that push is what triggers the run
you screenshot.

## Running the tests locally

```bash
pip install pytest
pytest -v scripts/
```

Both tests pass locally; `from math_utils import add, subtract` resolves because pytest
puts the test file's own directory (`scripts/`) on `sys.path` — there is no `__init__.py`
in `scripts/`, and adding one would break that import.
