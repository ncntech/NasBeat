# SmartBot README

This branch adds the SmartBot automation suite: 120 workflow stubs and a set of practical CI workflows focused on mobile (Flutter Android/iOS) plus Rust support.

What I added:
- Core workflows: flutter-ci, rust-ci, codeql, dependabot, coverage, fastlane-release, integration-tests, stale, automerge, release-drafter.
- 120 SmartBot stub workflows under .github/workflows/smartbots/ named smartbot-001.yml ... smartbot-120.yml.

Behavior and safety:
- Workflows that require secrets will skip publish steps and include instructions in the PR.
- The automerge controller is configured to merge Dependabot/format PRs when checks pass. You asked to merge when all checks pass; the PR from SmartBot -> main will be set up for review before merge.

How to enable/disable individual bots:
- Go to .github/workflows and either disable a workflow or modify triggers.
- The README inside the PR will list each SmartBot stub and its intended behavior.

Next steps:
- Review the PR and enable secrets for publishing or coverage uploading as needed.

