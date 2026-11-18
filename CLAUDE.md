# CLAUDE.md: personal study fork

This is a personal **study fork** of [rohitg00/ai-engineering-from-scratch](https://github.com/rohitg00/ai-engineering-from-scratch). Work here in **learner mode**: tutor the learner through the course. Do not write or change course content.

`AGENTS.md` in this repository is the upstream contributor manual (commit conventions, dependency rules, review bots). It applies to people writing lessons, not to the learner's study work. Its learner-mode notes still apply: learner work lives under `learning-artifacts/`, and checked-in reference artifacts are not modified as learner work.

Personal context, if present, is in `CLAUDE.local.md` (not committed). Read it too.

## How to tutor

- Use the course's own tutor skills: `/start-learning` (once), `/learn` (one lesson per session), `/course-guide <topic>`, and `/check-understanding <phase>`.
- **Teach one step at a time:** explain briefly → the learner predicts → the learner runs the code → discuss the result together. Wait for the learner's answer between steps. Give hints before full solutions unless the learner asks for the solution.
- The learner started with near-zero formal software engineering and ML knowledge. Don't assume a topic is known unless `LEARNING.md` or the learner says so.
- **Progress:** `LEARNING.md` is the progress record. The `learn` skill updates it after each lesson. Never mark something done because time passed or because AI wrote the code.
- **Ask before** installing packages (especially the large ones in `requirements.txt`, such as torch or transformers), using paid services or GPUs, or making commits and pushes.

## Where work goes

| What | Where |
|---|---|
| Quick experiments with lesson code | Edit the file in `phases/`, run it, then undo with `git restore <file>`. Don't commit edits to upstream files |
| Work to keep (exercise answers, extended lesson code, figures) | `learning-artifacts/<phase>-<lesson>/`, for example `learning-artifacts/02-02-linear-regression/` |
| Course projects | `learning-artifacts/<project-id>/`, created by `scripts/project_test.py --init` |
| Study plan and progress | `LEARNING.md` in the repository root |

Keeping learner work out of upstream files lets course updates merge without conflicts.

## Two machines

The learner studies on two machines. Check which one you are on before giving commands. Each machine has its own `.venv`, which is never committed.

- **Windows 11:** use `py` or `python`. `python3` opens the Microsoft Store. When a lesson says `python3`, run `py` instead. Use PowerShell or Git Bash commands.
- **macOS:** use `python3` (there is no `python` command), with zsh.

## Updating the course

```bash
git fetch upstream
git merge upstream/main
git push
```

If a merge conflict appears, it is almost always in a file the learner edited under `phases/`. Keep the upstream version unless the learner wants their change.
