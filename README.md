# Polymarket Dashboard for Hoh Labs

A live Polymarket monitoring dashboard with price alerts.

## Features
- Live market data from Polymarket API
- Top 20 markets by 24h volume
- 5% price change alerts
- Tesla-inspired dark theme matching hohlabs.com
- Auto-refreshes every 60 seconds

## Deployment to hohlabs.com (WordPress)

### Option 1: Upload as Custom Page
1. Upload `index.html` to your WordPress media library or via FTP to the theme folder
2. Create a new WordPress page
3. Add a Custom HTML block with an iframe pointing to the dashboard:
```html
<iframe src="/wp-content/themes/your-theme/polymarket/index.html" 
        width="100%" height="1200" frameborder="0"></iframe>
```

### Option 2: FTP/SFTP Upload
1. Connect to hohlabs.com via FTP/SFTP
2. Upload `index.html` to `/wp-content/themes/[your-theme]/`
3. Access at: `hohlabs.com/wp-content/themes/[your-theme]/index.html`

### Option 3: GitHub Pages (Free Alternative)
1. Create a GitHub repository
2. Upload `index.html`
3. Enable GitHub Pages in settings
4. Access at `yourusername.github.io/repository/index.html`
5. Then embed via iframe in WordPress

## Local Testing
```bash
# Open directly in browser
open index.html

# Or serve locally
npx serve .
```

## Files
- `index.html` - Complete dashboard (no server needed)
- Works entirely client-side via Polymarket's public API

## API
Uses Polymarket's public Gamma API (no auth required):
- Endpoint: `https://gamma-api.polymarket.com/events`
- Rate limit: 4000 requests per 10 seconds

## Customization
- Edit `ALERT_THRESHOLD` in index.html to change alert sensitivity
- Default: 5% price movement

## Next Steps
- Add webhook notifications for alerts
- Add historical price charts
- Add trading signal suggestions
