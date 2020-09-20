# Get the branch name from a pull request (PR)

A Github Action that retrieves the branch name from a PR and sets it in the output for other actions to use.
It can either accept a specific PR ID/number, or try to take from the current context if none is provided.

# Usage

### Example of providing a PR ID to fetch & subsequently use the branch name
```yaml
- name: Get branch name based on PR ID
  uses: andrevalentin/get-branch-name-by-pr@1.0.0
  id: pr_data
  with:
    repo-token: ${{ secrets.GITHUB_TOKEN }}
    pr-id: 123

- name: Checkout code
  uses: actions/checkout@v2
  with:
    ref: ${{ steps.pr_data.outputs.branch }}
```

### Example where the action just takes the PR ID from context
```yaml
- name: Get branch name based on PR
  uses: andrevalentin/get-branch-name-by-pr@1.0.0
  id: pr_data
  with:
    repo-token: ${{ secrets.GITHUB_TOKEN }}

- name: Checkout code
  uses: actions/checkout@v2
  with:
    ref: ${{ steps.pr_data.outputs.branch }}
```

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
