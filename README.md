# OAuth Callbacks - Social Aggregator

This directory contains the OAuth callback pages for Social Aggregator's social media integrations.

## 📁 Directory Structure

```
oauth-callbacks/
├── index.html              # Main landing page
├── README.md              # This file
├── spotify/
│   ├── callback.html      # Spotify OAuth callback handler
│   └── success.html       # Spotify success page
└── discord/
    ├── callback.html      # Discord OAuth callback handler
    └── success.html       # Discord success page
```

## 🔧 Setup Instructions

### 1. Deploy to GitHub Pages

1. Push this entire `oauth-callbacks` folder to your GitHub repository
2. Enable GitHub Pages in your repository settings
3. Set the source to the root directory
4. Your callback URLs will be:
   - `https://ikarman4.github.io/oauth-callbacks/spotify/callback`
   - `https://ikarman4.github.io/oauth-callbacks/discord/callback`

### 2. Update OAuth App Settings

#### Spotify App Configuration:
1. Go to [Spotify Developer Dashboard](https://developer.spotify.com/dashboard)
2. Select your app
3. Click "Edit Settings"
4. Add redirect URI: `https://ikarman4.github.io/oauth-callbacks/spotify/callback`
5. Save changes

#### Discord App Configuration:
1. Go to [Discord Developer Portal](https://discord.com/developers/applications)
2. Select your application
3. Go to OAuth2 settings
4. Add redirect URI: `https://ikarman4.github.io/oauth-callbacks/discord/callback`
5. Save changes

## 🎯 How It Works

### OAuth Flow:
1. User clicks "Connect Spotify/Discord" in the app
2. App opens browser with authorization URL
3. User authorizes the app on the platform
4. Platform redirects to callback page with authorization code
5. Callback page processes the code and sends it back to the app
6. App exchanges code for access token
7. User's account is connected

### Callback Page Features:
- ✅ **Error Handling**: Displays clear error messages
- ✅ **Security**: Validates state parameter
- ✅ **User Experience**: Beautiful UI with loading states
- ✅ **Auto-close**: Automatically closes window after success
- ✅ **Debug Info**: Shows authorization details for troubleshooting
- ✅ **Retry Logic**: Allows users to retry failed authorizations

## 🔒 Security Features

- **State Parameter Validation**: Prevents CSRF attacks
- **Error Handling**: Secure error message display
- **HTTPS Only**: All callbacks use secure connections
- **No Sensitive Data**: Only authorization codes are handled

## 🎨 Customization

### Styling:
- Each platform has its own color scheme
- Responsive design works on all devices
- Modern glassmorphism UI design
- Smooth animations and transitions

### Functionality:
- Easy to add new platforms
- Configurable auto-close timers
- Customizable success messages
- Debug mode for development

## 🚀 Adding New Platforms

To add a new platform (e.g., Twitter, YouTube):

1. Create a new directory: `oauth-callbacks/twitter/`
2. Copy `spotify/callback.html` and modify:
   - Update colors and branding
   - Change OAuth URLs and scopes
   - Update postMessage types
3. Create `twitter/success.html`
4. Update `index.html` to include the new platform
5. Update your app's OAuth configuration

## 🐛 Troubleshooting

### Common Issues:

1. **"Invalid redirect URI"**
   - Ensure the redirect URI in your OAuth app matches exactly
   - Check for trailing slashes or case sensitivity

2. **"State parameter mismatch"**
   - The state parameter must be preserved throughout the flow
   - Check that your app generates and validates the same state

3. **"Authorization code not received"**
   - Check browser console for JavaScript errors
   - Verify the callback URL is accessible
   - Ensure the OAuth app is configured correctly

4. **"Window won't close"**
   - Some browsers block window.close() for security
   - The success page will show a manual close option

### Debug Mode:
- Open browser developer tools
- Check the console for detailed logs
- The callback pages show authorization details
- Use the "Try Again" button to retry failed flows

## 📱 Mobile Support

The callback pages work on mobile devices and include:
- Touch-friendly buttons
- Responsive design
- Custom URL scheme support
- Proper viewport configuration

## 🔄 Updates

When updating the callback pages:
1. Test the OAuth flow thoroughly
2. Update the version in the HTML comments
3. Clear browser cache if needed
4. Verify all platforms still work

---

**Note**: These callback pages are designed to work with the Social Aggregator app. Make sure your app is configured to handle the postMessage events and custom URL schemes sent by these pages.
