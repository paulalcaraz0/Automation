# GitHub Activity Automation

This repository automates a small daily commit to keep your GitHub contribution graph green.

## How it works
- A GitHub Actions workflow runs daily on a schedule.
- hihi
- It appends a UTC timestamp to `logs/activity.log`.
- If there are changes, it commits and pushes them back to the repository using the built-in `GITHUB_TOKEN`.

## Setup
1. Create a new repository on GitHub under your account (BunquinTheodore), for example: `github-activity-automation`.
2. Clone it locally and copy these files in, or initialize this folder as a git repo and push it as the new repo.
3. Push to GitHub. Actions will run automatically on the schedule.

### Initialize and push (example)
```bash
# Initialize repo, replace the URL with your repo
git init
git add .
git commit -m "chore: initial automation setup"
# Set your GitHub repo URL
git remote add origin https://github.com/BunquinTheodore/github-activity-automation.git
git branch -M main
git push -u origin main
```

## Run schedule
- Default cron in the workflow is set to run daily at 03:00 UTC (11:00 UTC+08).
- You can adjust the schedule in `.github/workflows/green-activity.yml`.
- You can also trigger it manually from the Actions tab using "Run workflow".

## Notes
- The workflow uses `permissions: contents: write` and relies on the default `GITHUB_TOKEN` provided by GitHub Actions.
- If you fork or make this private, ensure Actions are enabled.
