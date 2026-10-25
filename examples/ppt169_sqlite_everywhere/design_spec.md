<!-- ppt-master-schema: design-spec/v1 -->
# SQLite Everywhere - Design Spec

## I. Project Information

| Item | Value |
| --- | --- |
| Project Name | sqlite_everywhere_ppt169_20261024 |
| Canvas Format | ppt169 — PPT 16:9, 1280×720 |
| Page Count | 12 |
| Primary Language | en |
| Target Audience | Software engineers at an internal technical sharing session; they write SQL and run client/server databases, and may think of SQLite as a toy or test-only store |
| Communication Intent | Explain why SQLite is the most deployed database: first the deployment evidence, then the mechanism (in-process architecture, layer stack, B-tree pages, rollback journal vs WAL), then the trust factors (testing culture, public-domain license); finish by teaching the official when-to-use / when-not-to-use judgment |
| Desired Audience Outcome | Engineers can describe SQLite's layer stack and the rollback-journal vs WAL trade-off, and can apply sqlite.org's checklist to decide when SQLite fits and when a client/server engine is the better choice |
| Core Message / Ask / Action | SQLite is everywhere because it competes with fopen(), not with Oracle: an in-process, zero-configuration, single-file engine, verified by test code 590× the size of the library and free of any license |
| Delivery Context | Presenter-led engineering tech talk (about 20 minutes, projected); secondary: the deck is shared afterwards as a reference |
| Artifact Afterlife | Shared reference deck for the team; sources cited on page so readers can follow up on sqlite.org |
| Reading Mode | balanced |
| Content Strategy | balanced default (content_divergence left blank): re-architect the official sqlite.org pages into one teaching arc, keeping every figure exactly as published |
| Design Style | Custom "Drafting Sheet" — engineering blueprint schematic on dark paper (direction 0 of 3, selected) |
| AI Image Acquisition Path | auto |
| Generation Mode | continuous |
| Spec Refinement | disabled |
| Speaker Notes | enabled — explicit user instruction (dogfood brief: Speaker Notes=true) |
| Custom Animations | enabled — explicit user instruction (dogfood brief: Custom Animations=true, objects scope, adjacent-page Morph at least twice) |
| Narration Audio | disabled — explicit user instruction (dogfood brief: Narration Audio=false) |
| Created Date | 2026-10-24 |

Confirmation surface: the user explicitly delegated both confirmation gates to the agent. Stage 1 decided `free_design` (no template intent, no supplied workspace root). Stage 2 authored three directions — 0 "Drafting Sheet" (dark blueprint schematic, Bahnschrift + Segoe UI + Consolas, contrast pairing), 1 "Datasheet" (white-paper data-journalism grid, Arial throughout + Consolas, concord pairing, signal-red accent), 2 "Terminal" (near-black dark-tech, phosphor green, Consolas-led headings) — and selected 0 because the content is mostly architecture, page anatomy, and process diagrams that read most naturally as annotated engineering drawings. `design_spec_depth: brief`.

## II. Canvas Specification

| Property | Value |
| --- | --- |
| Format | PPT 16:9 |
| Dimensions | 1280 × 720 |
| viewBox | `0 0 1280 720` |
| Margins | 64 px left/right, 48 px top, 40 px bottom |
| Content Area | x 64–1216, y 48–680 |

## III. Visual Theme

### Theme Style

- **Mode**: custom
- **Mode References**: instructional, pyramid
- **Mode Behavior**: Open with the conclusion-level evidence (it is everywhere, here is why that is plausible), then teach the mechanism top-down through the layer stack in ordered, annotated steps where each page explains one layer or one mechanism; close with the trust factors and a decision checklist the engineer can apply. Titles state what the page teaches.
- **Visual style**: custom
- **Visual Style References**: blueprint
- **Visual Style Behavior**: Each page is a sheet from one engineering drawing set: deep navy paper with a faint 32 px grid, all structure drawn in thin single-weight pale-cyan line work (1.25–2 px, square or 2 px corners), components as outlined boxes with mono component codes, connectors with arrowheads and dimension lines, leader-line annotations instead of cards; one amber spot accent marks the current layer, key path, or hero number per page; a small drawing-sheet title block (sheet number, source page) anchors the lower-right corner of every content page. Depth comes from isometric layering and line weight, never shadows.
- **Theme**: SQLite as an engineered object laid open on the drafting table — one file, one library, one stack of layers
- **Tone**: precise, calm, quietly confident; technical without hype

