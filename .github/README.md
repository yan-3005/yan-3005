# GitHub Workflows

This directory contains various GitHub Actions workflows to enhance the GitHub profile README with automated stats, visualizations, and activity tracking.

## Workflows Overview

### 1. Profile Stats (`profile-stats.yml`)
- Updates the README with detailed GitHub stats using [waka-readme-stats](https://github.com/anmol098/waka-readme-stats)
- Generates a contribution snake animation using [Platane/snk](https://github.com/Platane/snk)
- **Schedule**: Runs daily at midnight
- **Required Secrets**:
  - `WAKATIME_API_KEY`: API key from WakaTime
  - `GH_TOKEN`: GitHub Personal Access Token

### 2. GitHub Metrics (`metrics.yml`)
- Generates comprehensive GitHub metrics using [lowlighter/metrics](https://github.com/lowlighter/metrics)
- Includes language stats, activity calendar, achievements, and more
- **Schedule**: Runs daily at midnight
- **Required Secrets**:
  - `METRICS_TOKEN`: GitHub Personal Access Token

### 3. Streak Stats (`streak-stats.yml`)
- Generates a GitHub streak stats image using [DenverCoder1/github-readme-streak-stats](https://github.com/DenverCoder1/github-readme-streak-stats)
- **Schedule**: Runs daily at midnight
- **Output**: Generates `dist/streak-stats.svg`

### 4. GitHub Trophies (`trophies.yml`)
- Generates GitHub profile trophies using [ryo-ma/github-profile-trophy](https://github.com/ryo-ma/github-profile-trophy)
- **Schedule**: Runs daily at midnight
- **Output**: Generates `dist/trophies.svg`

## Setup Instructions

1. Create the following secrets in your repository settings:
   - `GH_TOKEN`: GitHub Personal Access Token with repo scope
   - `WAKATIME_API_KEY`: Get this from your WakaTime account
   - `METRICS_TOKEN`: Same as GH_TOKEN or create a separate one

2. Enable GitHub Actions in your repository settings

3. The workflows will run automatically according to their schedules, or you can manually trigger them from the Actions tab

## Customization

Feel free to customize any of these workflows to match your preferences:

- Change themes for different components
- Adjust schedule frequency
- Add or remove specific metrics
- Modify layout in the README.md file

## Troubleshooting

If the workflows fail:
1. Check that all required secrets are correctly set up
2. Verify that the GitHub Actions are enabled for the repository
3. Ensure your README.md is properly formatted to accept the generated content
4. Review the workflow logs for specific error messages