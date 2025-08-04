# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **BetaWorx steel company website** built with Astro 5.11.0 and Tailwind CSS 4.x. The site is a single-page application showcasing steel construction and manufacturing services with a professional gunmetal and silver color scheme.

## Development Commands

- `npm run dev` - Start development server at localhost:4321
- `npm run build` - Build production site to ./dist/
- `npm run preview` - Preview production build locally
- `npm run astro` - Run Astro CLI commands

## Architecture

### Tech Stack
- **Astro 5.11.0** - Static site generator with component-based architecture
- **Tailwind CSS 4.x** - Utility-first CSS framework (configured via Vite plugin)
- **TypeScript** - Type checking with strict configuration

### Project Structure
```
src/
├── components/        # Reusable UI components
├── layouts/          # Page layouts
├── pages/            # Route-based pages
└── styles/           # Global styles
```

### Component Architecture
- **Layout.astro** - Main layout wrapper with global navigation
- **index.astro** - Single-page application entry point that imports all sections
- **Component pattern** - Each section is a separate Astro component (Hero, Services, About, etc.)

### Page Flow
The site follows a single-page application pattern:
1. All sections are imported in `src/pages/index.astro`
2. Layout wrapper includes fixed navigation
3. Components are rendered sequentially: Hero → SocialProof → Services → About → Testimonials → Contact → Footer

### Styling System
- **Custom Color Palette**: Gunmetal (#2C3539), Dark Gunmetal (#1F2528), Silver (#C0C0C0), Light Silver (#eeeded)
- **CSS Variables**: Colors defined in component-level `:root` selectors
- **Tailwind Integration**: Custom colors mixed with Tailwind utilities
- **Responsive Design**: Mobile-first approach with breakpoint-specific styling

### Navigation
- **Fixed navbar** with smooth scrolling to sections
- **Mobile hamburger menu** with JavaScript toggle functionality
- **Active state tracking** based on scroll position
- **Scroll offset**: 80px to account for fixed navbar height

## Key Features

### Interactive Elements
- Smooth scrolling navigation
- Mobile responsive hamburger menu
- Scroll-based active navigation states
- Custom hover effects and transitions

### Image Handling
- Hero background image: `/public/images/HeroImage.jpg`
- Astro asset imports for optimized loading
- Responsive image sizing

### Custom JavaScript
- Mobile menu toggle functionality
- Smooth scrolling implementation
- Active section highlighting
- Click outside to close mobile menu

## Development Notes

### Color System
All components use consistent CSS custom properties for the steel company branding. When adding new components, follow the existing color variable pattern rather than hardcoding colors.

### Component Development
- Each major section is a separate `.astro` component
- Components include both HTML structure and component-scoped styles
- Follow the existing pattern of frontmatter, HTML, and `<style>` blocks

### Responsive Design
The site uses a mobile-first approach with careful attention to:
- Typography scaling across breakpoints
- Button and CTA responsiveness
- Navigation menu behavior
- Trust indicator grid layouts