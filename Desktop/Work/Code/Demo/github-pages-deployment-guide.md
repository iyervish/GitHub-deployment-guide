# Deploying React Apps to GitHub Pages: A Complete Guide

## Prerequisites
- Git installed on your local machine
- Node.js and npm installed
- GitHub account
- React application code ready for deployment

## Step-by-Step Deployment Instructions

### 1. Create a GitHub Repository
1. Go to GitHub and create a new repository
2. Make it public if you want to use GitHub Pages with a free account
3. Copy the repository URL for the next step

### 2. Local Setup
```bash
# Initialize git in your project (if not already done)
git init

# Add remote repository
git remote add origin <your-repository-url>

# Create and switch to main branch (if not already on it)
git checkout -b main
```

### 3. Configure package.json
Add these fields to your `package.json`:
```json
{
  "homepage": "https://<your-github-username>.github.io/<repository-name>",
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build"
  }
}
```

### 4. Install Dependencies
```bash
# Install gh-pages as a dev dependency
npm install --save-dev gh-pages
```

### 5. Deploy the App
```bash
# Build and deploy
npm run deploy
```

### 6. GitHub Settings
1. Go to your repository settings
2. Navigate to "Pages" under "Code and automation"
3. Select "Deploy from a branch" under "Source"
4. Choose "gh-pages" branch and "/(root)" folder
5. Click "Save"

## Troubleshooting Tips

### Deployment Failures
1. Verify your working directory:
```bash
pwd
git remote -v
```

2. Check repository connection:
```bash
git remote -v
```

3. Verify build folder contents:
```bash
ls build
```

### Blank Page After Deployment
1. Check if your `homepage` in `package.json` matches your GitHub Pages URL
2. Ensure all asset paths are relative
3. Clear browser cache and try a hard refresh
4. Check browser console for specific errors

## Common Mistakes to Avoid
1. Wrong homepage URL format in `package.json`
2. Deploying without building first
3. Using absolute paths for assets
4. Not waiting for GitHub Pages to finish deployment
5. Incorrect branch selection in GitHub Pages settings

## Quick Command Reference
```bash
# Initialize and setup
git init
git remote add origin <repository-url>

# Install dependencies
npm install --save-dev gh-pages

# Deploy
npm run deploy

# Check status
git status
git remote -v

# Force rebuild and deploy
rm -rf build/
npm run build
npm run deploy
```

## Additional Resources
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Create React App Deployment Guide](https://create-react-app.dev/docs/deployment/#github-pages)
- [gh-pages npm package](https://www.npmjs.com/package/gh-pages) 