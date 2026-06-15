---
name: design-character-outfit
description: Infer core visual elements and design coherent clothing, accessories, equipment, and text-only prompt previews for game or animation characters. Use when the user says "创建人物", asks to create or dress a character, requests a reusable outfit design element or motif, requests a character outfit derived from identity and scene, or wants an existing character design reviewed and compiled into English and Chinese prompt text without generating an image.
---

# Design Character Outfit

Create a character outfit by deriving visible design decisions from the character's identity, behavior, scene, and practical needs. Treat the result as a game or animation character design, then compile it into an efficient image-generation prompt.

## Text-Only Mode

- Operate entirely in text. Do not call image-generation tools, create images, or begin image generation.
- Treat the English and Chinese prompts as preview text for review and revision only.
- Output the prompts in the response, then stop.
- Generate an image only when the user makes a separate, explicit request to generate one. `【创建人物】`, creating an outfit, requesting prompts, or approving a text design does not count as permission to generate an image.

## Core Rules

- Infer clothing from the person and current situation. Do not map a profession directly to a stock uniform.
- Base every occupational character on a real, specific, explainable occupation, then derive a game-readable professional visual language instead of defaulting to literal modern workwear.
- Show concise, reviewable design rationale. Do not expose private chain-of-thought.
- Prefer professional, affluent, authoritative, specialist, creative, or socially distinctive occupations. Avoid labor-intensive occupations unless the user requests one.
- Always perform an active accessory, carried-object, and wearing-relationship derivation. Accessories are likely to appear, but never fill a slot or meet a count with an object that lacks a credible source, wearing relationship, or clear visual responsibility.
- Treat large, bright, highly decorative, precious-looking, or unusually conspicuous ornaments as low-probability candidates. Use them only when their structural, character, cultural, or compositional basis is strong enough for their visual weight.
- Preserve a clear visual hierarchy. Remove elements that compete with the focal point or duplicate another element's purpose.
- Distinguish broad visual sources from deployable core visual elements. Define a core element's recognizable form, transformations, and full-body deployment before building the outfit.
- Use one primary core element and at most one supporting element. Vary how the element enters clothing and accessories instead of copying the complete motif everywhere.
- Prefer element applications that combine decoration with practical construction or use. Do not create arbitrary element-shaped openings in single-layer garments.
- Use broad garment categories plus inferred attributes. Do not require an exhaustive clothing encyclopedia.
- Make the English image prompt authoritative. Make the Chinese prompt a faithful translation only; do not add details.
- Do not invent a personal name during outfit tests unless the user requests one or a name materially helps the task. Identify the character by role or a neutral label instead.

## Workflow

### 1. Establish the Character

Read `references/character-inference.md`.

If the user supplies only `【创建人物】`, invent a coherent character and scene. If the user supplies partial constraints, preserve them and infer only the missing information.

Default to an unnamed character during text-only outfit testing. If the user requests a name, derive it from the established cultural and linguistic context; avoid fashionable stock names, repeated naming patterns, and names reused from earlier characters or unrelated context.

Establish enough information to make clothing decisions:

- cultural background, age range, wealth, occupation, and social authority
- concrete responsibilities, behavior habits, aesthetic habits, and clothing taboos
- climate, current scene, immediate goal, expected movement, and likely risks

Use a real occupation with explainable responsibilities, work environment, common tools, and occupational clothing. Replace vague conceptual titles whose real work cannot be clearly explained.

Do not ask questions unless a missing answer would fundamentally change the requested design. Otherwise, make a clear assumption and state it briefly.

### 2. Set the Character-Design Direction

Before selecting garments, answer:

> If this were a game or animation character, what should the audience understand at first glance?

Define the first impression, silhouette, identity readability, focal point, color hierarchy, emphasized body areas, memorable distinction, and intended visual density.

### 3. Derive Clothing Requirements

Translate identity and situation into visible requirements:

- identity to communicate
- actions the outfit must permit
- environment and risks it must handle
- objects the character needs to carry
- personal objects suggested by identity, habits, relationships, history, or taste
- wearing, connecting, carrying, storage, adjustment, and temporary-holding relationships
- tradeoff among status, comfort, mobility, concealment, and protection

Keep this derivation concise. State design consequences rather than narrating every reasoning step.

### 4. Derive the Game-Readable Professional Visual Sources

Read `references/professional-visual-language.md`.

For every occupational character:

