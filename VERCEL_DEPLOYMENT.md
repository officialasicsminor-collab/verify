# Vercel Deployment Guide

This guide will help you deploy the USDT Verification DApp to Vercel for free.

## Prerequisites

1. A Vercel account (free at https://vercel.com)
2. A GitHub account
3. Your code pushed to GitHub

## Step 1: Push Code to GitHub

1. Create a new repository on GitHub
2. Push your code to the repository:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

## Step 2: Deploy to Vercel

1. Go to https://vercel.com and sign in
2. Click "Add New" → "Project"
3. Import your GitHub repository
4. Vercel will automatically detect the project settings
5. Click "Deploy"

## Step 3: Configuration

Vercel will automatically configure:
- **Framework Preset:** Other
- **Root Directory:** ./
- **Build Command:** (none needed)
- **Output Directory:** public
- **Install Command:** npm install

## Step 4: Environment Variables (Optional)

If you need to set environment variables:
1. Go to your project settings in Vercel
2. Navigate to "Environment Variables"
3. Add any required variables

## Step 5: Access Your App

After deployment:
- Vercel will provide a URL like: `https://your-project.vercel.app`
- Access the verification page at: `https://your-project.vercel.app/verify`

## Important Notes

### API Endpoint
- The API endpoint is automatically available at: `https://your-project.vercel.app/api/verify`
- Vercel serverless functions handle this automatically

### HTTPS
- Vercel provides automatic HTTPS
- This is required for Trust Wallet to work properly

### Custom Domain (Optional)
1. Go to project settings → Domains
2. Add your custom domain
3. Follow the DNS instructions provided

## Troubleshooting

### Build Fails
- Ensure `package.json` has correct dependencies
- Check that `api/verify.js` exists and is valid

### API Not Working
- Verify the API endpoint is at `/api/verify`
- Check Vercel function logs for errors

### Wallet Connection Issues
- Ensure you're using HTTPS (Vercel provides this automatically)
- Trust Wallet requires HTTPS to work

## File Structure for Vercel

```
your-project/
├── api/
│   └── verify.js          # Serverless function
├── public/
│   ├── verify.html
│   ├── verify.js
│   ├── verify.css
│   └── ...                # Other frontend files
├── vercel.json            # Vercel configuration
├── package.json           # Dependencies
└── README.md
```

## Differences from Traditional Deployment

- No `server.js` needed (Vercel handles routing)
- No `express` or `cors` dependencies needed
- API functions go in `api/` directory
- Static files go in `public/` directory
- Automatic HTTPS provided
- Serverless functions (no persistent server)

## Support

For Vercel-specific issues:
- https://vercel.com/docs
- https://vercel.com/support
