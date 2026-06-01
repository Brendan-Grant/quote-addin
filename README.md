# Quote Builder — Outlook Add-in

Select items from your SharePoint price list and insert a formatted quote table directly into an Outlook email.

## Files in this repository

| File | Purpose |
|---|---|
| `taskpane.html` | The add-in UI that loads inside Outlook |
| `commands.html` | Required blank page for the manifest |
| `manifest.xml` | Upload this to M365 Admin Center to deploy the add-in |
| `assets/` | Icon images (see below) |

## Setup steps

### 1. Replace YOUR-GITHUB-USERNAME
Do a find-and-replace in `manifest.xml` — swap every instance of `YOUR-GITHUB-USERNAME` with your actual GitHub username.

### 2. Add icon images
Place these PNG files in the `assets/` folder:
- `icon-16.png` (16×16)
- `icon-32.png` (32×32)
- `icon-64.png` (64×64)
- `icon-80.png` (80×80)
- `icon-128.png` (128×128)

You can use any simple icon. A plain blue square with "Q" works fine.

### 3. Enable GitHub Pages
In your GitHub repository: Settings → Pages → Source: Deploy from branch → Branch: main → / (root) → Save.

Wait ~2 minutes, then visit:
`https://YOUR-GITHUB-USERNAME.github.io/quote-addin/taskpane.html`

If you see the add-in UI, hosting is working.

### 4. Update Azure redirect URI
In portal.azure.com → App registrations → Quote Builder Add-in → Authentication:
Add redirect URI: `https://YOUR-GITHUB-USERNAME.github.io/quote-addin/taskpane.html`

### 5. Deploy via M365 Admin Center
1. Go to admin.microsoft.com
2. Settings → Integrated apps → Upload custom app
3. Upload `manifest.xml`
4. Assign to yourself (or all users) → Deploy

### 6. Use the add-in
1. Open Outlook and compose a new email
2. Click **Insert Quote** in the ribbon
3. Sign in with Microsoft 365
4. Click ⚙ Config and enter your SharePoint file URL and path
5. Search, select items, click **Insert quote table into email**