### Color Scheme

| Role | HEX | Purpose |
| --- | --- | --- |
| Background | #0B1F3A | Blueprint paper field on every page |
| Secondary background | #11294B | Panel lift, title block, table header fills |
| Primary | #8CC4EE | Schematic line work, frames, connectors, icons |
| Accent | #FFB547 | Single spot highlight: current layer, key path, hero number |
| Secondary accent | #5ED3C4 | Second semantic lane (WAL / "works well" side) when a page contrasts two mechanisms |
| Body text | #EAF2FB | Titles and body copy |
| Secondary text | #9FB6CF | Captions, annotations, source lines |
| Divider | #2D4C74 | Rules, table borders, hairlines |
| Grid | #16305A | Faint background grid lattice |
| Negative | #FF7A6B | "Use client/server instead" / failure markers |

### AI Image Strategy

- **Image Rendering**: custom
- **Image Rendering References**: blueprint
- **Image Rendering Behavior**: Technical blueprint line drawing on deep navy paper: crisp uniform pale-cyan strokes, isometric axonometric projection, faint grid at very low opacity, a single amber highlight on the focal element. No shading, no texture, no glow halos, no painterly marks; reads like a draftsman's exploded-assembly sheet.
- **Visual**: an exploded isometric drawing of one database file opened into stacked fixed-size pages, with leader lines and blank callout tags
- **Mood**: precise and calm, like an exploded-view sheet in a machinist's manual

## IV. Typography System

### Font Plan

| Role | Character (Reference) | Primary | English if non-English | Fallback tail |
| --- | --- | --- | --- | --- |
| Title | DIN-like engineering sans, slightly condensed | Bahnschrift | — | sans-serif |
| Body | Neutral humanist sans | Segoe UI | — | sans-serif |
| Code | Monospace for component names, file names, API calls, coordinates | Consolas | — | monospace |

- **Title stack**: Bahnschrift, sans-serif
- **Body stack**: Segoe UI, sans-serif
- **Code stack**: Consolas, monospace
- **Display stack**: Bahnschrift, sans-serif
- **Hero stack**: Bahnschrift, sans-serif
- **Role rationale**: `code` carries every component code, source file name, and API symbol the blueprint style labels in mono; `display` keeps hero numerals in the title family.

### Font Size Hierarchy

| Purpose | Anchor Size (px) |
| --- | ---: |
| Body | 22 |
| Title | 40 |
| Subtitle | 28 |
| Lead | 26 |
| Annotation | 16 |
| Footnote | 13 |
| Code | 17 |
| Kicker | 15 |
| Cover Title | 76 |
| Hero | 112 |

## V. Layout Principles

### Deck-wide Direction

- **Hierarchy direction**: kicker (sheet code) → title → the drawing → annotations → source line; the eye lands on the amber element first
- **Composition tendency**: the schematic is the layout — one dominant drawing per page with copy hung on leader lines or set in a narrow side column; comparisons as two lanes of the same drawing
- **Cross-page continuity**: a recurring layer-stack rail (eight labelled bands from Interface to OS Interface) appears on the architecture pages and its amber marker moves as the explanation descends; the drawing-sheet title block recurs on every content page
- **Spacing posture**: variable by page rhythm — dense diagram pages, one breathing page (P10), open anchors
- **Spacing anchors**: page margin 64 px · block gap 24 px · column gutter 32 px · corner radius 2 px · body leading 1.4

## VI. Icon Usage Specification

- **Primary bundled library**: tabler-outline
- **Stroke Width**: 1.5
- **Brand-logo library**: simple-icons (real platforms and products named by sqlite.org/mostdeployed and the SQLite mark itself)

