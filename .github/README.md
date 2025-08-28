# GitHub Actions Wiz CLI Scanning

This repository includes a GitHub Actions workflow that automatically builds Docker images and scans them with Wiz CLI on pull requests.

## Workflow: Docker Build and Wiz Scan

**File:** `.github/workflows/docker-build-and-wiz-scan.yml`

### What it does:
- Triggers on pull requests to `main` or `master` branches
- Builds a Docker image from the root `Dockerfile`
- Downloads and installs Wiz CLI
- Configures Wiz for FedRamp environment
- Scans the built Docker image for vulnerabilities and compliance

### Setup Requirements:

#### 1. Configure Repository Secrets
You need to add the following secrets in your repository settings (`Settings > Secrets and variables > Actions`):

- `WIZ_CLIENT_ID`: Your Wiz client ID
- `WIZ_CLIENT_SECRET`: Your Wiz client secret

#### 2. Wiz FedRamp Configuration
The workflow is pre-configured to use Wiz's FedRamp environment by setting `WIZ_ENV=fedramp`.

### Usage:
1. Create a pull request against the `main` or `master` branch
2. The workflow will automatically run and:
   - Build the Docker image
   - Install Wiz CLI
   - Scan the image
   - Report results in the workflow logs

### Workflow Output:
The workflow provides detailed logging including:
- Docker build progress
- Wiz CLI installation confirmation
- Scan initiation and results

Check the "Actions" tab in GitHub to view workflow runs and scan results.