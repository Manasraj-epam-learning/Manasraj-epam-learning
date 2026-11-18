# EPAM Learning Portfolio

This repository documents my ongoing learning in the CoE EPAM program. It collects my notes, small Python implementations and practice exercises, organised by topic. I am a B.Tech student specialising in Artificial Intelligence and Machine Learning at LNCT, Bhopal.

It is a learning record, not a finished product. Topic status is stated honestly: one topic is completed and the others are in progress.

## Learning objectives

- Build a solid understanding of AI fundamentals and how machine learning systems are built and evaluated.
- Strengthen programming and problem-solving skills in Python.
- Learn how to evaluate AI outputs through prompt and instruction evaluation.
- Understand how AI agents are structured.
- Practise Agile and Scrum ways of working used in real software teams.
- Write clean, readable code that I can explain.

## Progress

| # | Topic | Status | What is in the folder |
|---|-------|--------|-----------------------|
| 1 | [AI Foundations](AI-Foundations/) | Completed | Detailed notes, glossary, 2 programs (regression, spam classifier), 6 exercises, saved outputs |
| 2 | [Python](Python/) | In progress | Basic notes, 7 small programs, 3 problem-solving exercises |
| 3 | [Prompt Evaluation](Prompt-Evaluation/) | In progress | Introductory notes, checklist evaluator, 7 test cases |
| 4 | [AI Agents](AI-Agents/) | In progress | Introductory notes, small rule-based agent, demo run |
| 5 | [Instruction Evals](Instruction-Evals/) | In progress | Introductory notes, instruction checker, 7 test cases |
| 6 | [Agile Mindset](Agile-Mindset/) | In progress | Agile and Scrum notes, 5 scenarios, sample product and sprint backlog |

## Repository navigation

```
epam-learning-portfolio/
├── README.md
├── AI-Foundations/       notes/ code/ practice/ outputs/
├── Python/               notes/ code/ practice/ outputs/
├── Prompt-Evaluation/    notes/ code/ examples/
├── AI-Agents/            notes/ code/ examples/
├── Instruction-Evals/    notes/ code/ examples/
└── Agile-Mindset/        notes/ exercises/
```

Each topic folder has its own README with an overview, folder structure, run instructions, sample output and learning outcomes.

Suggested starting point: [AI-Foundations/README.md](AI-Foundations/README.md), then the topic that interests you.

## How to run the code

All programs use only the Python standard library. Python 3.8 or later is required (the code was tested with Python 3.12). Open a terminal in a topic folder and follow its README, for example:

```bash
cd AI-Foundations
python code/spam_classifier.py
```

## Technologies used

- Python 3 (standard library only: `random`, `math`, `re`, `json`, `csv`, `collections`, `dataclasses`, `pathlib`)
- Markdown for notes and documentation
- Git and GitHub for version control

## Honest notes

- The machine learning examples use tiny, hand-made datasets to show the workflow. Their scores are not evidence of real-world performance.
- Programs that are rule-based (the keyword spam filter, the agent) are labelled as such and are not presented as AI models.
- In-progress topics contain introductory material and will grow as my learning continues.
