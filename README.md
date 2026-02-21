# Wordwander

**Trace the journey of words across languages, cultures, and centuries.**

Wordwander is an interactive etymology visualization tool that maps how words migrated through historical languages and geographical regions to arrive in modern English. Type any word and watch its origin story unfold on an animated world map.

🌐 **Live site:** [kcowger.github.io/wordwander](https://kcowger.github.io/wordwander)

## What it does

- Fetches real etymology data from the Wiktionary API
- Traces complete word lineages across multiple languages (including recursive chain-following for modern Wiktionary's distributed etymology format)
- Plots each language on a high-resolution world map with animated migration paths
- Displays an interactive timeline alongside the map, synchronized during playback
- Shows phonetic romanizations for non-Latin scripts (Arabic, Greek, Cyrillic, Devanagari)
- Handles words with multiple etymologies via a sense picker
- Supports shareable URLs (`?w=sugar`)

## Features

- **Animated migration paths** connecting each language in the word's journey
- **Auto-zoom** that frames the entire journey on screen
- **Bidirectional hover highlighting** between the map and the timeline sidebar
- **Cognate branches** showing related words that split from the same root
- **High-resolution coastlines** rendered from Natural Earth GeoJSON data
- **Dot separation** so overlapping locations (like English, Middle English, and Old English in the UK) spread apart cleanly
- **Zoom, pan, and touch support** for exploring the map

## How it works

Wordwander is a single HTML file with no build step, no framework, and no server. It runs entirely in the browser.

1. User enters a word
2. The app fetches the word's Wiktionary page via their public API
3. It parses etymology templates (`{{inherited}}`, `{{borrowed}}`, `{{derived}}`, `{{etymon}}`)
4. For modern Wiktionary entries using distributed `{{etymon}}` templates, it recursively fetches ancestor pages to reconstruct the full chain
5. Each language in the chain is mapped to geographical coordinates and historical metadata
6. The journey is rendered as an animated SVG map and a synchronized sidebar timeline

## Examples to try

sugar · guitar · salary · philosophy · democracy · chocolate · coffee · algebra · tsunami · hurricane · pajama · kindergarten · avatar · karma · mosquito

## Tech

- Vanilla HTML/CSS/JS (single file, ~1000 lines)
- Wiktionary API for etymology data
- Natural Earth GeoJSON for world coastlines
- SVG for map rendering and animation
- No dependencies, no build tools

## License

MIT
