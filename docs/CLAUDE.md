# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

This is a static website with no build process. Common development tasks:

- **Live preview**: Serve the site locally for testing
  ```bash
  # Using Python (built-in)
  python -m http.server 8000
  
  # Or using Node.js if available
  npx serve .
  ```
  
- **Deployment**: The site is deployed to Vercel via GitHub integration
  - Pushes to `main` branch trigger automatic deployment
  - Manual deployment: Push to GitHub or use Vercel CLI
  
- **Asset updates**: 
  - Place new images in `assets/` directory
  - Update references in HTML/CSS as needed
  - Optimize images for web use (the site uses various sizes for favicons/apple-touch-icon)

## Code Architecture

### Tech Stack
- **HTML5**: Semantic markup with accessibility considerations (ARIA labels, lang attributes)
- **CSS3**: Modern CSS with CSS variables for theming, responsive design, and smooth interactions
- **JavaScript**: Minimal vanilla JS (only updates the year in footer)
- **Deployment**: Vercel (static site hosting)

### File Structure
```
index.html      # Main landing page
styles.css      # All styling (CSS variables, responsive layout)
script.js       # Minimal JS (year update)
assets/         # Static assets:
                #   - appicon.png, favicon-*.png (site icons)
                #   - logo.jpg (OG image)
                #   - logo/*.svg (provider logos for cloud fallback)
                #   - img/*.gif (feature illustrations)
docs/           # Documentation:
                #   - PRODUCT.md (product details)
                #   - DESIGN.md (design decisions)
```

### Key Design Patterns
1. **Responsive Layout**: Uses CSS `clamp()`, `minmax()`, and flexible grids
2. **CSS Variables**: Centralized theme colors in `:root` for easy theming
3. **Smooth Interactions**: Subtle transitions on hover/focus states
4. **Accessibility**: 
   - Proper ARIA labels
   - Semantic HTML elements
   - Focus outlines
   - Reduced motion support
5. **Performance**:
   - Optimized asset sizes (logos as SVGs where possible)
   - System fonts to avoid font loading delays
   - Lazy loading on images (`loading="lazy"`)
   - Minimal JavaScript

### Component Organization
The page is divided into clear sections:
- **Header**: Sticky navigation with brand logo
- **Hero**: Main value proposition with download CTA
- **Features**: 6-card grid illustrating key capabilities
- **Privacy**: Two-column text layout explaining data protection
- **Download**: Prominent APK download button
- **Footer**: Copyright and tagline

### Styling Approach
- Mobile-first responsive design
- CSS variables for consistent theming
- Flexbox and Grid for layout
- Subtle gradients and shadows for depth
- Consistent spacing and border-radius

## Common Tasks

### Updating Content
1. **Text changes**: Edit `index.html` directly
2. **Styling changes**: Modify `styles.css` (CSS variables at top for theme colors)
3. **Adding features**: 
   - Add new card to `.grid` in features section
   - Update corresponding section in HTML
   - Add any new assets to `assets/img/`
4. **Changing logos**: Replace files in `assets/logo/` and update HTML references
5. **Updating GIFs**: Place new animations in `assets/img/` and reference in HTML

### Deployment Notes
- The site is configured for Vercel deployment via `.vercel/project.json`
- All static files are served as-is (no build step)
- Ensure assets are web-optimized before committing
- The APK is served via GitHub releases (not stored in repo due to size)

### Development Best Practices
- Keep CSS modifications minimal - reuse existing variables and classes
- Optimize any new images (especially GIFs) for web use
- Test responsiveness across device sizes
- Maintain accessibility standards (color contrast, focus states)
- Keep JavaScript minimal - prefer CSS for interactions when possible