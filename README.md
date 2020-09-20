# Get the branch name from a pull request (PR)

A Github Action that retrieves the branch name from a PR and sets it in the output for other actions to use.
It can either accept a specific PR ID/number, or try to take from the current context if none is provided.

# Usage

```yaml
- uses: andrevalentin/get-branch-name-by-pr@1.0.0
  id: pr_data
  with:
    repo-token: ${{ secrets.GITHUB_TOKEN }}
    pr-id: 123

- name: Checkout code
  uses: actions/checkout@v2
  with:
    ref: ${{ steps.pr_data.outputs.branch }}
```

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
