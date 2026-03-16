# Personal Surf Forecasting System

This repo hosts a GitHub Pages surf forecast dashboard for Roman + Cato.

## Key Files

- `index.html` — the live dashboard (GitHub Pages serves this)
- `data/current_situation.md` — surfer profiles, location, preferences, system notes
- `data/best_conditions_for_surf_spots.json` — 57-spot database with ideal conditions per spot, grouped into forecast regions
- `data/skills/surf-forecast/SKILL.md` — full instructions for the forecast process
- `data/skills/update-situation/SKILL.md` — instructions for updating the situation file

## Chrome Scraping via AppleScript

Surfline requires a Premium login. Roman's Chrome has the cookies. Use `osascript` to control Chrome:

```bash
# Open a URL in Chrome
osascript -e 'tell application "Google Chrome" to set URL of active tab of front window to "https://www.surfline.com/..."'

# Get page text content
osascript -e 'tell application "Google Chrome" to execute active tab of front window javascript "document.body.innerText"'

# Click an element
osascript -e 'tell application "Google Chrome" to execute active tab of front window javascript "document.querySelector(\"SELECTOR\").click()"'
```

Wait ~3 seconds after navigation for Surfline's JS to render before extracting content.

## Git

Commit and push after updating index.html. Use message format: "Forecast update: YYYY-MM-DD [morning/evening]"
