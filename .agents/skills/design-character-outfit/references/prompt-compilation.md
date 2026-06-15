# Image Prompt Compilation

Treat the English image prompt as the executable visual specification. Treat the Chinese prompt as its faithful translation.

This reference only prepares and previews prompt text. Never call an image-generation tool or generate an image as part of this workflow. Stop after returning the English prompt and its Chinese translation unless the user separately and explicitly requests image generation.

## Natural Prompt Form

Use slots, categories, and checks only while designing. Do not expose that internal structure in the final prompt.

Write the final prompt as coherent natural visual prose:

- describe the image in a logical viewing order
- connect related garments and details into complete sentences
- place colors, fit, shape, finish, and location next to the objects they modify
- vary sentence length while keeping each sentence visually specific
- use paragraphs only when they separate meaningful visual groups

Prefer this order when it suits the image:

1. required fighter-scale heavyweight body, broad square face, heroic proportions, pose, and framing
2. face, hair, and expression
3. dominant clothing silhouette and inner layer
4. lower-body clothing, footwear, and selected equipment
5. focal details, character-focused lighting, pure white background, and rendering style

Do not output slot labels, colon-led modules, inventory lists, repetitive `wearing... wearing...` clauses, disconnected keyword piles, or JSON-like prompt structures.

During the current text-testing phase, describe the character against a seamless pure white background without environmental scenery or background objects. Character-focused lighting from invisible off-frame sources is allowed and encouraged when it improves finish quality. Integrate the lighting and pure white background naturally near the end of the main visual description.

Rewrite any slot-labeled inventory into connected visual sentences without introducing garments, colors, accessories, or equipment that were not selected during the design process.

## Preserve

- the complete fighter-scale heavyweight physique, slightly enlarged proportionally substantial head, broad square face, larger-than-realistic heroic proportions, muscle-dominant body composition, and readable six-block abdominal contour near the beginning
- visible anatomy, proportions, and body composition
- visible garments, fit, color, shape, condition, wearing method, and intentionally selected finish
- when applicable, slightly shortened full-length trouser hems, the narrow visible band of white socks, and unobscured low-cut or ankle-height footwear
- selected accessories, equipment, and their exact locations
- pose, expression, composition, viewing angle, lighting, and setting when relevant
- character-focused key light, fill light, rim light, cel-shaded form shadows, and controlled highlights from invisible off-frame sources
- smooth, polished, glossy, oily, or reflective finishes expressed only through clean two-dimensional highlight shapes and simplified reflections
- silhouette, focal point, color hierarchy, and image style
- the current testing-phase seamless pure white background instruction
- the exact fixed reference-image scope sentence at the very end

## Remove or Rewrite

- backstory and reasons for choosing an item
- professional research, player-association lists, candidate motifs, motif-selection rationale, and design-percentage explanations
- occupation names, job responsibilities, rank, wealth level, and social role when they are only labels
- habits, motives, goals, risks, and events that are not visibly occurring in the requested image
- invisible personality claims without a visible expression
- reasoning steps and design commentary
- evaluative design language such as "clear visual hierarchy", "the only accent color", "memorable", "luxurious", or "authoritative" unless rewritten as concrete visible instructions
- vague praise such as "handsome" or "well designed"
- repeated descriptions of the same feature
- conflicting garments, colors, locations, or poses
- exhaustive descriptions of low-priority objects
- negative statements about items that are simply absent
- surface texture patterns, fabric weave, leather grain, knit texture, pores, skin grain, stubble texture, scratches, distressed texture, granular detail, texture maps, PBR terminology, realistic material simulation, and photorealistic micro-detail
- any environment, scenery, location, architecture, furniture, floor treatment, horizon, atmospheric effect, background object, visible light fixture, background glow, background gradient, or environmental reflection during the current pure-white-background testing phase

Material knowledge may guide garment structure internally, but do not name or describe material texture in the final prompt unless the user explicitly requests it. Distinguish allowed finish from prohibited texture:

- Allowed: clean glossy highlight, polished reflective accent, smooth cel-shaded shine, simplified reflection shape.
- Prohibited: leather grain, visible fabric weave, realistic metal texture, pore detail, texture mapping, physically based material rendering.

Convert useful abstract information into visible facts before removing it:

- `authoritative` -> upright posture, squared shoulders, restrained expression
- `wealthy` -> precise tailoring, immaculate fabric, subtle high-quality hardware
- `security-conscious` -> alert gaze and unobstructed hands
- `the only accent color` -> name the selected accent color and its exact visible placement