| Icon Path | Suitable Scenarios |
| --- | --- |
| icons/tabler-outline/database.svg | |
| icons/tabler-outline/file.svg | |
| icons/tabler-outline/server.svg | |
| icons/tabler-outline/device-mobile.svg | |
| icons/tabler-outline/device-desktop.svg | |
| icons/tabler-outline/device-tv.svg | |
| icons/tabler-outline/car.svg | |
| icons/tabler-outline/browser.svg | |
| icons/tabler-outline/code.svg | |
| icons/tabler-outline/binary.svg | |
| icons/tabler-outline/stack-2.svg | |
| icons/tabler-outline/lock.svg | |
| icons/tabler-outline/shield-check.svg | |
| icons/tabler-outline/bug.svg | |
| icons/tabler-outline/test-pipe.svg | |
| icons/tabler-outline/license.svg | |
| icons/tabler-outline/network.svg | |
| icons/tabler-outline/users.svg | |
| icons/tabler-outline/bolt.svg | |
| icons/tabler-outline/refresh.svg | |
| icons/tabler-outline/file-zip.svg | |
| icons/tabler-outline/circle-check.svg | |
| icons/tabler-outline/circle-x.svg | |
| icons/tabler-outline/alert-triangle.svg | |
| icons/tabler-outline/settings-off.svg | |
| icons/tabler-outline/certificate.svg | |
| icons/tabler-outline/cpu.svg | |
| icons/tabler-outline/world.svg | |
| icons/tabler-outline/terminal-2.svg | |
| icons/tabler-outline/feather.svg | |
| icons/simple-icons/sqlite.svg | |
| icons/simple-icons/android.svg | |
| icons/simple-icons/apple.svg | |
| icons/simple-icons/windows.svg | |
| icons/simple-icons/firefoxbrowser.svg | |
| icons/simple-icons/googlechrome.svg | |
| icons/simple-icons/safari.svg | |
| icons/simple-icons/skype.svg | |
| icons/simple-icons/itunes.svg | |
| icons/simple-icons/dropbox.svg | |
| icons/simple-icons/python.svg | |
| icons/simple-icons/php.svg | |
| icons/simple-icons/quickbooks.svg | |

## VII. Visualization Reference List

| Page | Family | Template | Usage |
| --- | --- | --- | --- |
| P09 | table | metric_table | Compare the four independent test harnesses by size, case count, and what each one guarantees |

## VIII. Image Resource List

| Filename | Dimensions | Ratio | Purpose | Type | Image pattern | Crop Policy | Acquire Via | Status | Reference | text_policy | page_role |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| cover_file_stack.png | 2752×1536 | 16:9 | Canonical generated drawing; feeds the two placed derivatives | Source | Not placed; source for cover and closing derivatives | adaptive | ai | Generated | Exploded isometric blueprint of a single database file: a thin file slab with about eight stacked equal-size page sheets lifted above it, top sheet amber, leader lines ending in empty callout tags, a dimension line along one edge; subject in the right two-thirds, left third quiet navy paper with faint grid | none | hero_page |
| cover_file_stack_fit.jpg | 1600×893 | 16:9 | Cover hook visual: one file that is a whole database | Illustration | Full-bleed drawing field; the exploded file sits in the right two-thirds while the left third stays quiet paper for the native title block; the empty callout tags may receive native mono labels | adaptive | ai | Generated | Derived from cover_file_stack.png; treatment=fit 1600x900; | none | hero_page |
| closing_file_stack_dim.jpg | 1600×893 | 16:9 | Closing field: the same drawing receded behind the final takeaway | Illustration | Full-bleed receded field under a dark scrim; the takeaway sits on top as native text | adaptive | ai | Generated | Derived from cover_file_stack.png; treatment=brightness 0.45, blur 3, fit 1600x900; | none | local |

## IX. Content Outline

### Part 1: Everywhere

#### Slide 01 - Cover

