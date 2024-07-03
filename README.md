# gh

## How to Configure Branch Protection Rules Using API

To configure branch protection rules using the GitHub API, follow these steps:

1. Create a JSON file with the branch protection rules. For example, create a file named `branch_protection.json` with the following content:

```json
{
  "required_status_checks": {
    "strict": true,
    "contexts": []
  },
  "enforce_admins": true,
  "required_pull_request_reviews": {
    "dismiss_stale_reviews": true,
    "require_code_owner_reviews": true
  },
  "restrictions": null
}
```

2. Use the `gh api` command to apply the branch protection rules using the JSON file:

```sh
gh api -X PUT -H "Accept: application/vnd.github.v3+json" /repos/<OWNER>/<REPO>/branches/<BRANCH>/protection --input branch_protection.json
```

Replace `<OWNER>`, `<REPO>`, and `<BRANCH>` with the appropriate values for your repository.

