# bauhaus_1919_1933

- Canvas format: ppt169 (1280×720)
- Created: 20261024
- Runtime: Default Generate (Strategist → Image_Generator → Executor) from a bare topic with topic research; free design
- Sources: the topic-research pair in `sources/` (thirty cited facts, with conflicting figures noted); no fact URL is expanded at export
- Mode / visual style: a design-history feature in a custom editorial archive style — warm paper, fine rules, Arial Black year numerals, a single vermilion focus; the Bauhaus circle, square and triangle act as page fields and picture windows
- Structure diagrams drawn natively: the 1919–1933 Gantt chart across three cities and directors, the preliminary-course rings, the form/craft master pairing, the masters' year ruler, the closure sequence and the emigration routes
- Images: five CC-licensed Wikimedia photographs credited on the page and recorded in `images/image_sources.json` (the Dessau building also as an ink-and-paper duotone derivative), plus one AI workshop scene labelled as not a historical photograph; all JPEG q82 at ≤1920px. The 1926 masters' rooftop photo and Bayer's original alphabet had no openly licensed source and were dropped from the plan; the universal-type page uses a labelled native letter specimen
- Object animations and four Morph transitions (the cover circle becomes the manifesto seal; the object pedestal turns circle → square → triangle across pages 8–10; the diaspora origin grows into the closing circle); Chinese speaker notes

## Directories

- `svg_output/`, `svg_final/`, `images/`, `icons/`, `notes/`, `sources/`, `analysis/`, `animations.json`, `design_spec.md`, `spec_lock.md`, `exports/` as in the other examples

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir>
```