- **Audience move**: "SQLite is the toy DB in my test suite" → curious why sqlite.org claims more deployments than every other engine combined
- **Relationships**: contrast — SQLite vs fopen() vs Oracle (competes with the first, not the second)
- **Cover impact**: hook = sqlite.org's own line "Think of SQLite not as a replacement for Oracle but as a replacement for fopen()"; composition Reference — exploded single-file drawing on the right, title block on quiet left paper
- **Title**: SQLite: Why It's Everywhere
- **Core message**: SQLite competes with fopen(), not Oracle — and that is why it is everywhere
- **Content**: kicker "SHEET 00 · TECH TALK" · title · subtitle "Not a replacement for Oracle — a replacement for fopen()" · source line sqlite.org/about
- **Images**: cover_file_stack_fit.jpg as the drawing field
- **Motion suggestion**: title block then the drawing settle in; the file drawing is the opening state of the deck motif

#### Slide 02 - Most deployed

- **Audience move**: skeptical of "most deployed" → sees the concrete host list and the arithmetic behind "over one trillion databases"
- **Relationships**: membership — named hosts belong to the deployment set; order/link — 4.0e9 smartphones × hundreds of database files each → >1e12 databases in active use; contrast — SQLite vs zlib for "most deployed library"
- **Composition**: hero arithmetic chain as the dominant drawing; brand-mark host grid as the supporting evidence; zlib note as an annotation
- **Title**: Likely used more than all other database engines combined
- **Core message**: SQLite ships inside every phone, every major browser, and every Mac and Windows 10/11 install — over a trillion databases are in use
- **Content**: Found in every: Android device · iPhone/iOS device · Mac · Windows 10/11 install · Firefox, Chrome, Safari · Skype · iTunes · Dropbox client · TurboTax and QuickBooks; also PHP and Python; most TVs/set-top boxes and automotive multimedia systems · arithmetic: >4.0e9 smartphones × hundreds of SQLite files each → likely >1e12 databases in active use · annotation: probably the second most widely deployed library after zlib — and, being statically linked many times per device, "might" be the first · source sqlite.org/mostdeployed
- **Visualization**: arithmetic chain (number × number → number) as native type and geometry, unkeyed

#### Slide 03 - Serverless by design

- **Audience move**: pictures a database as a server process → sees SQLite as a library linked into the application that reads and writes an ordinary file
- **Relationships**: contrast — client/server engine (application → network → server process → its files) vs SQLite (application with the library inside → one ordinary disk file); membership — properties of the single file (tables, indices, triggers, views; cross-platform 32/64-bit and big/little-endian)
- **Composition**: two lanes of one drawing — left lane client/server, right lane in-process; spec callouts hung on the SQLite lane
- **Title**: No server: the library is the database engine
- **Core message**: SQLite has no separate server process; the whole SQL database lives in a single cross-platform disk file the application opens directly
- **Content**: client/server lane: app → network → server process → data files · SQLite lane: app + linked library → one disk file · callouts: zero-configuration, nothing to install or administer · one file holds tables, indices, triggers, views · file copies freely between 32/64-bit and big/little-endian machines · library can be under 900 KiB with all features · max database 281 TB · US Library of Congress recommended storage format · source sqlite.org/about, sqlite.org/whentouse

### Part 2: How it works

#### Slide 04 - The layer stack

- **Audience move**: treats SQLite as a black box → holds a map of eight layers in three groups they will descend through next
- **Relationships**: order — Interface → Tokenizer → Parser → Code Generator → Bytecode Engine (VDBE) → B-tree → Pager (page cache) → OS Interface (VFS); membership — SQL Compiler = tokenizer, parser, code generator; Core = interface, VDBE; Backend = B-tree, pager, OS interface; link — prepare_v2 compiles SQL into bytecode, step() runs it
- **Composition**: the deck's layer-stack rail drawn at full size: eight stacked bands with group brackets and mono source-file tags; one-sentence summary as the lead
- **Title**: SQLite compiles SQL into bytecode, then runs it on a virtual machine
- **Core message**: Every statement flows down one stack: compile (tokenizer → parser → code generator), execute (VDBE), store (B-tree → pager → VFS)
- **Content**: band labels with files: Interface main.c/legacy.c/vdbeapi.c · Tokenizer tokenize.c · Parser parse.y (Lemon) · Code Generator select.c, where*.c, expr.c… · Bytecode Engine vdbe.c · B-tree btree.c · Pager pager.c, wal.c, pcache*.c · OS Interface os_unix.c, os_win.c · groups: SQL Compiler / Core / Backend · source sqlite.org/arch
- **Motion suggestion**: Morph candidate into P05 — the layer-stack rail continues and the compiler bands expand; bands reveal top to bottom within this page

