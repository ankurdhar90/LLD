Create a blueprint-style data flow diagram as a single self-contained HTML page
(inline SVG, no external images) and publish it as an artifact.

VISUAL STYLE
- Blueprint look: royal-blue paper (#3350b5), faint minor grid every 20px and
  stronger major grid every 100px, off-white line art (#e4ecff), rounded outer
  frame with an inner border.
- IBM Plex Mono (Google Fonts), uppercase title with letter-spacing at the top.
- Engineering-drawing touches: dimension lines (with end ticks) above each zone
  carrying its label, and a title block in the bottom-right corner
  ("SHEET 1 / 1" plus a legend).

CONTENT
- Three zones left to right: SOURCE DB, STAGING, TARGET DB. Name each zone with
  its database and technology.
- Each table is a rounded box: header with the table name, then one row per
  column. Mark PK on primary keys and "FK → table" on foreign keys.
- Dashed yellow arrows show foreign-key dependencies between tables within the
  same zone, anchored at the FK column row.
- Solid numbered arrows show the pipeline steps between zones (extract,
  transform, load). A numbered circle sits on each arrow, and a step list at the
  bottom gives the note for each (incremental, full refresh, SCD2 merge, etc.).
- Compute load order from the FK graph with a topological sort. Show an
  L1/L2/L3 badge on every table (L1 = no dependencies, load first).
- Hovering a table dims everything except its upstream and downstream tables and
  edges.

IMPLEMENTATION
- Drive everything from one SPEC object at the top of the script: zones,
  tables (id, zone, cols with k:"pk"/"fk" and ref), and flows
  (from, to, step, note). Layout is computed from the spec, so I can edit the
  data without touching the drawing code.
- Make the SVG responsive (viewBox, width 100%).

MY DATA FLOW
<paste CREATE TABLE statements or a table list for source, staging, and target>

MAPPINGS
<for each target table: which source or staging tables feed it, and the
transform, e.g. "dim_customer ← stg_customers, SCD2 merge">

If anything is ambiguous (which table maps to which, where staging sits), make
a reasonable assumption and list it at the end rather than asking.
