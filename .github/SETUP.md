# Setting Up GitHub Profile Stats Workflows

This guide will help you properly set up and troubleshoot all the GitHub Actions workflows to make your profile README amazing.

## Initial Setup

1. **Create GitHub Personal Access Token**
   - Go to GitHub Settings → Developer Settings → Personal Access Tokens → Generate New Token
   - Select at minimum these scopes: `repo`, `user`
   - Copy the generated token (you'll only see it once!)

2. **Add Secrets to Your Repository**
   - Go to your profile repository settings → Secrets and variables → Actions
   - Add the following secrets:
     - `GH_TOKEN`: Your GitHub personal access token
     - `METRICS_TOKEN`: Your GitHub personal access token (same as above or create a new one)

3. **Set Up WakaTime (Optional but Recommended)**
   - Sign up for [WakaTime](https://wakatime.com)
   - Install WakaTime plugins for your code editors/IDEs
   - Get your WakaTime API Key from your account settings
   - Add as a secret to your repository:
     - `WAKATIME_API_KEY`: Your WakaTime API key

## Workflow Explanation

### Snake Animation Workflow (`snake.yml`)
- **What it does**: Generates a snake game animation based on your GitHub contribution graph
- **Output**: Creates SVG files in the `dist/` directory
- **Customization**: You can modify the colors and appearance in the workflow file

### Profile Stats Workflow (`profile-stats.yml`)
- **What it does**: Updates your README with detailed coding stats from WakaTime and GitHub
- **Output**: Modifies your README.md directly
- **Customization**: You can modify which metrics to show in the workflow file

### GitHub Metrics Workflow (`metrics.yml`)
- **What it does**: Generates comprehensive GitHub metrics and badges
- **Output**: Creates SVG files that are displayed in your README
- **Customization**: Many options available in the workflow file

### Recent Activity Workflow (`update-activity.yml`)
- **What it does**: Updates your README with your most recent GitHub activity
- **Output**: Modifies the README.md section between activity markers
- **Customization**: You can change the frequency and number of activities

## Troubleshooting

### Workflows Not Running
1. Check if GitHub Actions is enabled for your repository
2. Manually trigger workflows using the "Run workflow" button in the Actions tab
3. Check if you've properly set up all required secrets

### Images Not Showing
1. Make sure the workflow has run at least once successfully
2. Check if the paths in your README match the output paths in the workflows
3. Ensure the repository has the proper permissions to write to the output branch

### Snake Animation Not Working
1. Make sure the `output` branch exists (create it if it doesn't)
2. Manually run the snake workflow once
3. Check the paths in your README to ensure they match the output location

### WakaTime Stats Missing
1. Ensure WakaTime is properly installed in your IDEs/editors
2. Make sure you've been coding for at least a day with WakaTime active
3. Verify the API key is correctly set as a secret

## Advanced Customization

### Changing Themes
Most of the workflows allow theme customization. Look for parameters like `theme:` in the workflow files.

### Adding More Metrics
The `metrics.yml` workflow has many plugins you can enable. Check the [lowlighter/metrics documentation](https://github.com/lowlighter/metrics/blob/master/README.md) for more options.

### Custom Layout
You can modify the README.md layout to arrange your stats in different ways, add more sections, or change the design.

## Final Steps

After setting everything up:

1. Push all changes to your repository
2. Go to the Actions tab and manually trigger each workflow once
3. Wait for all workflows to complete
4. Check your profile to see the results
5. Make any necessary adjustments to fix issues or customize the appearance

Your GitHub profile should now be automatically updated daily with all your stats, streaks, and activity!