You are writing a knowledge document about the topic below. A document made only
of text is not finished. Every concept that has a shape (a flow, a structure, a
comparison, a sequence, a hierarchy, a set of numbers) must also appear as a
picture, placed next to the text that explains it.

TOPIC AND AUDIENCE
<topic, for example "how the liquidity coverage ratio is calculated">
<who will read it and what they already know, for example "a new analyst with no banking background">
<the source material or standard to rely on, if any>

PRODUCE THE DOCUMENT AS BEFORE, THEN ADD THE PICTURES

1. Before writing, list every concept in the document. Next to each, choose the
   picture type from this table. If none fits, say why and skip it; do not force one.

   | If the concept is...                          | Draw a...                              |
   |-----------------------------------------------|----------------------------------------|
   | a process or steps in order                   | flowchart                              |
   | who sends what to whom, over time             | sequence diagram                       |
   | how parts connect or depend on each other     | dependency or system diagram           |
   | a hierarchy, categories or a taxonomy         | tree or nested boxes                   |
   | two or more options compared                  | comparison table or side-by-side panel |
   | a formula or calculation                      | worked-example diagram: inputs, operation, result, each with its number |
   | numbers over time or across categories        | bar or line chart, labelled, with units |
   | where something comes from and goes to        | source-to-destination (lineage) map    |
   | a timeline or calendar                        | timeline                               |
   | the whole topic                               | one overview picture at the start      |

2. Always include: one overview picture at the top that shows the whole topic on
   one page, and one worked example drawn as a picture, with real numbers.

3. Make every picture follow these rules:
   - One idea per picture. If it needs more than about 12 boxes, split it.
   - Every box, arrow and axis is labelled in plain words. Arrows say what moves.
   - Reading order is left to right, then top to bottom.
   - Use at most five colours, and use colour to mean something (for example one
     colour per stage), never as decoration. Never rely on colour alone: also use
     a label, shape or pattern.
   - A short caption under each picture states the one thing it shows.
   - Text in the picture matches the document's own terms exactly.
   - Add alt text (or a one-sentence description) for every picture.
   - Numbers in a picture must equal the numbers in the text. Recompute them.

4. Choose the format by what you are producing:
   - **HTML output:** draw each picture as inline SVG, so the page is
     self-contained (no external images). Use CSS variables for colours with a
     light and a dark theme, and make the SVG scale to the page width.
   - **Markdown output:** use Mermaid code blocks for flowcharts, sequence
     diagrams and trees; for anything Mermaid cannot draw, save an SVG file
     next to the document and embed it with a normal image link.
   - **Never** use a picture you cannot see the source of, and never describe a
     picture in words only ("a diagram showing...") without producing it.

5. Interactive extras, only if the output is HTML and they help understanding:
   hover to highlight what a box depends on, click to show its definition, a
   slider to change an input and watch the result move. Keep the static picture
   readable without them.

PLACEMENT
- Each picture goes immediately after the paragraph that introduces it, not in an
  appendix.
- End with a "Pictures in this document" list: number, title, what it shows, and
  the section it belongs to.

CHECK BEFORE YOU FINISH
- Every concept in your list from step 1 has a picture or a stated reason for none.
- Every picture renders (open it or validate the syntax) and nothing overlaps or
  is cut off.
- Every picture has a caption and alt text, and its numbers match the text.
- Someone who reads only the pictures and captions gets the main message.
- If anything was ambiguous, make a reasonable assumption and list it at the end
  rather than asking.
