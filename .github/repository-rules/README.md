# Preferred GitHub Repository Rules

These files capture the preferred settings for this repository:

- `repository-settings.json` configures `main` as the default branch, allows only squash merges, and deletes head branches after pull requests merge.
- `main-branch-protection.json` protects `main`, requires a pull request with an approval from the repository owner via CODEOWNERS, allows the owner to bypass pull request requirements, and prevents force pushes and branch deletion.

