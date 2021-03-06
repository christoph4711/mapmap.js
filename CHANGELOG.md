# mapmap.js Changelog

## 0.2.8

### New

- New method `Map.symbolizeAttribute()` to assign any SVG attributes from data.
- New method `Map.zOrder()` to determine ordering of SVG elements
- Symbol depictions in HTML legend are SVG based now, for flexibility and consistency.
- New attributes `reverse`(boolean) and `order` (function) in HTML legend options to control ordering of classes
- Accessor functions for map panes (SVG (g)roup elements): `Map.getGeometryPane()`, `Map.getOverlayPane()`, `Map.getFixedPane()`.
- Accessor function for path generator ([d3.geo.path](https://github.com/d3/d3-3.x-api-reference/blob/master/Geo-Paths.md#path)): `Map.getPathGenerator()`

### Changes

- `Map.choropleth()` is now deprecated - use `Map.symbolize(mapmap.symbolize.choropleth(…))` instead
- `Map.hoverInfo()` shows up only if there is text to be shown
- `Map.projection()` now returns the projection if called without parameters
- New option for `Map.geomtry()`: `setExtent` (default: `true`) to determine whether map extent should be set to geometries' extent on load
- `Map.geometry()` now also accepts single GeoJSON objects

### Fixes

- Fix hoverInfo to hide properly on fast mouse movements

## 0.2.7

- Internal changes to legend generation code to make it more versatile, improve labeling of ranges (#11, #22)
- Greatly improved handling of missing, empty or invalid values (#23)
- Optional generation of histogram in HTML legend
- Remove dead code for SVG legend, should be recreated in the future 
- New metadata fields `valueUnit`, `undefinedLabel` and `undefinedColor` (See [documentation](https://github.com/floledermann/mapmap.js/wiki/API-Documentation#metadata-fields)).
- Improved positioning of hoverInfo (tooltips) when scrolled, fixed obscure Firefox bug for positioning them (#27).
- Warn if mapReduce transformation yielded no results
- Provide `activate` and `deactivate` functions for zoom behavior to style active element
- Fix bug causing zoom behavior to fail if no hoverInfo was active (#18)
- Fix usage of `center` option for zoom behavior
- Output warning message if Promise is missing (e.g. IE) and needs to be polyfilled

## 0.2.6

- Fix bug in hoverInfo introduced in 0.2.5

## 0.2.5

- Browser compatibility fixes for map resizing and hoverInfo positioning (#13)
- Support passing a file handler for customized parsing to `.data()` through the fileHandler option (#15).
- Support passing an accessor/row-conversion function to `.data()` through the `accessor` option (#10).

## 0.2.4

- Do not add inline CSS border to HTML legend color boxes - this can be easily added through CSS
- Upstream syntax fix in datadata library (#9)

## 0.2.3

- extent() now only modifies the projections scale and translation, leaving center alone. This allows using rotated projections.
- Support for TSV files
- Renamed `applyBehaviour()` -> `applyBehavior()`, `applyMapBehaviour()` -> `applyMapBehavior()` for consistent US spelling.
- Improved formatting of ranges for HTML legend

## 0.2.2

- Initial public release