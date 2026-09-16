# Omni Flash Production Prompt Contract

Use this contract only after explicit approval of the current Phase A.

## Production package order

Deliver these sections in order:

1. Global continuity block
2. Standalone English prompts: three for a 30-second video, or six for a 60-second video
3. Stitching guide
4. Voice and music continuity note

## Global continuity block

State the current aspect ratio, theme polarity, line-art character design, three-color palette in ordinary descriptive language, narrator identity, audio arc, and continuity strategy. Treat this block as a review summary; each prompt still repeats all critical locks.

## Standalone prompt order

Write every prompt in this order:

1. Output specification: approximately ten seconds, chosen aspect ratio, 720p target, 24 FPS, synchronized audio
2. Background and base line-art polarity; for light mode, use a flat, uniform, digitally pure-white canvas with no shading or three-dimensional surface treatment
3. Character lock: hollow circular head, no face, no clothing, no filled body, stable proportions, uniform medium line weight
4. Three-color palette, expressed only with ordinary color names, and semantic roles
5. Composition strategy for the chosen ratio
6. First-frame state inherited from the previous clip
7. `[0–3s]`, `[3–7s]`, and `[7–10s]` visual beats
8. Exact audio-only English dialogue in quotation marks
9. Identical narrator description, emotion, and delivery
10. BGM, synchronized SFX, and voice-first mixing
11. Final-frame transition state inherited by the next clip
12. Negative constraints, including no visible writing or technical color notation

Make each prompt understandable without the global block or any other prompt.

## Style language

Use this wording to request density without character drift:

> rapid scene changes, kinetic motion-graphic transformations, and frequent visual events, while preserving an identical stick-figure design, constant line weight, and strict temporal consistency

Avoid `rapid style changes`, which can invite model changes to drawing style, line weight, or character design.

## Timed visual sequence

Translate the approved storyboard row into three connected events. State where the character begins, what changes, how the camera moves, which accent color carries meaning, and what fills or exits the final frame.

Use at least four content-relevant visual devices per prompt. Do not introduce new narrative claims during prompt expansion.

## Dialogue and visual text

Quote the approved English VO exactly once as audio-only dialogue. Instruct the model not to add, omit, paraphrase, repeat, reorder, caption, or visually transcribe words.

**For `subtitle_placement: none` or `post-production`:** Default every generated clip to no visible words, letters, numbers, captions, interface copy, palette labels, production annotations, logos, or watermarks. Require icon-only message bubbles, content cards, clocks, meters, and notifications. Put optional approved phrases in a separate post-production overlay list outside the prompts.

**For `subtitle_placement: embedded`:** Include approved subtitle text, timing, placement, styling, and contrast specifications in the model prompt. See **Embedded subtitle specifications** section below. Forbid all text *except* the approved subtitles and essential UI elements (icon-only cards if necessary).

## Embedded subtitle specifications

**When `subtitle_placement: embedded`, include in every model prompt:**

1. **Subtitle list:** Each subtitle, exact wording, and time window (e.g., "Subtitle 1 (0:00–0:04): 'Fall toward a black hole, and gravity stops playing fair.'")
2. **Placement:** "Position subtitles bottom-center, within safe margin (10% from frame edges). Render all subtitles in this clip with identical placement."
3. **Text rendering:** "Use clean, simple sans-serif font, [size] pixels equivalent at 720p. Render text in [color] for high contrast against the background."
4. **Contrast:** "Ensure text remains legible at all times; if scene background changes, adjust text rendering or add subtle background fade/box behind text."
5. **Timing:** "Each subtitle appears 0.2s before voiceover begins and disappears 0.2s after VO ends for the text."
6. **Consistency:** "All subtitles in this clip use identical font, size, color, placement, and timing style."

**Example snippet to include in a prompt:**
> "Render the following subtitles in the bottom-center area of the frame:
> - Subtitle 1 (0:00–0:04): 'Fall toward a black hole, and gravity stops playing fair.' (position: bottom-center, color: black, font: clean sans-serif, 18px equivalent)
> - Subtitle 2 (0:04–0:10): 'Spacetime itself bends toward it — and pulls everything, even light, along with it.' (same styling)"

Do not use hexadecimal, RGB, HSL, Pantone, or other technical color notation for subtitle text — use ordinary descriptive color names only.

## Palette notation

Use ordinary descriptive color names such as vivid red, electric blue, or warm gold. Never put hexadecimal, RGB, HSL, Pantone, or other technical color notation in a generation prompt. Models may reproduce prominent notation literally as unwanted interface text.

For light mode, describe the background as a completely flat, uniform, digitally pure-white canvas. Explicitly forbid gray or off-white tint, paper or canvas texture, grain, gradients, vignette, shadows, ambient occlusion, lighting falloff, bloom, fog, color grading, and three-dimensional background depth. Do not use a color code for white.

## Audio contract

Repeat the same narrator specification in every prompt. State delivery changes without changing voice identity. Keep narration dominant over BGM and effects.

Synchronize effects to visible events such as impacts, transformations, energy releases, steps, wipes, or object movement.

## Negative contract

**For `subtitle_placement: none` or `post-production`:**

Forbid:
- photorealism and unwanted 3D rendering
- facial features, hair, or clothing unless approved
- extra limbs, malformed anatomy, disconnected lines, or changed proportions
- broken or changing line weight
- inverted theme polarity or unexplained colors
- unintended characters or irrelevant spectacle
- visible words, letters, numbers, technical color notation, palette labels, interface copy, captions, subtitles, logos, or watermarks
- altered, omitted, repeated, reordered, or added dialogue

**For `subtitle_placement: embedded`:**

Forbid everything above *except* the approved subtitle text. Additionally forbid:
- any text or words *other than* the exact approved subtitles
- altered, omitted, repeated, reordered, or added subtitle text
- subtitle text in locations other than the specified placement
- subtitle styling (font, color, size, timing) that deviates from specifications
- any unintended captions, labels, or interface copy (subtitles only)

## Stitching guide

List all clips in order. For every cut, repeat the exact ending state and matching opening state. Include any trim, short audio crossfade, or match-cut note needed for assembly.

## Audio continuity note

Independent text-only generations may vary in voice and music. Recommend, in order:

1. Reuse the same voice or audio reference when the interface supports it.
2. Repeat the identical narrator description in every prompt.
3. For maximum consistency, generate synchronized SFX and add one continuous external English voiceover and BGM track during assembly.

## Phase B checks

- The user approved the current Phase A.
- Exactly three standalone prompts are present for a 30-second video, or six for a 60-second video, matching the confirmed duration.
- Each prompt repeats ratio, theme, character, palette, voice, audio, transition, and negative locks.
- Each prompt has all three timed beats and at least four relevant visual devices.
- Every ending matches the next opening.
- Dialogue exactly matches the approved narration.
- Dialogue is explicitly audio-only and is never displayed visually (unless `subtitle_placement: embedded`).
- Standalone prompts contain no hexadecimal, RGB, HSL, Pantone, or other technical color notation.
- If `subtitle_placement: none` or `post-production`: Generated scenes contain no visible writing; optional overlay phrases are listed separately for post-production.
- If `subtitle_placement: post-production`: A separate SRT file is provided with timed phrases (never embedded in generated clips).
- If `subtitle_placement: embedded`: Each prompt includes exact subtitle text, placement, styling, contrast, and timing specifications; no text appears outside these approved subtitles.
