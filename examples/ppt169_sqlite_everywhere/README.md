# sqlite_everywhere

- Canvas format: ppt169 (1280×720)
- Created: 20261024
- Runtime: Default Generate (Strategist → Image_Generator → Executor); free design
- Sources: eight official sqlite.org pages (about, mostdeployed, arch, fileformat2, wal, testing, whentouse, copyright) fetched with `source_to_md.py` into `sources/`; every figure on the deck traces to them and each page names its source page in the title block
- Mode / visual style: an engineering tech talk in a custom "Drafting Sheet" blueprint style — navy paper with a faint grid, pale-cyan single-weight line work, one amber accent per page, a drawing-sheet title block on every content page
- Structure diagrams drawn natively: the eight-layer architecture stack, the compile and storage paths, B-tree page anatomy, rollback journal vs write-ahead log, WAL frames and checkpoints, the three-question selection checklist; the 590× test-to-library ratio as two area-proportional squares
- Images: one AI isometric exploded-file illustration (not bundled at source resolution; its prompt stays in `images/image_prompts.json`) with two derivatives — the fitted cover and a dimmed, blurred closing background (JPEG q82)
- Object animations and three Morph transitions (the layer stack becomes a rail highlighting the compile layers, then the storage layers; the WAL file grows into the frame timeline); English speaker notes

## Directories

- `svg_output/`, `svg_final/`, `images/`, `icons/`, `notes/`, `sources/`, `analysis/`, `animations.json`, `design_spec.md`, `spec_lock.md`, `exports/` as in the other examples

## Regenerate the PPTX

```bash
python3 skills/ppt-master/scripts/svg_quality_checker.py <this_dir> --canonical-authoring --stage final --json
python3 skills/ppt-master/scripts/svg_to_pptx.py <this_dir>
```
