---
type: assignment
date: 2026-04-05T0800-0400
title: Project 3 -- A Math Transformer
jupyter: /static_files/assignments/project3.ipynb
colab: https://colab.research.google.com/github/DL4DS/sp2026/blob/main/static_files/assignments/project3.ipynb
hide_from_announcements: false
published: true
due_event: 
    type: due
    date: 2026-04-17T23:59:00-5:00
    description: 'Project 3 due'
late_due_event:
    type: due
    date: 2026-04-19T23:59:00-5:00
    description: 'Project 3 late due'
---
## Project 3 -- Train a Math Transformer

Train an attention-based **decoder-only transformer** to evaluate math expressions involving positive integers, addition, and parentheses. The model must produce step-by-step reductions of parenthesized sub-expressions until a final integer result is reached.

Turn in on GradeScope.

## Grading Rubric

**Total Points: 100**

### Part 0: Notebook Submission (5 points)

| Test | Points | Description |
|------|--------|-------------|
| Notebook exists | 5 | `project.ipynb` must be present in the submission |

### Part 1: Benchmark Results (35 points)

Students must report benchmark accuracy results in their notebook for all combinations of `n` (number of nested operations) and `input_digits`:

| n | input_digits |
|---|-------------|
| 2 | 1, 2, 3 |
| 3 | 1, 2, 3 |
| 4 | 1, 2 |
| 5 | 1, 2 |

<br>

| Test | Points | Description |
|------|--------|-------------|
| Benchmark parsing | 5 | All 10 required (n, input_digits) entries are present in the notebook. Results should be formatted in a table with columns for n, input_digits, and accuracy. |
| Benchmark accuracy | 30 | Each of the 10 entries is scored by comparing the reported benchmark accuracy against the actual accuracy produced by `predict.py`. Up to 3 points per entry. Full credit if the absolute difference is less than 5%; zero credit if the difference exceeds 8%. *Hidden until after grades are published.* |

### Part 2: Model Weights (5 points)

| Test | Points | Description |
|------|--------|-------------|
| Saved model files | 5 | At least one `.pt` file must be present and loadable via `torch.load()` with `weights_only=True`. |

### Part 3: Prediction Accuracy (55 points)

A `predict.py` script must accept an input file and print predictions to stdout. Each output line should start with `(`.

| Test | Points | Min Accuracy | Visibility |
|------|--------|-------------|------------|
| Sanity check | 5 | 100% | Visible |
| accuracy 2-1 (n=2, 1-digit) | 5 | 90% | Visible |
| accuracy 2-2 (n=2, 2-digit) | 5 | 90% | Hidden |
| accuracy 2-3 (n=2, 3-digit) | 5 | 90% | Hidden |
| accuracy 3-1 (n=3, 1-digit) | 5 | 90% | Hidden |
| accuracy 3-2 (n=3, 2-digit) | 5 | 90% | Hidden |
| accuracy 3-3 (n=3, 3-digit) | 5 | 70% | Hidden |
| accuracy 4-1 (n=4, 1-digit) | 5 | 70% | Hidden |
| accuracy 4-2 (n=4, 2-digit) | 5 | 50% | Hidden |
| accuracy 5-1 (n=5, 1-digit) | 5 | 70% | Hidden |
| accuracy 5-2 (n=5, 2-digit) | 5 | 50% | Hidden |

#### Accuracy Scoring

Each accuracy test uses partial credit with a maximum of 5 points. The score scales linearly from 0 at the minimum accuracy threshold to 5 at 100% accuracy. Scores are truncated to integers.

#### Sanity Check

The sanity check runs `predict.py` against a simple known input (e.g., `(((1+2)+1)+8)=`) and verifies the model produces the correct output (`(((1+2)+1)+8)=((3+1)+8)=(4+8)=12`). This uses the same prediction pipeline as all other accuracy tests — the model itself must get the answer right. This test requires 100% accuracy.

### Leaderboard (ungraded)

The following accuracy metrics are tracked on the Gradescope leaderboard but do not contribute to the grade:

- `accuracy_2_3` (n=2, 3-digit inputs)
- `accuracy_3_3` (n=3, 3-digit inputs)
- `accuracy_4_2` (n=4, 2-digit inputs)
- `accuracy_5_2` (n=5, 2-digit inputs)