#### Slide 05 - Compile path

- **Audience move**: knows the layer names → understands how SQL text becomes a prepared statement and why the tokenizer drives the parser
- **Relationships**: order — SQL text → tokenizer → parser (Lemon, parse tree) → code generator / query planner → bytecode in sqlite3_stmt → sqlite3_step() on the VDBE; contrast — YACC/BISON (parser calls tokenizer) vs SQLite (tokenizer calls parser: thread-safe and faster)
- **Composition**: the layer-stack rail shrinks to a narrow left column with the compiler bands highlighted; the right field draws one statement's path through the three compiler stages to the VM
- **Title**: From SQL text to a bytecode program
- **Core message**: sqlite3_prepare_v2() is a compiler: tokens → parse tree → bytecode in a sqlite3_stmt, which sqlite3_step() runs until a row, completion, or error
- **Content**: example statement in mono (e.g. SELECT name FROM users WHERE id = ?) · tokenizer: hand-coded tokenize.c; the tokenizer calls the parser — threadsafe and faster than the YACC way · parser: generated by Lemon — reentrant, thread-safe, no leaks on syntax errors · code generator: where*.c + select.c are the query planner choosing among possibly millions of algorithms · sqlite3_stmt holds one bytecode program · sqlite3_step() runs it until done, a result row, a fatal error, or interruption · source sqlite.org/arch
- **Motion suggestion**: Morph from P04 (layer-stack rail → narrow rail, compiler bands highlighted); then the path steps reveal in order
- **Hyperlinks**: none

#### Slide 06 - Storage path and page anatomy

- **Audience move**: assumes a database file is opaque → can read the layout of one B-tree page and knows every read/write is in whole pages
- **Relationships**: order — B-tree requests fixed-size pages → pager caches them, provides rollback/atomic commit and locking → VFS performs OS file I/O; parent — table b-tree (64-bit rowid keys, data in leaves) and index b-tree (arbitrary keys, no data) are the two kinds; one b-tree per table and per index, all in the same file; parent — interior page holds K keys and K+1 child pointers; order — page regions: 100-byte file header (page 1 only) → 8/12-byte page header → cell pointer array → unallocated space → cell content area → reserved region
- **Composition**: narrow layer rail on the left now highlights the backend bands; the dominant drawing is one page drawn as a horizontal strip with dimensioned regions; a small table-vs-index b-tree note beside it
- **Title**: Down the stack: one file, many B-trees, fixed-size pages
- **Core message**: The B-tree layer asks the pager for fixed-size pages; each page has a precise byte layout, and all b-trees for all tables and indices live in one file
- **Content**: page size default 4096 bytes; any power of two 512–65536 · page regions with sizes: 100-byte database header (page 1 only) · page header 8 bytes (leaf) / 12 bytes (interior) · cell pointer array · unallocated space · cell content area · reserved region (usually 0) · table b-tree: 64-bit signed rowid key, data only in leaves · index b-tree: arbitrary key, no data · interior page: K keys, K+1 child pointers · sqlite_schema is always rooted at page 1 · max ≈ 4.29e9 pages × 65536 B ≈ 281 TB · file starts with the magic string "SQLite format 3" · source sqlite.org/arch, sqlite.org/fileformat2
- **Motion suggestion**: Morph from P05 (rail marker moves from compiler bands to backend bands); page regions reveal left to right

#### Slide 07 - Rollback journal vs WAL

