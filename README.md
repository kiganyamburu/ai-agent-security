# AI Agent Security Submission

This repository contains a starter submission for the JED Attack competition. The goal is to provide an `attack.py` file with an `AttackAlgorithm` class that searches for replayable multi-step failures in a tool-using agent.

## Main Files

- `attack.py`: submission entrypoint loaded by the evaluator.
- `getting-started-notebook.ipynb`: starter notebook used to generate and test the submission template.
- `aicomp_sdk/`: competition SDK and local sandbox utilities.
- `kaggle_evaluation/`: evaluator code used to load and replay submissions.

## What The Submission Does

The current `AttackAlgorithm` implementation follows the starter notebook pattern:

- resets the sandbox between attempts,
- sends a small set of candidate user-message chains,
- replays each chain against the environment,
- records any candidate whose trace satisfies the competition predicates.

## Local Run

If the repository dependencies are installed, you can run the smoke test with:

```bash
python attack.py
```

The bundled smoke test uses the local fixture-backed sandbox and prints the number of findings it discovers.

## Submission Notes

- The evaluator expects a top-level `attack.py` file.
- The class name must be `AttackAlgorithm`.
- The class must inherit from `aicomp_sdk.attacks.AttackAlgorithmBase`.
- The `run()` method must return a `list[AttackCandidate]`.

## Environment

The SDK depends on the competition environment and its Python packages. If local execution fails because a dependency is missing, install the competition requirements before rerunning the smoke test.