1. Identify the real specific occupation and its broader professional field.
2. Generate multiple player-recognizable visual sources associated with that field.
3. Compare them according to the character, culture, scene, and world.
4. Preserve the strongest sources for core-element derivation rather than treating a broad association as a finished element.
5. Identify a small number of real occupational tools, protective items, or identifiers that may clarify the specific occupation.

Do not use a fixed profession-to-outfit mapping or automatically select the first familiar association.

### 5. Derive the Core Visual Element System

Read `references/core-visual-elements.md`.

Derive one primary core visual element from the established character, professional visual sources, culture, behavior, history, scene, or other relevant sources. The source may be natural, cultural, occupational, geometric, behavioral, or narrative; it is not limited to plants or literal symbols.

Define the element's standard form, recognition anchors, allowed transformations, forbidden transformations, and suitable application methods. Add at most one supporting element when it improves specificity without competing with the primary element.

Then create a full-body deployment plan before selecting garments. Assign a primary expression, secondary expressions, restrained accents, optional implicit applications, quiet areas, and an upper-versus-lower-body visual balance. Do not use the complete element repeatedly on every garment.

### 6. Derive Accessories, Carried Objects, and Wearing Relationships

Read `references/outfit-slots.md`.

Every character must complete this derivation even when the final design is restrained. Generate at least:

- one personal-object candidate derived from identity, habit, taste, relationship, or experience
- one candidate with a wearing, connecting, carrying, storage, adjustment, temporary-holding, or use relationship
- one large-object candidate that may materially change the silhouette

Explore at least three different body regions or wearing relationships before selecting the final objects. Include possibilities beyond the waist, such as ear-area wearing, neck-and-chest suspension, cross-body structures, shoulder-and-back carrying, handheld or arm relationships, hip-and-leg relationships, and external silhouette-changing objects.

For each candidate, establish its source, single current state, reason for being worn or carried, visible attachment or carrying method, weight support, movement or access behavior when relevant, hand or body-location conflicts, and visual responsibility. Usually preserve two or three meaningful objects, adjusted for the intended design density, but treat this as a loose guideline rather than a minimum. Do not add an unsupported object merely to reach this default or to diversify body regions, and do not remove a meaningful object merely because it is not strictly necessary.

Treat gems, large metal ornaments, ornate brooches, luminous cores, and similarly high-visual-weight objects as low-probability candidates. They require a strong structural, cultural, identity, narrative, equipment, or compositional basis. Prefer ordinary, lived-in personal and carried objects for everyday characters.

### 7. Build the Outfit

Read `references/outfit-slots.md`.

Select only useful slots. For each selected item, specify concrete visible attributes such as garment type, silhouette, fit, length, color, closure, condition, wearing method, and location. Apply the established element deployment plan according to each location's structure and function. Use material knowledge internally to infer structure, but do not automatically turn it into surface texture detail.

Integrate selected accessories and carried objects as wearing relationships rather than isolated inventory. Keep the main chest-and-abdomen mass readable, but allow designed necklaces, cross-body straps, harnesses, suspended objects, cape fasteners, and chest connectors to cross part of the torso when they have an intentional attachment path and do not meaninglessly conceal the whole torso.

For the default target population, use a fighter-scale heavyweight male physique as a required invariant unless the user explicitly requests another body type:

- build the character on an extremely broad, enlarged skeletal frame rather than adding muscles to realistic human proportions
- use a thick short neck merging into massive trapezius muscles, a deep massively muscular torso, a moderately broad powerful waist, and enormous projecting pectorals
- make the shoulders, upper arms, forearms, thighs, calves, joints, hands, and feet uniformly massive and heavy
- keep muscle mass visually dominant, with only a shallow softening layer that reduces sharp definition without hiding the major muscle forms
- form the projecting abdomen from six enormous raised abdominal blocks; never render it as a smooth round belly
- use a slightly enlarged, proportionally substantial head with a broad cranial shape, full back-of-head volume, a broad square face, wide cheekbones, a heavy wide jaw, and a short wide chin
- use deliberately exaggerated heroic fighting-game proportions: roughly 7.25 to 7.75 heads tall, shoulders about 2.4 to 2.7 head-widths, enlarged hands and feet, and a towering larger-than-realistic presence created through body mass and width rather than a shrunken head
- favor tight T-shirts or tank tops as the inner layer; the stretched fabric must preserve the readable contours of the enormous pectorals and all six raised abdominal blocks through tension lines, shallow valleys, and controlled form shadows
- default the inner layer to white; across a large batch, target roughly 85% white and 15% other colors
- let clothing visibly respond to body volume without narrowing the waist, elongating the figure, or making every garment implausibly tight

