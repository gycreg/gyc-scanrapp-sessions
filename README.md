# Session Configuration for GitHub Sync

This folder contains the session configuration that will be synced to all conference staff devices.

## Setup Instructions

### 1. Create a GitHub Repository

Example repository name: `gyc-2025-sessions`

### 3. Get the Raw File URL

The sync feature needs the **raw content URL** from GitHub. To get it:

1. Navigate to `sessions.json` in your GitHub repository
2. Click the "Raw" button
3. Copy the URL from your browser

The URL format will be:
```
https://raw.githubusercontent.com/YOUR-ORG/REPO-NAME/main/sessions-config/sessions.json
```

Example:
```
https://raw.githubusercontent.com/gyc-conference/gyc-2025-sessions/main/sessions-config/sessions.json
```

### 4. Share the URL with Staff

Give this raw URL to all conference staff members. They will:

1. Open the QR Scanner app
2. Go to Settings (bottom navigation)
3. Tap "Sync Sessions from GitHub"
4. Paste the raw URL
5. Tap "Sync"

All 5 sessions will be automatically created on their devices!

## Updating Sessions

To update sessions for all staff:

1. Edit `sessions.json` in this folder
2. Commit and push changes to GitHub
3. Staff members can tap "Sync Sessions from GitHub" again
4. Duplicate sessions will be skipped (or renamed with " - Copy N" suffix)

## File Format

The `sessions.json` file follows this structure:

```json
{
  "version": "1.0",
  "event": "Event Name",
  "sessions": [
    { "name": "Session name here" },
    { "name": "Another session" }
  ]
}
```

### Required Fields

- `version`: Format version (currently "1.0")
- `sessions`: Array of session objects
- `sessions[].name`: The session name (required)

### Guidelines

- Session names should be descriptive and unique
- Include day, speaker, and time in the name for clarity
- Keep names under 100 characters for best display
- Avoid special characters that might cause issues (though most work fine)

## Troubleshooting

### "No internet connection" error
- Ensure device has internet access
- Try again when connected

### "Failed to fetch" error
- Verify the URL is correct and points to the raw content
- Ensure the repository is public
- Check GitHub status if issues persist

### "Invalid configuration format" error
- Verify `sessions.json` is valid JSON
- Ensure all required fields are present
- Check for typos or missing commas

### Sessions not appearing
- Verify sync completed successfully
- Check the Sessions page (bottom navigation)
- Restart the app if needed

## Security Note

This repository should be **public** so staff devices can access it without authentication. Do not include sensitive information in session names or configuration files.
