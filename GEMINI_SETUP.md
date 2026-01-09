# Gemini AI Code Review Setup Guide

This repository includes an automated code review workflow powered by Google Gemini AI.

## How It Works

When you create a pull request, the workflow automatically:
1. Fetches the PR diff
2. Sends it to Google Gemini 1.5 Flash for analysis
3. Posts a comprehensive code review as a PR comment

## Setup Instructions

### Step 1: Get Your Gemini API Key

1. Visit [Google AI Studio](https://aistudio.google.com)
2. Sign in with your Google account (use your account with Gemini Pro access)
3. Click "Get API key" in the left sidebar
4. Click "Create API key in new project"
5. Copy your API key

### Step 2: Add the Secret to GitHub

1. Go to your repository Settings → Secrets and variables → Actions
2. Click "New repository secret"
3. Name: `GEMINI_API_KEY`
4. Value: Paste your API key from Step 1
5. Click "Add secret"

### Step 3: Create a Pull Request

1. Create a new branch and make some code changes
2. Push your branch and create a PR
3. The workflow will automatically run
4. Check the PR for the Gemini AI code review comment

## Features

✅ Security issue detection
✅ Code quality analysis  
✅ Best practices suggestions
✅ Positive feedback on good code

## Workflow File

The workflow is defined in `.github/workflows/gemini-pr-review.yml`

## Limitations

- First 60 requests per minute are free (Gemini API)
- The review is limited to the first 3000 characters of the diff
- Works with pull requests created from the same repository (not forks)

## Troubleshooting

### Workflow doesn't run
- Verify the `GEMINI_API_KEY` secret is added
- Check that the API key is valid
- View the Actions tab to see workflow logs

### Empty review comment
- The API might have rate-limited your request
- Check if your API key has the correct permissions

## Support

For issues with Gemini API, visit [Google AI FAQ](https://support.google.com/ai-studio)

## Free Tier

Google's Generative AI API includes a free tier with:
- 60 requests per minute (RPM) limit
- Suitable for development and personal projects
