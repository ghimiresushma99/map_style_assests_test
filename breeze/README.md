# Generating Icon Sprites

**Modify Icons**

1. Import "raw_files_osm_liberty/iconset-osm_liberty.json" to the [Maki Editor](https://www.mapbox.com/maki-icons/editor/).
2. Apply your changes and download the icons in SVG format and the iconset in JSON format.
3. Optional: Format the JSON with `cat iconset.json | jq -MS '.'` for better legibility.
4. Add the SVG files from the folder [svgs_not_in_iconset](https://github.com/maputnik/osm-liberty/tree/gh-pages/svgs/svgs_not_in_iconset) to the folder `svgs` downloaded from the Maki Editor.
These are the SVGs for road shields, the dot used for city and town layers and the road area pattern which could not be modified using the Maki Editor. To modify these you could use e.g. [Inkscape](https://inkscape.org).
5. Install [spritezero-cli](https://github.com/mapbox/spritezero-cli). I had to use node version 8.17.0: `npm install -g @mapbox/spritezero-cli`
6. Generate the low resolution sprite: `spritezero osm-liberty ./svgs/`
7. Generate the high resolution sprite: `spritezero --retina osm-liberty@2x ./svgs/`

## Reference

- [OSM Liberty](https://github.com/maputnik/osm-liberty) 