# Change Default Branch Workflow

This workflow allows you to change the default branch of the repository using a GitHub App token for authentication.

## Setup Requirements

Before using this workflow, you need to configure the following repository secrets:

### GitHub App Secrets
- `APP_ID`: The GitHub App ID
- `APP_PRIVATE_KEY`: The GitHub App's private key (in PEM format)

### GitHub App Permissions
The GitHub App must have the following permissions:
- **Repository permissions:**
  - Contents: Read
  - Metadata: Read
  - Administration: Write (required to change default branch)

## Usage

1. Navigate to the Actions tab in your repository
2. Find the "Change Default Branch" workflow
3. Click "Run workflow"
4. Enter the name of the branch you want to set as default
5. Click "Run workflow" to execute

## What the workflow does

1. **Validates the target branch exists** on the remote repository
2. **Gets the current default branch** using the GitHub API
3. **Changes the default branch** to the specified target branch
4. **Verifies the change** was successful

## Security Notes

- Uses GitHub App authentication instead of personal access tokens for better security
- Requires minimal permissions (only what's needed to change the default branch)
- Validates input to ensure the target branch exists before making changes
- Provides clear error messages if something goes wrong

## Example

To change the default branch to `main`:
```
target_branch: main
```

To change the default branch to `develop`:
```
target_branch: develop
```