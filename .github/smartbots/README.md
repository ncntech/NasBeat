# Smartbots README

This directory contains 120 Smartbot GitHub Actions workflows created to analyze issues, scan code, monitor build health, and (simulated) apply automated fixes.

Important notes:
- Workflows run in the `smartbot` branch.
- To enable autopush / PR creation from Copilot-fixer workflows, set a repo secret named `REPO_WRITE_TOKEN` (a token with repo scope) or ensure `GITHUB_TOKEN` has write permissions.
- To integrate a real Copilot/LLM to generate code fixes, replace the simulated steps in `smartbot-***-copilot-fixer.yml` with your preferred action that calls an LLM, and store credentials in `COPILOT_API_KEY`.

Files created: 120 workflow files in `.github/workflows/`.

Examples of what each bot type does:
- Issue Analyzer: lists open issues in `nastech-ai/NasBeat`, comments with a simple categorization.
- Code Quality Scanner: runs `dart analyze` (if Dart/Flutter present) and `cargo clippy` (if Rust present) when possible, and comments a short report.
- Build Health Monitor: copies/aggregates open build-health issues from the parent repo and posts a summary.
- Copilot Fixer (simulated): creates a new branch with a trivial fix file and opens a pull request (demonstrates the automation flow). Replace with real LLM integration as needed.
