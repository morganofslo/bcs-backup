bcs-backup
==========

Backup and Restore BCS-460, BCS-462, and BCS-482 brew controller devices running 4.x firmware.  

## Getting Started

Check it out in action at [http://lawn-chair.github.io/bcs-backup](http://lawn-chair.github.io/bcs-backup)

## Usage Notes

- **Authentication must be disabled** on your BCS device for this utility to work. The browser's CORS restrictions prevent authenticated requests from working properly.
- After backup/restore, you can re-enable authentication on your BCS.

## Architecture

This is a static web application that communicates directly with BCS brewery controllers via their REST API.

```
resources/
├── js/index.js      # Main application logic (backup/restore)
├── pug/             # Pug templates → compiled to HTML
└── stylus/          # Stylus styles → compiled to CSS
vendor/
└── js/FileSaver.js  # Third-party library for file downloads
site/                # Build output (static site)
```

The application uses:
- **Pug** for HTML templating
- **Stylus** for CSS preprocessing
- **jQuery** for DOM manipulation
- **Async.js** for managing sequential API calls
- **BCS library** (loaded externally) for device communication

## Building and Running Locally

### Prerequisites

- Node.js

### Setup

```bash
npm install
```

### Development

```bash
npm run build   # Build the project (compile Pug, Stylus, concat JS)
npm run watch   # Watch for changes and rebuild automatically
```

Or using npx directly:

```bash
npx grunt
npx grunt watch
```

### Production Build

```bash
npm run dist    # Build with minified JavaScript
```

### Serving Locally

After building, start a local server:

```bash
npm start       # Serves site/ on http://localhost:3000
```

### Deploying to GitHub Pages

```bash
npm run deploy
```

