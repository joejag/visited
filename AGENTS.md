# AGENTS.md

## Project Overview

This is a personal travel tracker that visualizes visited European countries on an interactive map. The project is a static HTML/CSS/JavaScript site deployed to GitHub Pages at https://visited.joejag.com.

## Architecture

- **Single-page application** built with vanilla JavaScript (no build process)
- **Dependencies**: Leaflet.js for mapping, TopoJSON for geographic data
- **Data source**: `visited.json` contains ISO 3166-1 alpha-2 country codes for visited countries
- **Deployment**: GitHub Pages with custom domain via CNAME

## File Structure

```
.
├── index.html        # Main application (HTML, CSS, JavaScript)
├── visited.json      # List of visited country codes
├── README.md         # User-facing documentation
├── CNAME             # Custom domain configuration
└── AGENTS.md         # This file
```

## Key Design Principles

1. **No build process**: All code is in a single HTML file for simplicity
2. **Minimal dependencies**: Uses CDN-hosted libraries (Leaflet, TopoJSON)
3. **Data-driven**: Country visits are managed through `visited.json`
4. **Visual clarity**: Clean UI with progress tracking and regional groupings
5. **Static deployment**: No backend, runs entirely in browser

## Component Architecture

### Color System
- Defined in `colors` object with harmonious blue/cool tones
- Consistent palette for visited (green), unvisited (grey), and region colors
- Each region has a distinct color for visual identification

### Region Definitions
- Countries grouped into 10 geographic regions (Nordics, Balkans, etc.)
- Each region has: country list, color, and emoji identifier
- Used for progress tracking and sidebar organization

### Map Rendering
- Uses world-atlas TopoJSON data filtered to European countries
- Country code mapping from UN codes to ISO 3166-1 alpha-2
- Styling differentiates visited (saturated, region-colored) from unvisited (desaturated grey)
- Malta rendered as point marker due to its small size in 110m dataset

### Statistics
- Circular progress ring showing overall completion
- Count of visited vs. unvisited countries
- Motivational text changes based on progress

### Sidebar
- Regional breakdown with progress bars
- Country tags (visited = green checkmark, unvisited = grey circle)
- Hover effects for interactivity

## Common Tasks

### Adding a Visited Country
1. Add the ISO 3166-1 alpha-2 code to `visited.json`
2. Commit and push to GitHub
3. GitHub Pages will automatically deploy

### Adding a New Country to Track
1. Add country code to appropriate region in `regions` object
2. Add country code mapping in `countryNames` object
3. Add TopoJSON mapping in `countryNameMap` if needed (UN code → ISO code)
4. Update README.md region list

### Modifying Regions
1. Edit `regions` object to add/remove countries or change colors
2. Ensure all country codes exist in `countryNames` and `europeanCountries` set
3. Consider updating region emoji if changing region scope

### Styling Changes
1. Modify CSS in `<style>` block
2. Use existing color variables from `colors` object for consistency
3. Maintain responsive breakpoints (@media queries at 1024px and 768px)

## Development Guidelines

### When Making Changes

1. **Preserve simplicity**: Avoid adding build tools or frameworks
2. **Test locally**: Open `index.html` in a browser to verify changes
3. **Maintain data separation**: Keep visited countries in `visited.json`, not hardcoded
4. **Follow existing patterns**: Use the established color system and component structure
5. **Ensure responsiveness**: Test on mobile viewport sizes

### Code Style

- Use ES6+ JavaScript features (async/await, arrow functions, template literals)
- Inline styles use the `colors` object for consistency
- Comments mark major sections with decorative separators
- Descriptive variable names (e.g., `visitedCountries`, `regionMap`)

### Common Pitfalls

- **Country code mismatches**: Ensure UN codes in `countryNameMap` correctly map to ISO codes
- **Malta rendering**: It's a special case rendered as a point marker
- **Progress animations**: Use setTimeout for CSS transition triggers
- **CDN versions**: Pin Leaflet and TopoJSON versions to avoid breaking changes

## API Reference

### Global Variables
- `visitedCountries`: Array of ISO country codes loaded from `visited.json`
- `regions`: Object defining regional groupings, colors, and emojis
- `regionMap`: Lookup table mapping country code → region data
- `countryNames`: Mapping of ISO codes to full country names
- `europeanCountries`: Set of all tracked European country codes

### Key Functions
- `loadVisited()`: Fetches `visited.json` and initializes map
- `loadMap()`: Loads TopoJSON data and renders Leaflet map
- `updateStats()`: Calculates and displays progress statistics
- `renderRegions()`: Builds sidebar regional breakdown
- `lightenColor(color, opacity)`: Utility for color manipulation
- `getFeatureCentroid(geometry)`: Calculates label placement

## Testing

Since this is a static site with no automated tests:

1. **Visual testing**: Open `index.html` and verify:
   - Map renders correctly
   - Visited countries are highlighted in region colors
   - Unvisited countries are light grey
   - Statistics show correct counts and percentages
   - Regional progress bars are accurate
   - Responsive layout works on mobile sizes

2. **Data validation**:
   - Ensure all codes in `visited.json` are valid ISO 3166-1 alpha-2
   - Check that all codes exist in `europeanCountries` set
   - Verify no duplicate country codes across regions

3. **Browser compatibility**: Test in Chrome, Firefox, Safari

## Future Enhancements (from README)

- Better SVG map with accurate country shapes
- Hover tooltips with country names
- Year-by-year tracking of visits
- Custom region definitions
- Export/import functionality

When implementing these, maintain the no-build-process philosophy and data-driven approach.