## Mandatory Cleaning Passes

### Pass 1: Pixel Test

Inspect every phrase independently:

> Could a viewer point to the pixels created or changed by this phrase?

If no, delete it or convert it into a concrete visible feature. Do not copy sentences from character biography or design rationale into the prompt.

### Pass 2: Attention Test

Inspect the surviving prompt:

1. Is the same visual fact already stated elsewhere?
2. Does a minor detail receive more wording than the body, outfit, or focal point?
3. Does any phrase conflict with another instruction?
4. Can two phrases be compressed without losing visible information?
5. Would deleting the phrase leave the generated image materially unchanged?

Delete or compress anything that fails this pass. There is no fixed target length; retain useful specificity without diluting attention.

### Pass 3: Natural-Language Test

Read the prompt from beginning to end:

1. Does it describe one coherent image rather than recite an inventory?
2. Are related visual facts joined naturally?
3. Are transitions smooth without adding narrative filler?
4. Can any labeled module or fragment be rewritten as a concrete sentence?

Rewrite the prompt until it reads as natural visual direction while preserving precise image-relevant details.

### Pass 4: Body and White-Background Gate

Reject and rewrite the prompt unless all conditions pass:

1. The opening fully describes the enlarged heavyweight skeletal frame, moderately broad powerful waist, uniformly massive limbs, slightly enlarged proportionally substantial head with broad cranial volume, broad square face, oversized hands and feet, and larger-than-realistic heroic proportions created through mass and width rather than a shrunken head.
2. The body description cannot reasonably be interpreted as lean, narrow-waisted, conventionally athletic, realistically proportioned, obese, smooth-bellied, or body-fat-dominant.
3. The projecting abdomen is explicitly formed by six enormous raised abdominal blocks, and a tight inner layer preserves their readable contour through stretched fabric, shallow valleys, and controlled form shadows.
4. The prompt explicitly requests an isolated full-body character on a seamless pure white background.
5. The prompt contains no environment, scenery, location, horizon, floor line, architecture, furniture, atmospheric effects, background objects, visible light fixtures, background glow, background gradient, or environmental reflections.
6. The pure white background instruction appears immediately before the fixed final reference-image sentence.
7. Any lighting affects only the character through controlled highlights and form shadows; it does not create background content or a visible scene.
8. The head remains visually balanced with the body, and no collar, scarf, hood, lapel, or trapezius form encloses or shrinks its silhouette.

### Pass 5: Strict 2D Surface Gate

Reject and rewrite the prompt unless all conditions pass:

1. The image is explicitly a polished hand-drawn two-dimensional character illustration with refined cel-animation coloring and shading.
2. No phrase requests 3D rendering, texture maps, PBR materials, photorealism, realistic surface texture, or micro-detail.
3. Any smoothness, polish, gloss, oiliness, or reflection is represented through clean cel-shaded highlight shapes and simplified two-dimensional reflections.

## Hard Exclusions

Do not place these kinds of sentences in the final prompt:

```text
He works as...
He is responsible for...
He habitually...
The design communicates...
This serves as the only accent...
The visual hierarchy is clear...
The outfit feels authoritative but not threatening...
```

Express only their visible consequences when those consequences matter.

## Translation Rule

Translate the final English prompt into Chinese after the English cleaning pass. Preserve meaning, order, emphasis, and omissions. Do not improve, reinterpret, or add information in Chinese.

## Fixed Testing-Phase Ending

Every English prompt must end with the following exact sentence, even when no reference image is currently attached:

```text
Kyoto Animation-inspired refined 2D cel-animation coloring and shading, polished hand-drawn finish, and clearly readable muscular forms. Clean color shapes, controlled cel shadows, and selective two-dimensional highlights and reflections.
```

Every Chinese prompt must end with the following exact faithful translation:

```text
京都动画式精致二维赛璐璐动画上色与阴影、高完成度手绘质感以及清晰可读的肌肉体块。干净色块、受控赛璐璐阴影，以及选择性的二维高光与反射。
```

Place the seamless pure white background instruction immediately before this fixed final sentence. Do not omit, paraphrase, shorten, or place content after the fixed final sentence during the current testing phase.

Interpret `Kyoto Animation-inspired refined 2D cel-animation coloring and shading` only as linework, coloring, shading, controlled highlights, simplified reflections, and finish quality. It must never shrink the head, narrow the face, reduce body mass, create a lean waist, shrink the hands or feet, or restore realistic human proportions.