- **Audience move**: knows "SQLite has journaling" vaguely → can state exactly what each mode writes where and when COMMIT happens
- **Relationships**: contrast — rollback journal (copy original pages to the journal, write changes into the database file, COMMIT = journal deleted, crash = play journal back) vs WAL (database file untouched, changes appended to the -wal file, COMMIT = a commit record appended, readers keep reading the original); order within each lane — write steps then commit point
- **Composition**: two parallel lanes of the same drawing (journal lane in primary, WAL lane in secondary accent) with the commit point marked by the amber accent in each
- **Title**: Two ways to commit atomically: rollback journal vs write-ahead log
- **Core message**: The rollback journal saves the old pages and overwrites the database; WAL leaves the database alone and appends the new pages — so readers and the writer stop blocking each other
- **Content**: rollback journal (default): copy original content → journal file · write changes directly into the database · COMMIT when the journal is deleted · crash/ROLLBACK replays the journal · WAL (since 3.7.0, 2010-07-21): original content stays in the database · changes appended to the WAL file · COMMIT = commit record appended to the WAL · readers continue on the unaltered database while commits proceed · source sqlite.org/wal

#### Slide 08 - WAL concurrency and checkpoints

- **Audience move**: knows WAL appends → understands end marks, the wal-index, checkpoints, and the costs of WAL
- **Relationships**: order — writer appends frames → each reader fixes an end mark at its start → reader takes the latest copy of a page before its end mark, else reads the database → checkpoint copies WAL content back to the database, stopping at the oldest active reader's end mark → WAL rewinds when fully checkpointed; contrast — advantages vs disadvantages
- **Composition**: the WAL lane from P07 extends into a timeline strip of WAL frames with reader end-mark ticks and a checkpoint sweep; pros/cons as a two-column annotation underneath
- **Title**: WAL: readers don't block the writer; checkpoints move pages home
- **Core message**: Each reader pins an end mark in the WAL, the single writer keeps appending, and a checkpoint copies pages back — automatically once the WAL reaches 1000 pages
- **Content**: end mark per read transaction = one consistent snapshot · wal-index in shared memory locates pages fast — so all processes must be on the same host (no network filesystem) · one writer at a time (one WAL file) · auto-checkpoint at 1000 pages by default · a long-running reader can stall the checkpointer · pros: significantly faster in most scenarios · more concurrency · more sequential I/O · far fewer fsync() calls · cons: same host only · extra -wal and -shm files · very slightly slower (1–2%) for read-mostly workloads · source sqlite.org/wal
- **Motion suggestion**: Morph from P07 — the WAL lane continues and stretches into the frame timeline; then end marks and the checkpoint sweep reveal in order

### Part 3: Why you can trust it

#### Slide 09 - Testing culture

- **Audience move**: assumes a small embedded library is lightly tested → sees test code at 590× the library and four independent harnesses with 100% MC/DC
- **Relationships**: contrast — 155.8 KSLOC library vs 92,053.1 KSLOC of test code and scripts (590×); membership — four independent harnesses (TCL, TH3, SQL Logic Test, dbsqlfuzz); link — TH3 provides 100% branch and 100% MC/DC coverage of the core
- **Composition**: hero ratio "590×" with a unit-scale visual (one library block vs its test mass) on the left; harness table on the right
- **Title**: The test code is 590 times larger than the library
- **Core message**: As of 3.42.0 the library is about 155.8 KSLOC of C and the project carries 92,053.1 KSLOC of test code — with 100% branch and 100% MC/DC coverage
- **Content**: hero 590× · 155.8 KSLOC library vs 92,053.1 KSLOC tests (version 3.42.0, 2023-05-16) · table rows: TCL tests — 51,445 distinct cases, millions of runs, public domain · TH3 — 1,055.4 KSLOC C, 50,362 cases, about 2.4 million instances, 100% branch + MC/DC, 248.5 million tests in a pre-release soak · SQL Logic Test — 7.2 million queries compared against PostgreSQL, MySQL, SQL Server, Oracle 10g · dbsqlfuzz — about one billion mutations per day, mutates SQL and database file together · also: out-of-memory, I/O error, crash and power-loss tests · source sqlite.org/testing
- **Visualization**: harness-table (table/metric_table) · 590× unit-scale visual (unkeyed microvisual)
- **Native-ready**: harness-table=yes

