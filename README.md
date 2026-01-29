# DRRP Official Website - Jekyll Multi-language Setup

## Structure

This website uses Jekyll with a single-source multi-language approach to be served using GitHub Pages.

### Key Files

- **`_includes/index-content.html`** - Single source of truth for all page content
  - Contains all language versions using `{% if page.lang == 'en' %}...{% endif %}` conditionals
  - Edit this file to update content for all languages

- **`_layouts/default.html`** - Shared layout for all pages
  - Dynamic metadata based on `page.lang`
  - Navigation with language flags

- **Language versions:**
  - `/index.html` - English (default, root URL)
  - `/ru/index.html` - Russian version
  - `/uk/index.html` - Ukrainian version

### How It Works

1. Each language version file sets only `lang` variable in front matter
2. All files include the same `index-content.html`
3. Content is shown/hidden based on `page.lang` value using Liquid conditionals

### Adding New Content

To add new content visible in all languages:

1. Edit `_includes/index-content.html`
2. Add content with language conditionals:
   ```liquid
   {% if page.lang == 'en' %}English text{% endif %}
   {% if page.lang == 'ru' %}Русский текст{% endif %}
   {% if page.lang == 'uk' %}Український текст{% endif %}
   ```

### Building

```bash
jekyll build
# or
jekyll serve
```

### URLs

- English: `https://drrp-team.github.io/`
- Russian: `https://drrp-team.github.io/ru/`
- Ukrainian: `https://drrp-team.github.io/uk/`
