# Common Run Website

This repository hosts the privacy policy and support pages for Common Run, deployed via GitHub Pages.

## Setup Instructions

1. **Enable GitHub Pages:**
   - Go to your repository settings on GitHub
   - Navigate to "Pages" in the left sidebar
   - Under "Source", select "Deploy from a branch"
   - Choose the `main` branch (or `master` if that's your default branch)
   - Select the `/ (root)` folder
   - Click "Save"

2. **Your site will be available at:**
   - `https://[your-username].github.io/Common-Run/`
   - Or if you have a custom domain, configure it in the Pages settings

3. **Important:** Make sure all files are committed and pushed to GitHub:
   ```bash
   git add .
   git commit -m "Add website files"
   git push
   ```

## Troubleshooting GitHub Pages

If your site isn't visible, check these common issues:

1. **Files not pushed to GitHub:**
   - Make sure you've committed and pushed all files (index.html, support.html, styles.css, .nojekyll)
   - Check your repository on GitHub to confirm the files are there

2. **GitHub Pages not enabled:**
   - Go to Settings → Pages
   - Verify "Source" is set to a branch (usually `main` or `master`)
   - Verify the folder is set to `/ (root)`
   - Click "Save" if you made changes

3. **Wrong branch selected:**
   - Make sure you selected the branch where your files are (usually `main` or `master`)
   - Check which branch is your default branch in Settings → Branches

4. **Deployment delay:**
   - After enabling Pages, it can take 1-5 minutes for the site to be available
   - Check the "Pages" section in Settings for deployment status
   - Look for a green checkmark indicating successful deployment

5. **Repository visibility:**
   - Public repositories: Pages work immediately
   - Private repositories: Pages also work, but check if there are any restrictions

6. **Clear browser cache:**
   - Try a hard refresh: `Cmd+Shift+R` (Mac) or `Ctrl+Shift+R` (Windows/Linux)
   - Or try an incognito/private window

7. **Check the URL:**
   - Make sure you're using the correct repository name in the URL
   - Format: `https://[username].github.io/[repository-name]/`
   - Note: Repository name is case-sensitive

## Pages

- **Privacy Policy:** `index.html` - The app's privacy policy
- **Support:** `support.html` - Support form for users to report issues

## Setting Up the Support Form (EmailJS)

The support form is integrated with EmailJS. Follow these steps to configure it:

### 1. Create an EmailJS Account
1. Sign up for a free account at [emailjs.com](https://www.emailjs.com/)
2. Verify your email address

### 2. Set Up Email Service
1. Go to **Email Services** in your EmailJS dashboard
2. Click **Add New Service**
3. Choose your email provider (Gmail, Outlook, etc.) and connect it
4. Note your **Service ID** (e.g., `service_xxxxxxx`)

### 3. Create an Email Template
1. Go to **Email Templates** in your EmailJS dashboard
2. Click **Create New Template**
3. Use the following template variables:
   - `{{title}}` - Issue title
   - `{{description}}` - Issue description
   - `{{name}}` - User's name (or "Not provided")
   - `{{email}}` - User's email (or "Not provided")
   - `{{date}}` - Submission date/time

4. Example template:
   ```
   Subject: Support Request: {{title}}
   
   New support request received:
   
   Title: {{title}}
   Description: {{description}}
   
   Contact Information:
   Name: {{name}}
   Email: {{email}}
   
   Submitted: {{date}}
   ```
5. Note your **Template ID** (e.g., `template_xxxxxxx`)

### 4. Get Your Public Key
1. Go to **Account** → **General** in your EmailJS dashboard
2. Copy your **Public Key** (e.g., `xxxxxxxxxxxxxxxx`)

### 5. Update support.html
1. Open `support.html`
2. Replace `YOUR_PUBLIC_KEY` with your EmailJS Public Key (line ~56)
3. Replace `YOUR_SERVICE_ID` with your Service ID (line ~88)
4. Replace `YOUR_TEMPLATE_ID` with your Template ID (line ~88)

The form will now send emails directly to your configured email address when users submit support requests!

## Customization

- **Styling:** Edit `styles.css` to customize the appearance
- **Privacy Policy:** Edit `index.html` to update the privacy policy content
- **Support Form:** Edit `support.html` to modify the form fields
- The date and year are automatically updated via JavaScript
