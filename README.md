# Get Branch Name From Pull Request (PR)

A github action that retrieves the branch name from a PR and sets it in the output for other actions to use.
It can either accept a specific PR ID, or try to take from the current context if none is provided.

# Usage

```yaml
- uses: andrevalentin/get-branch-name-by-pr@1.0.0
  id: vars
  with:
    repo-token: ${{ secrets.GITHUB_TOKEN }}
    pr-id: 123
- run: echo ${{ steps.vars.outputs.branch }}
```

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)