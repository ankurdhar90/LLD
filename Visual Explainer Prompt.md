You are writing a knowledge document about the topic below. A document made only
of text is not finished. Every idea that has a shape (a process, a structure, a
comparison, a cycle, a set of numbers, a place) must also appear as a picture,
placed next to the text that explains it. This applies to any subject: science,
law, software, medicine, history, finance, cooking, anything.

TOPIC AND AUDIENCE
Topic: <the subject, for example "how vaccines work", "the French Revolution",
        "how a mortgage is priced", "how DNS resolves a name", "making sourdough">
Reader: <who they are and what they already know, for example "a teenager with
         no biology background" or "a developer new to networking">
Source material: <documents, links or a standard to rely on, or "general knowledge">
Output format: <HTML page, Markdown file, or "your choice">

STEP 1: PLAN THE PICTURES BEFORE WRITING
List every concept the document will explain. Next to each, pick the picture type
that matches what the concept IS. If two fit, pick the one a beginner reads
fastest. If none fits, write why and skip it; never force a picture.

| The concept is...                                  | Draw a...                                        |
|----------------------------------------------------|--------------------------------------------------|
| the whole topic                                    | overview map: main parts and how they relate     |
| steps in order, with decisions                     | flowchart                                        |
| who or what interacts, in time order               | sequence diagram                                 |
| a repeating process                                | cycle diagram                                    |
| parts that depend on or feed each other            | dependency or flow map                           |
| a hierarchy, categories or kinds                   | tree or nested boxes                             |
| the parts of one object or system                  | labelled anatomy or exploded view                |
| layers, each built on the one below                | stack diagram                                    |
| two or more things compared                        | comparison table or side-by-side panel           |
| two measures that sort things into groups          | 2x2 matrix                                       |
| what overlaps and what does not                    | Venn or overlap diagram                          |
| a cause leading to effects                         | cause-and-effect chain                           |
| a state that changes when something happens        | state diagram                                    |
| a shrinking or filtering path                      | funnel                                           |
| a formula or calculation                           | worked example: inputs, operation, result, with real numbers |
| numbers over time or across categories             | chart (bar, line or pie) with axis labels and units |
| events across time                                 | timeline                                         |
| something in space                                 | map or floor plan                                |
| before and after, or old versus new                | before/after panel                               |
| something abstract                                 | an analogy picture (the idea drawn as something familiar), labelled with what each part stands for |

STEP 2: ALWAYS INCLUDE
- One overview picture at the top showing the whole topic on a single page.
- One worked example drawn as a picture with real numbers or a real case.

STEP 3: RULES FOR EVERY PICTURE
- One idea per picture. If it needs more than about 12 elements, split it.
- Label every box, arrow and axis in plain words. Arrows say what moves or what
  they mean.
- Read left to right, then top to bottom. Start and end are obvious.
- At most five colours, each with a meaning. Never rely on colour alone: also use
  a label, shape or pattern, so the picture works in greyscale.
- Give each picture a title, a one-line caption stating the single thing it shows,
  and alt text (a sentence describing it for someone who cannot see it).
- Use the same terms in the picture as in the text.
- Any number in a picture must match the text. Recompute it; do not copy from memory.
- Show only what the reader needs. Remove decoration.

STEP 4: FORMAT
- HTML output: draw every picture as inline SVG (no external images), with
  colours as CSS variables and a light and a dark theme, scaling to the page width.
- Markdown output: use Mermaid code blocks where they can draw it (flowchart,
  sequence, state, timeline, tree). For anything else, write an SVG file beside the
  document and embed it with an image link.
- Never describe a picture in words only ("a diagram showing...") without producing
  it. A picture you did not produce does not count.
- Optional, HTML only: hover to highlight what an item connects to, click for a
  definition, a slider to change an input and watch the result move. The static
  picture must still be readable without them.

STEP 5: PLACEMENT
- Put each picture straight after the paragraph that introduces it.
- Finish with a list "Pictures in this document": number, title, what it shows,
  and the section it belongs to.

CHECK BEFORE YOU FINISH
- Every concept in your Step 1 list has a picture or a stated reason for none.
- Every picture renders (open it or validate its syntax); nothing overlaps or is
  cut off; text is readable at phone width.
- Every picture has a title, caption and alt text, and its numbers match the text.
- A reader who looks only at the pictures and captions gets the main message.
- If anything was ambiguous, make a reasonable assumption and list it at the end
  rather than asking.