#### Slide 10 - Public domain

- **Audience move**: worries about licensing a dependency → knows there is no license at all, and why contributions are restricted to keep it that way
- **Relationships**: link — every author signed a public-domain affidavit → anyone may copy, modify, sell, or distribute for any purpose → project is open-source but not open-contribution; link — jurisdictions that do not recognize public domain → Hwaci sells a Warranty of Title
- **Composition**: breathing page — one large statement with a short three-step chain beneath; generous paper
- **Title**: No license to comply with: SQLite is in the public domain
- **Core message**: All code and documentation are dedicated to the public domain by signed affidavits; anyone may use SQLite for any purpose, commercial or private
- **Content**: statement "Anyone is free to copy, modify, publish, use, compile, sell, or distribute the original SQLite code… for any purpose" · chain: authors sign public-domain affidavits (kept in a firesafe at Hwaci) → every line written from scratch, traceable → open-source, not open-contribution · footnote: where public domain is not recognized, a Warranty of Title can be purchased · source sqlite.org/copyright

### Part 4: Choosing it

#### Slide 11 - When to use it

- **Audience move**: knows how SQLite works → can apply the official four-question checklist to their own system
- **Relationships**: order — checklist questions asked in sequence (data separated by a network? → many concurrent writers? → big data? → otherwise SQLite); contrast — works well (embedded/IoT, application file format, low-to-medium websites under ~100K hits/day, data analysis, enterprise cache, server-side per-user databases, data transfer, archives, temporary databases) vs client/server better (many clients over a network, high-volume write-heavy sites, datasets toward 281 TB, many simultaneous writers)
- **Composition**: decision flow drawn as a vertical chain of three gates exiting right to "client/server" and ending at "choose SQLite"; works-well list as a compact side column
- **Title**: The checklist: three questions before you pick SQLite
- **Core message**: Choose client/server when the data is across a network, when many writers must write at the same instant, or when the data outgrows one file — otherwise choose SQLite
- **Content**: Q1 data separated from the application by a network? → client/server · Q2 many concurrent writers that cannot take turns? → client/server (SQLite: unlimited readers, one writer at a time) · Q3 big data, more than fits one file? → client/server (limit 281 TB) · otherwise → choose SQLite · works well: embedded & IoT · application file format · websites under ~100K hits/day (conservative) · data analysis · cache for enterprise data · server-side database · data transfer format · archives · internal/temporary databases · source sqlite.org/whentouse

#### Slide 12 - Closing

- **Audience move**: has the pieces → leaves with one sentence and a reason to reach for SQLite where they would have reached for fopen()
- **Relationships**: link — three reasons (architecture: in-process single file, zero-config; trust: 590× test code, 100% MC/DC; freedom: public domain) → one conclusion (it competes with fopen())
- **Closing impact**: binding takeaway "Reach for SQLite wherever you would have reached for fopen()"; composition Reference — the receded file drawing as field with three short reason tags converging on the takeaway
- **Title**: SQLite competes with fopen()
- **Core message**: Small, fast, reliable — and free: use SQLite as your application's file format wherever local data lives
- **Content**: takeaway line · three reason tags: in-process single file, zero-configuration · 590× test code, 100% MC/DC · public domain · motto "Small. Fast. Reliable. Choose any three." · source sqlite.org
- **Images**: closing_file_stack_dim.jpg as receded field

## X. Speaker Notes Requirements

- **Generation**: enabled
- **Filename**: match each SVG filename under `notes/`
- **Content**: explain each drawing in the order it reveals; every number comes from the cited sqlite.org page; mention the source page aloud where a number is surprising
- **Total duration**: about 20 minutes
- **Notes style**: conversational, patient engineering explainer
- **Presentation purpose**: explain why SQLite is the most deployed database, teach its architecture and journaling trade-offs, and equip engineers to decide when to use it
