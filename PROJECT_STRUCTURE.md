# Project Structure

This Jekyll blog uses the al-folio academic theme with the following organization:

## Directory Structure

```
cjmlarson.github.io/
├── _data/              # Data files
│   ├── gpx/           # GPS track files
│   ├── tracks/        # Processed track data (GeoJSON, etc.)
│   ├── cv.yml         # CV data
│   └── repositories.yml
├── _includes/          # Reusable components
│   └── maps/          # Map-related includes
├── _layouts/           # Page templates
├── _pages/             # Static pages (about, etc.)
├── _posts/             # Blog posts (YYYY-MM-DD-title.md)
├── _sass/              # SCSS stylesheets
│   └── _posts.scss    # Custom post styling
├── _site/              # Generated site (git-ignored)
├── assets/             # Static assets
│   ├── img/           # Images
│   │   └── posts/     # Post-specific images
│   │       └── weissmies/  # Images for Weissmies post
│   ├── css/           # Compiled CSS
│   └── js/            # JavaScript files
├── docker-compose.yml  # Main Docker configuration
├── _config.yml         # Main Jekyll configuration
├── _config_dev.yml     # Development overrides (faster builds)
└── _config_fast.yml    # Ultra-fast dev mode

## Development

### Running locally with Docker:
```bash
docker-compose up
```
Site will be available at http://localhost:8080

### Configuration files:
- `_config.yml`: Main configuration
- `_config_dev.yml`: Disables slow plugins for faster development
- `_config_fast.yml`: Bare minimum plugins for ultra-fast rebuilds

### Adding new blog posts:
1. Create file in `_posts/` with format: `YYYY-MM-DD-title.md`
2. Add images to `assets/img/posts/[post-name]/`
3. Use front matter for metadata (layout, title, tags, etc.)

### Map data:
- GPX files: Store in `_data/gpx/`
- Processed GeoJSON: Store in `_data/tracks/`
- Map components: Create in `_includes/maps/`