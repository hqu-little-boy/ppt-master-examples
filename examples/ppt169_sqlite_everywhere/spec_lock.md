<!-- ppt-master-schema: spec-lock/v1 -->
# Execution Lock

## canvas
- viewBox: 0 0 1280 720
- format: PPT 16:9

## communication
- primary_language: en
- audience: Software engineers at an internal tech talk who use client/server databases and may see SQLite as a toy
- objective: Explain why SQLite is the most deployed database through its evidence, architecture, journaling, testing, and license, so engineers can describe the layer stack and the rollback-vs-WAL trade-off and apply sqlite.org's when-to-use checklist
- core_message: SQLite is everywhere because it competes with fopen(), not Oracle — an in-process, zero-config, single-file engine with test code 590× the library and no license at all
- consumption_mode: balanced

## mode
- mode: custom
- mode_references: instructional, pyramid
- mode_behavior: Open with conclusion-level deployment evidence, then teach the mechanism top-down through the layer stack in ordered annotated steps, one layer or mechanism per page; close with trust factors and an applicable decision checklist. Titles state what the page teaches.

## visual_style
- visual_style: custom
- visual_style_references: blueprint
- visual_style_behavior: Sheets from one engineering drawing set — deep navy paper with a faint 32 px grid, structure in thin single-weight pale-cyan line work with 2 px corners, components as outlined boxes with mono component codes, arrowed connectors, dimension lines and leader-line annotations instead of cards; one amber spot accent per page marks the current layer, key path, or hero number; a small drawing-sheet title block anchors the lower-right of every content page; depth from isometric layering and line weight, never shadows.

## colors
- background: #0B1F3A
- secondary_bg: #11294B
- primary: #8CC4EE
- accent: #FFB547
- secondary_accent: #5ED3C4
- body_text: #EAF2FB
- secondary_text: #9FB6CF
- divider: #2D4C74
- grid: #16305A
- negative: #FF7A6B
- image_rendering: custom
- image_rendering_references: blueprint
- image_rendering_behavior: Technical blueprint line drawing on deep navy paper with crisp uniform pale-cyan strokes, isometric axonometric projection, faint low-opacity grid, and a single amber highlight on the focal element; no shading, texture, glow halos, or painterly marks — an exploded-assembly drafting sheet.

## typography
- font_family: Segoe UI, sans-serif
- title_family: Bahnschrift, sans-serif
- body_family: Segoe UI, sans-serif
- code_family: Consolas, monospace
- display_family: Bahnschrift, sans-serif
- hero_family: Bahnschrift, sans-serif
- body: 22
- title: 40
- subtitle: 28
- lead: 26
- annotation: 16
- footnote: 13
- code: 17
- kicker: 15
- cover_title: 76
- hero: 112

## icons
- library: tabler-outline
- stroke_width: 1.5
- inventory: tabler-outline/database, tabler-outline/file, tabler-outline/server, tabler-outline/device-mobile, tabler-outline/device-desktop, tabler-outline/device-tv, tabler-outline/car, tabler-outline/browser, tabler-outline/code, tabler-outline/binary, tabler-outline/stack-2, tabler-outline/lock, tabler-outline/shield-check, tabler-outline/bug, tabler-outline/test-pipe, tabler-outline/license, tabler-outline/network, tabler-outline/users, tabler-outline/bolt, tabler-outline/refresh, tabler-outline/file-zip, tabler-outline/circle-check, tabler-outline/circle-x, tabler-outline/alert-triangle, tabler-outline/settings-off, tabler-outline/certificate, tabler-outline/cpu, tabler-outline/world, tabler-outline/terminal-2, tabler-outline/feather, simple-icons/sqlite, simple-icons/android, simple-icons/apple, simple-icons/windows, simple-icons/firefoxbrowser, simple-icons/googlechrome, simple-icons/safari, simple-icons/skype, simple-icons/itunes, simple-icons/dropbox, simple-icons/python, simple-icons/php, simple-icons/quickbooks

## images
- cover: images/cover_file_stack_fit.jpg | source=ai | crop=adaptive
- closing: images/closing_file_stack_dim.jpg | source=ai | crop=adaptive

## page_rhythm
- P01: anchor
- P02: dense
- P03: dense
- P04: dense
- P05: dense
- P06: dense
- P07: dense
- P08: dense
- P09: dense
- P10: breathing
- P11: dense
- P12: anchor

## page_visualizations
- P09: table/metric_table

## pptx_structure
- mode: flat

## forbidden
- `mask`, `<style>`, `class`, external CSS, `<foreignObject>`, `textPath`, `@font-face`, `<animate*>`, `<set>`, `<script>` / event attributes, `<iframe>`
- HTML named entities in text; write typography as raw Unicode and escape XML reserved characters
