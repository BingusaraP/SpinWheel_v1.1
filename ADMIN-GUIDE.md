# 🎡 Dynamic Spin Wheel Admin System

This enhanced spin wheel now supports **dynamic configuration** without the need to redeploy code to GitHub Pages!

## 🚀 Quick Start

### For End Users
- Open `Home.html` to use the spin wheel
- The wheel will display the current configuration set by administrators

### For Administrators
1. Open `admin.html` in your web browser
2. Login with the admin password (default: `FITSMILES`)
3. In Wheel Configuration, choose a wheel size (8, 10, or 12)
4. Edit each segment’s Name, Type, and Color as needed
5. Click “Save Configuration”
6. Click “Open Main Wheel” to view it in a new tab

**Notes**:
- The two action buttons are at the bottom-right of the Wheel Configuration panel (Save above Open)
- The main wheel listens for changes and also polls every 5 seconds, so updates appear shortly after you save

## 🔧 Admin Features

### Wheel Configuration (fixed sizes)
- Select from 8, 10, or 12 segments
- Per-segment editors:
  - **Name**: any text. The wheel renders up to two curved lines with an ellipsis if long
  - **Type**: one of
    - Fitsmiles Prize (prize)
    - Fitsmiles Coins (fitsmiles)
    - No win (fail)
  - **Color**: pick a hex color per slice
- Size templates pre-fill common values (5/10/15/20 Fitsmiles alternating with “Sorry”). You can customize all values after applying a template
- Each segment is independent. Editing a “No win” name changes only that segment

### Settings (appearance)
- **Wheel Title**
- **Organization Name**

These appear on `Home.html` and update without needing a reload after you save

## 🛡️ Security

### Changing the Admin Password
To change the admin password, edit the `ADMIN_PASSWORD` constant in `admin.html`:

```javascript
const ADMIN_PASSWORD = 'your-new-password-here';
```

**Important**: Change the default password before deploying to production!

### Authentication
- Login sessions are stored locally and persist until browser storage is cleared
- No sensitive data is transmitted over the network
- All configuration is stored in the browser's localStorage

## 💾 How It Works

- All configuration is stored in the browser’s `localStorage`
- No server/database is required. Static hosting (e.g., GitHub Pages) works fine
- Keys used by the system:
  - `wheelSegments`: Array of segment text values
  - `wheelColors`: Array of segment colors (hex)
  - `wheelOutcomes`: Array of outcome types (prize | fitsmiles | fail)
  - `wheelTitle`: Display title
  - `wheelOrgName`: Organization name

The main wheel also recognizes these if present from older setups (not currently editable in the admin UI):
- `wheelEnableSounds` ("true" | "false")
- `wheelEnableConfetti` ("true" | "false")
- `wheelSpinDuration` (seconds, integer)

### Auto-Reload
- Changes from the admin panel are automatically detected
- The main wheel updates every 5 seconds if configuration changes
- No need to refresh the page after making admin changes

## 🎨 Customization

### Adding New Templates
In `admin.html`, add new templates to the `loadTemplate()` function:

```javascript
case 'your-template':
  template = [
    { text: "Prize 1", color: "#FF0000" },
    { text: "Prize 2", color: "#00FF00" },
    // ... more segments
  ];
  break;
```

### Custom Styling
- Edit the CSS in `admin.html` to change the admin panel appearance
- Edit the CSS in `Home.html` to change the wheel appearance
- Both files use the same color scheme for consistency

## 🚀 Deployment to GitHub Pages

1. Push all files to your GitHub repository
2. Enable GitHub Pages in repository settings
3. Choose the source branch (usually `main` or `gh-pages`)
4. Your wheel will be available at `https://yourusername.github.io/repository-name/Home.html`
5. Admin panel will be at `https://yourusername.github.io/repository-name/admin.html`

## 📱 Browser Compatibility

- ✅ Chrome (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- 📱 Mobile browsers (responsive design)

## 🔄 Updating

When you want to add new features or fix bugs:
1. Make changes to the HTML/CSS/JavaScript files
2. Commit and push to GitHub
3. **User configurations are preserved** - no data loss!
4. Users will get the new features while keeping their custom settings

## 🆘 Troubleshooting

### Common Issues

**Admin panel won't load**: Check that JavaScript is enabled in your browser

**Changes not saving**: Check browser console for localStorage errors

**Wheel not spinning**: Verify that the segments configuration is valid (minimum 2 segments)

**Sounds not playing**: Check browser autoplay policies and ensure sound files exist

### Reset Everything
To completely reset the wheel to defaults:
1. Open browser developer tools (F12)
2. Go to Application/Storage → Local Storage
3. Delete all entries starting with "wheel"
4. Refresh the page

## 🤝 Support

For technical support or feature requests, contact your development team or check the project repository for documentation and issue tracking.

---

**🎉 Enjoy your new dynamic spin wheel system!** No more manual deployments needed - just configure and go!
