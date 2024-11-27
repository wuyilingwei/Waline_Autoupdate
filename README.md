# Auto-Update for Waline(Vercel) with GitHub Actions

This project automates updates for the Waline Vercel deployment, ensuring your environment stays up-to-date with minimal effort. The solution leverages GitHub Actions to trigger automatic Vercel deployments every month.

## Features

Seamless Updates: Automatically updates the Waline package to the latest version.

Effortless Deployment: Uses GitHub Actions to push a blank commit, triggering Vercel deployment without manual intervention.

Low Permissions: Requires only minimal permissions (contents: write) for the default GitHub token. No need to generate keys manually.

Maintenance-Free: Ensures the action remains active by preventing auto-disable after extended inactivity.

Scheduled Automation: Deploys automatically on a monthly schedule, with additional manual trigger support.

## Steps to Set Up

1. Connect Vercel Project to GitHub Repository

Ensure your Vercel project is linked to your GitHub repository. If not, manually create a connection in the Vercel dashboard.

3. Update package.json

Modify your package.json to always pull the latest Waline version by replacing the dependency line with:

  `"@waline/vercel": "latest"`

3. Configure GitHub Action

Copy workflow file into your repository at .github/workflows/Auto_update.yml with the following file:

https://raw.githubusercontent.com/wuyilingwei/Waline_Autoupdate/refs/heads/main/.github/workflows/Auto_update.yml

## How It Works

Scheduled Execution: The GitHub Action runs monthly or on-demand via manual trigger.

Empty Commit: A blank commit is pushed to the repository, signaling a change.

Vercel Auto-Deploy: Vercel detects the push and redeploys your project with the latest Waline version.

## Alternative Approaches

While this solution is simple and secure, other methods could be explored:

Vercel API Triggers: Using a scheduled API call to trigger deployment (requires API token management).

Direct Deployment Command: Sending deployment commands via GitHub Action (adds configuration complexity and potential security risks).

~~I'm not interest to write this, this readme was created by OPENAI. (based on my blog)~~

I used vercel to deploy, maybe other deployment providers have similar features, maybe you can try it. Setting the deployment repository to private still works fine.
