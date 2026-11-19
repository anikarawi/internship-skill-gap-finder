# Internship Skill Gap Finder

## Problem

My app helps students targeting analyst internships decide which portfolio project to build next by comparing tasks across target roles with the skills they have practiced. It covers investment analysis, credit analysis, and consulting.

## What it does

1. Shows selected tasks and the ESCO skill matched to each task.
2. Counts how many selected roles use each standardized skill.
3. Removes the skills the student has already practiced to reveal the remaining gaps.
4. Ranks portfolio projects by how many missing skill and role combinations they address.

The input CSV is extracted from the [O*NET 30.3 Task Statements dataset](https://www.onetcenter.org/dictionary/30.3/text/task_statements.html). It keeps all 48 source rows for three occupations, with task IDs and original wording. The task counts are 26 for financial and investment analysts, 11 for credit analysts, and 11 for management analysts. The ESCO rules match nine statements, three per role. Skill overlap and project rankings use those nine matches.

Source: O*NET 30.3 Database, U.S. Department of Labor, Employment and Training Administration, used under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Changes: selected three occupations, renamed the task text and occupation code columns, and added a short role label.

## How to run it

1. Open `Internship_Skill_Gap_Finder.ipynb` in Google Colab.
2. Upload `role_tasks.csv` and `esco_snapshot.csv` to the Colab session using the **Files** panel.
3. Choose **Runtime → Run all**. The notebook calls the [European Commission’s ESCO search API](https://ec.europa.eu/esco/api/search) without a key. If a lookup fails, the notebook says it is using the bundled snapshot.
4. In Step 3, edit `TARGET_ROLES` and `PRACTICED_SKILLS` using the displayed names. Run that cell and the cells below it.

## Example output

With all three roles selected and presenting reports checked off:

| Recommended project | Score | Missing skills addressed |
|---|---:|---|
| Company and credit memo | 5 | Analyse company financial performance, analyse financial risk, and create a financial report |

The score is 2 roles for performance analysis, 2 for risk analysis, and 1 for financial reporting. Use a public filing to compare two years of results and write a one-page credit memo that explains a downside scenario.

## AI Use Disclosure

- **Did I use AI?** Yes.
- **What did I ask it to do?** Build a useful, course rubric and gives internship seekers a concrete next step.
- **What did I change or verify myself?** Everything, made sure the rubric made sense and I understood the code and scoring. 
- **What did I write myself?** The rest of the code.
- **Do I understand every line I am submitting?** Yes
