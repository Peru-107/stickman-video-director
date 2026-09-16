# Director's Proposal Contract

Use this contract for Phase A. Present a readable production proposal and stop for confirmation before writing model prompts.

## Rewrite the source

Create one natural English narration scaled to the confirmed duration: 65–75 words for approximately 27–33 seconds of speech in a 30-second video, or 130–150 words for approximately 55–65 seconds of speech in a 60-second video.

- Preserve the source's core claim, names, numbers, and factual meaning.
- Strengthen a weak opening with an immediate hook.
- Remove repetition and secondary branches from long sources.
- Expand short sources with a relevant example, progression, reframe, or callback.
- Prefer clear spoken English to literal translation.
- Simplify wording before increasing speaking speed.
- Do not invent research, statistics, quotations, product claims, or factual details.

Use the user's language for planning explanations. Keep the voiceover in English and give a reference translation in the user's language.

## Header contract

Present these items in order:

1. English title and reference-language title
2. Core message and opening hook
3. Chosen aspect ratio, light/dark theme, and duration (30 or 60 seconds)
4. Narrator identity, speaking pace, English word count, and estimated duration
5. Up to three saturated accent colors, named in ordinary language, and what each represents
6. BGM direction, emotional turn, tone, and narrative arc

Default the narrator only after required setup is complete: a bright, energetic adult female voice speaking natural American English. Infer tone and accent colors from the source when the user did not specify them.

## Narrative patterns

Choose the pattern that fits the source:

- Motivational: strong hook → recognition → escalation → reframe → action → payoff and CTA
- Educational: surprising hook → setup → mechanism → consequence → practical meaning → takeaway
- Commercial: pain point → consequence → product reveal → mechanism → proof or use case → benefit and CTA

## Storyboard contract

Produce exactly three approximately ten-second rows for a 30-second video, or six approximately ten-second rows for a 60-second video:

| Time | Narrative purpose | Stick-figure scene | Motion, camera, and transition | English VO | Reference translation | BGM / SFX | Text (if embedded subtitles) |
|---|---|---|---|---|---|---|---|

Give each row a different narrative job. Allocate approximately 21–25 English words per row while keeping sentence boundaries natural.

When `subtitle_placement: embedded`, populate the **Text** column with timed subtitle cues (breaking at spoken sentence boundaries, 5–10 words per line, two lines max per card) plus placement/styling notes (see **Embedded subtitle styling** section below). When `subtitle_placement: post-production` or `subtitle_placement: none`, leave this column empty or omit it.

## Visual-density recipe

Build every row from three sequential beats:

- `0–3s`: establish or inherit the visual premise.
- `3–7s`: transform, escalate, or explain the metaphor.
- `7–10s`: deliver a climax and create the next transition.

Use at least four relevant devices per row:

- expressive stick-figure action
- environmental transformation
- concrete visual metaphor
- diagram, arrow, or icon-only symbol
- particles, energy, fluid, explosion, or light
- camera push, pull, pan, orbit, shake, or tracking move
- foreground wipe or object crossing the lens
- match cut, shape morph, or motion-matched transition
- interaction with another figure or oversized object

Require a perceptible visual change every two to three seconds. Make every effect clarify or intensify the spoken idea; omit unrelated spectacle.

## Palette and text

Keep the background and stick figure monochrome according to the selected theme. Use no more than three saturated accent colors across the video. Assign semantic meaning such as anxiety, danger, energy, discovery, or success.

Name colors only with ordinary descriptive language. Do not use hexadecimal, RGB, HSL, Pantone, or other technical color notation anywhere in the proposal or production prompts.

**For `subtitle_placement: none` or `post-production`:** Default the generated video to no visible words, letters, numbers, captions, interface copy, or technical annotations. Make message bubbles, content cards, meters, clocks, and notifications icon-only. After the storyboard, optionally list concise two-to-five-word English overlays for post-production, including their target clips and safe placement; never carry those overlays into the video-generation prompts.

**For `subtitle_placement: embedded`:** Include subtitle text, timing, placement, and styling specifications in the storyboard's Text column and in all model prompts. See **Embedded subtitle styling** section below.

