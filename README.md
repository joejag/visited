# Visited - European Countries Tracker

A visual interactive map of Europe tracking countries I've visited. The site displays a map with visited countries highlighted, progress by geographic region, and regional groupings.

## Features

- 🗺️ Interactive Europe map with all European countries
- 🎨 Visual highlighting of visited countries
- 📊 Progress tracking by geographic regions (Nordics, Balkans, etc.)
- 🎯 Predefined region groupings for travel planning
- 📱 Responsive design
- ⚡ Pure HTML/CSS/JavaScript (no dependencies)

## How It Works

- **Visited countries** are stored in `visited.json`
- When you visit a new country, add its ISO 3166-1 alpha-2 country code to `visited.json` and commit
- The map automatically updates to show your progress
- Regions display completion percentage and highlight when fully visited

## Setup

1. Clone the repository
2. Open `index.html` in a browser
3. To update visited countries, edit `visited.json` with country codes

## Country Codes

All European countries use their standard ISO 3166-1 alpha-2 codes:
- `DE` = Germany
- `FR` = France
- `IT` = Italy
- `ES` = Spain
- `GB` = United Kingdom
- etc.

## Regions

The map groups countries into:
- **Nordics**: Iceland, Norway, Sweden, Finland, Denmark
- **British Isles**: UK, Ireland
- **Benelux**: Netherlands, Belgium, Luxembourg
- **Central Europe**: Germany, Poland, Czech Republic, Slovakia, Austria, Switzerland
- **Western Europe**: France, Spain, Portugal
- **Southern Europe**: Italy, Slovenia, Malta, Greece, Cyprus, Turkey
- **Balkans**: Croatia, Bosnia, Serbia, Montenegro, Albania, North Macedonia, Bulgaria
- **Eastern Europe**: Ukraine, Belarus, Romania, Moldova
- **Baltics**: Lithuania, Latvia, Estonia
- **Russia (European)**: European Russia
- **Turkey (European)**: European Turkey
- **Microstates**: Andorra, Monaco, Liechtenstein, San Marino, Vatican City

## Deployment

This site is deployed to GitHub Pages at [https://visited.joejag.com](https://visited.joejag.com)

To deploy to your own domain:
1. Enable GitHub Pages in repository settings
2. Point your custom domain DNS to GitHub Pages
3. Add your domain in repository settings

## Future Improvements

- Better SVG map with accurate country shapes
- Hover tooltips with country names
- Year-by-year tracking of visits
- Custom region definitions
- Export/import functionality

