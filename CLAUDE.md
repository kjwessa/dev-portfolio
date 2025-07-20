# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static personal portfolio website for Kevin Wessa built with vanilla HTML, CSS, and JavaScript. It features a card-based layout showcasing different aspects of Kevin's life and work.

## Technology Stack

- **Pure HTML/CSS/JavaScript**: No frameworks or build tools
- **Static Website**: Traditional web development approach
- **Custom Fonts**: Uses "Permanent Marker" font via @font-face
- **Responsive Design**: Flexbox-based layout with mobile-first approach

## Development Commands

Since this is a vanilla HTML/CSS/JS project, there are no build commands or package scripts. Development workflow:

```bash
# View the site locally
open index.html
# Or serve via Python (if needed for testing)
python3 -m http.server 8000
# Or serve via Node.js (if available)
npx serve .
```

## Architecture and Structure

### Key Files
- `index.html` - Main portfolio page with semantic HTML structure
- `style.css` - Complete styling with responsive card layout
- `fonts/` - Custom font files (PermanentMarker.ttf, .woff)
- `images/` - Optimized portfolio images for each section

### Layout Structure
The site uses a **card-based architecture** with:
- **Hero Header**: Full viewport height with background image overlay
- **Card Grid**: Four main content cards (Family, Friends, Web Development, Business)
- **Footer**: Simple contact information

### CSS Organization
- CSS reset and box-sizing normalization at top
- Custom font definitions with @font-face
- Component-like organization: header styles, card styles, footer styles
- Responsive design using flexbox (cards are 350px with flex-wrap)

## Code Patterns

### HTML Structure
- Uses semantic HTML5 elements (`<header>`, `<section>`, `<footer>`)
- Each card follows consistent structure: image, title, description
- Proper alt attributes for accessibility

### CSS Conventions
- BEM-like naming conventions
- Consistent use of flexbox for layout
- Mobile-first responsive approach
- Image overlay technique for header background

## Development Considerations

- **No Build Process**: Files can be edited directly and viewed in browser
- **Image Optimization**: All images are already web-optimized (.opt extensions)
- **Font Loading**: Custom fonts are self-hosted for performance
- **Static Deployment**: Ready for deployment to any static hosting service
- **Browser Compatibility**: Uses modern CSS features (flexbox, CSS3)

## Content Sections

The portfolio currently has four main cards:
1. **Family** - Personal/family content with IMG_2128.2000.opt.jpeg
2. **Friends** - Social content with IMG_0174.2000.opt.JPG  
3. **Web Development** - Professional work with web-dev.2000.opt.jpeg
4. **Business** - Business/entrepreneurship with screenshot

## Git Workflow

- Uses Graphite for enhanced git workflow (`.graphite_*` files present)
- Clean commit history showing progressive development
- Main branch for primary development