## Composition by aspect ratio

- `16:9`: use left-center-right staging, lateral tracking, horizontal match cuts, and deliberate negative space. Reserve clean space for optional post-production overlays when useful.
- `9:16`: use foreground/background depth, vertical reveals, stacked motion, foreground passes, and interface-safe overlay space.
- `1:1`: keep action compact and center-weighted. Use short travel paths and avoid crucial events at extreme edges.

Changing ratio requires new staging, camera paths, transition geometry, and overlay-safe negative space. Changing theme requires inverted base colors and a fresh contrast check.

## Continuity

End each row with a visible interface that the next row inherits: a pose, moving object, filled frame, travel direction, shape, or camera motion. Name both sides of every connection in the proposal.

## Embedded subtitle styling

When `subtitle_placement: embedded`, use these guidelines:

**Placement:** Bottom-center (default for 9:16 / 1:1 vertical ratio) or bottom-third (default for 16:9). Reserve safe margin from frame edge (at least 10% of frame width/height). Never place text over critical action or the main character's center of mass unless unavoidable.

**Readability:** Use high contrast between subtitle color and background. For light-theme videos, use dark text (black or dark gray). For dark-theme videos, use light text (white or off-white). Never use the same color as an accent in the scene.

**Styling:** Simple, clean sans-serif font. Consistent size throughout (recommend 16–24px equivalent for 720p). No decorative fonts, shadows, glows, or outlines unless required for contrast. Text should feel like a natural part of the frame, not an overlay.

**Timing:** Each card appears 0.2s before VO begins and disappears 0.2s after VO ends, creating a slight overlap for legibility (users read ahead slightly).

**Content:** Break at natural pauses: sentence boundaries, clause breaks, or dialogue speaker changes. Aim for 5–10 words per line, two lines max per card, to avoid cluttering the frame.

Include these specifications in the Text column of the storyboard alongside the subtitle text itself.

## SRT generation (post-production mode)

When `subtitle_placement: post-production`, after Phase A approval, generate an SRT file from the Text column:

- Each subtitle index is a sequential number starting at 1.
- Each timecode spans from the start of the VO phrase to its end, in the format `HH:MM:SS,mmm --> HH:MM:SS,mmm`.
- Subtitle text is 1–2 lines, breaking at logical word boundaries (5–10 words per line).
- No formatting codes; plain text only.

Provide the full SRT file as a separate code block after Phase B, or offer it as downloadable text alongside the Omni Flash prompts.

## Confirmation ending

End Phase A by asking the user to:

- approve the current proposal and generate the matching Omni Flash prompts (three for 30 seconds, six for 60 seconds) plus SRT file if `subtitle_placement: post-production`;
- revise a named scene, narration passage, or subtitle placement/timing; or
- change a global setting such as aspect ratio, theme, duration, subtitle placement, palette, voice, or tone.

Do not include final model prompts or SRT file. A global change invalidates approval and requires a revised Phase A.

## Phase A checks

- Source, aspect ratio, theme, duration, and subtitle placement choice are known.
- English narration matches the chosen duration: 65–75 words and approximately 27–33 seconds for 30 seconds, or 130–150 words and approximately 55–65 seconds for 60 seconds.
- Exactly three (30-second) or six (60-second) storyboard rows have distinct narrative purposes.
- Every row has three beats, at least four visual devices, audio, and a transition.
- Visual change occurs approximately every two to three seconds.
- No more than three saturated accent colors are used (not counting subtitle text color).
- No technical color notation is present.
- If `subtitle_placement: embedded`, Text column specifies timed phrase breaks, placement (bottom-center / bottom-third), text color/contrast, and font guidance; subtitle text breaks at natural boundaries (5–10 words per line, two lines max).
- If `subtitle_placement: post-production`, Text column contains timed phrase breaks for SRT generation.
- If `subtitle_placement: none`, no text is specified anywhere.
- Every adjacent pair has a named continuity connection.
- The ending returns to the central message.
- No unsupported factual detail was added.
