# 🚀 GitHub Pages Deployment Guide

Follow these steps to deploy your dynamic spin wheel to GitHub Pages:

## Step 1: Prepare Your Repository

1. **Create a new GitHub repository** or use your existing one
2. **Upload all files** from your local SpinWheel folder:
   - `index.html` (landing page)
   - `Home.html` (main wheel)
   - `admin.html` (admin panel)
   - `ADMIN-GUIDE.md` (documentation)
   - `README.md` (if you have one)
   - `fitsmile_logo.png`
   - `play_button.png`
   - `spin-sound.mp3`
   - `win-sound.mp3`
   - `lost-sound.mp3`

## Step 2: Enable GitHub Pages

1. **Go to your repository settings**:
   - Navigate to your GitHub repository
   - Click on "Settings" tab
   - Scroll down to "Pages" section

2. **Configure GitHub Pages**:
   - Under "Source", select "Deploy from a branch"
   - Choose "main" branch (or your default branch)
   - Select "/ (root)" folder
   - Click "Save"

## Step 3: Wait for Deployment

- GitHub will provide you with a URL like: `https://yourusername.github.io/repository-name/`
- Initial deployment may take 5-10 minutes
- You'll see a green checkmark when it's ready

## Step 4: Test Your Deployment

### User Experience
1. Visit: `https://yourusername.github.io/repository-name/`
2. You should see the landing page with options to access the wheel or admin panel
3. Click "Open Spin Wheel" to test the spinning functionality

### Admin Experience
1. Visit: `https://yourusername.github.io/repository-name/admin.html`
2. Login with password: `spinwheel2024` (remember to change this!)
3. Test configuration changes and verify they apply to the main wheel

## Step 5: Customize for Your Use

### Change Admin Password
**IMPORTANT**: Before sharing publicly, change the admin password:

1. Edit `admin.html`
2. Find this line: `const ADMIN_PASSWORD = 'spinwheel2024';`
3. Replace with your secure password: `const ADMIN_PASSWORD = 'your-secure-password';`
4. Commit and push the changes

### Set Your Default Configuration
1. Access the admin panel
2. Configure your desired default segments and colors
3. Set your organization name and wheel title
4. Configure sound/visual preferences
5. Save configuration

## Step 6: Share with Your Team

### For Regular Users:
- **Main Wheel**: `https://yourusername.github.io/repository-name/Home.html`
- **Landing Page**: `https://yourusername.github.io/repository-name/`

### For Administrators:
- **Admin Panel**: `https://yourusername.github.io/repository-name/admin.html`
- **Password**: (Your custom password)

## Updates and Maintenance

### Making Code Updates
1. Edit files locally or directly on GitHub
2. Commit changes
3. GitHub Pages will automatically redeploy (usually within 5 minutes)
4. **User configurations are preserved** - no data loss!

### Backing Up Configurations
Since configurations are stored in browser localStorage:
1. Important configurations should be documented
2. Consider creating template configurations in the admin panel
3. Test configurations on different devices/browsers

## Troubleshooting

### Common Issues:

**404 Error**: 
- Ensure GitHub Pages is enabled in repository settings
- Check that `index.html` exists in the root directory

**Admin Panel Not Working**:
- Verify JavaScript is enabled in browser
- Check browser console for errors
- Ensure all files are uploaded correctly

**Sounds Not Playing**:
- Check that audio files (`.mp3`) are uploaded
- Some browsers block autoplay - user interaction may be required
- Verify files are accessible at the correct URLs

**Configurations Not Saving**:
- Check browser localStorage settings
- Ensure site is running over HTTPS (GitHub Pages provides this)
- Try clearing browser cache and reconfiguring

### Testing Locally
Before deploying, you can test locally:
1. Use a local web server (not file:// protocol)
2. Python: `python -m http.server 8000`
3. Node.js: `npx serve .`
4. Then visit: `http://localhost:8000`

## Security Notes

- The admin system is frontend-only for simplicity
- Not suitable for highly sensitive applications
- For production use, consider:
  - More secure authentication
  - Server-side configuration storage
  - User permission management

## Need Help?

- Check the `ADMIN-GUIDE.md` for detailed usage instructions
- GitHub Pages documentation: https://docs.github.com/en/pages
- For technical issues, check your browser's developer console

---

**🎉 Your spin wheel is now live and dynamically configurable!**