Do not default to a lean, narrow-waisted, long-necked, small-headed, small-faced, realistically proportioned, conventional fitness-model, obese, smooth-bellied, or body-fat-dominant build. Treat these body, head, and face rules as mandatory defaults, not optional flavor, while preserving explicit user instructions.

### 8. Edit the Overall Design

Use `references/visual-design-checks.md`.

Review the outfit as a complete game or animation design. Resolve wearing conflicts, hand occupancy, unsupported loads, implausible access paths, and unexplained asymmetry; improve silhouette and readability; and remove unsupported or redundant objects. Do not remove a meaningful object merely because it is not strictly necessary. Back-mounted equipment and other silhouette-changing objects must be considered during derivation, then retained or rejected according to their source, attachment, movement compatibility, and silhouette value.

Revise the design before presenting it. Do not merely report problems.

### 9. Compile and Clean the Image Prompt

Read `references/prompt-compilation.md`.

Compile the English prompt from the finalized visible design, not by copying prose from `【人物基础】`, `【角色设计方向】`, `【服装需求推导】`, `【职业视觉推导】`, `【核心设计元素】`, or `【元素部署方案】`.

Treat outfit slots as internal planning structure only. Rewrite the final English prompt as coherent, natural visual prose rather than a slot list, labeled modules, keyword pile, or template-like concatenation.

Begin the English prompt with a complete natural-language description of the required fighter-scale heavyweight body, broad square face, and larger-than-realistic heroic proportions. Do not compress this to generic phrases such as `muscular man`, `large man`, or `athletic build`.

Run both mandatory cleaning passes from `references/prompt-compilation.md`:

1. Remove every phrase that does not directly describe pixels, composition, or two-dimensional illustration.
2. Compress repetition and remove low-priority details that dilute attention.
3. Read the complete prompt as natural visual language and smooth any mechanical transitions.

Do not include occupation labels, responsibilities, habits, motives, narrative explanations, design evaluation, or abstract social impressions unless they have been converted into a concrete visible feature.

Keep the final prompt strictly two-dimensional. Do not describe surface textures, texture maps, realistic micro-detail, or 3D rendering. Smooth, polished, glossy, or reflective finishes are allowed when expressed through clean cel-shaded highlights and simplified reflection shapes.

Do not impose a fixed word count. Keep all details that materially improve the image while preventing attention dilution.

This step produces text only. Do not submit the compiled prompt to an image-generation tool.

During the current text-testing phase, always specify a full-body character on a pure white background. Remove any conflicting scene description before output, but do not add a list of excluded background content.

Always append the fixed style sentence from `references/prompt-compilation.md` as the final sentence of the English prompt. Always append its faithful Chinese translation as the final sentence of the Chinese prompt. Do not omit or paraphrase these fixed endings.

### 10. Present the Result

Use this structure:

```text
【人物基础】
Concise identity, habits, scene, and current goal.

【角色设计方向】
First impression, silhouette, focal point, colors, and density.

【服装需求推导】
Concise requirements and their visible design consequences.

【职业视觉推导】
Real occupation, professional field, player associations, candidate visual sources, real occupational anchors, and game-character adaptation.

【核心设计元素】
Visual sources, candidate elements, primary element, standard form, recognition anchors, allowed and forbidden transformations, optional supporting element, and selection rationale.

【元素部署方案】
Primary expression, secondary expressions, accents, implicit applications, quiet areas, and upper-versus-lower-body visual balance.

【配饰、携带物与穿戴关系派生】
Explored regions and relationships, candidate sources, selected objects, current states, attachment and load-support methods, access paths, hand occupancy, silhouette effects, and important rejected candidates.

【最终服装设计】
Body, selected clothing slots, selected accessories/equipment, and signature detail.

【设计复核与删减】
Important corrections and intentionally omitted elements.

【English Image Prompt】
Clean image-generation prompt.

【中文提示词翻译】
Faithful Chinese translation of the English prompt.
```

Omit empty slot labels from `【最终服装设计】`. Keep the text preview useful for review. Stop after presenting the text.

## Reference Routing

- Read `references/character-inference.md` when creating or completing a character profile.
- Read `references/professional-visual-language.md` for every occupational character before selecting garments.
- Read `references/core-visual-elements.md` after establishing visual sources and before selecting garments.
- Read `references/outfit-slots.md` when selecting garments, accessories, equipment, or design density.
- Read `references/visual-design-checks.md` when reviewing a completed character design.
- Read `references/prompt-compilation.md` before producing final image prompts.
