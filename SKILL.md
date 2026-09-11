---
name: cinematic-anime-photo
description: Transform an attached or provided photo into a cinematic anime scene with luminous skies, atmospheric lighting, rich color, and detailed backgrounds while preserving the subject's identity and composition.
metadata:
  short-description: Turn photos into luminous cinematic anime scenes
---

# Cinematic Anime Photo

Transform a user's photo into an original cinematic anime rendering. Use high-level visual traits such as luminous skies, expressive clouds, saturated twilight color, detailed hand-painted backgrounds, atmospheric perspective, soft linework, and film-like light. Do not copy a living artist's exact signature style.

## Scope

This skill edits a supplied photo. It can handle portraits, groups, pets, places, products, and everyday scenes. Preserve the important subject and scene structure unless the user asks for a different composition.

## Workflow

1. Identify the image as an edit target. Use an attached image directly; for a local file, inspect it with `view_image` before editing.
2. Preserve identity, pose, body proportions, clothing silhouette, camera framing, composition, and important objects. Change the rendering style, lighting, and atmosphere only unless the user requests more.
3. Use the built-in `image_gen` tool by default. Use CLI/API mode only if the user explicitly asks for it.
4. Shape the prompt around this original cinematic anime direction:
   - luminous sky and expressive cloud forms
   - saturated blue, gold, and twilight color relationships
   - detailed environments with atmospheric depth
   - soft, clean linework with painterly light
   - subtle film-like contrast and glow
5. If the user asks for “Makoto Shinkai-like” or names another living artist, translate the request into the high-level traits above and omit the artist's name from the image prompt.
6. Inspect the result for identity, pose, composition, unwanted objects, text, watermarks, and obvious distortions. Make one targeted follow-up edit when needed.
7. Show the result inline. Keep the original photo unchanged and report the saved path when the output is project-bound.

## Prompt template

```text
Use case: style-transfer
Asset type: edited photo
Primary request: transform the supplied photo into an original cinematic anime scene
Input images: Image 1 — edit target
Subject: preserve the subject's identity, pose, expression, clothing silhouette, and important details
Scene/backdrop: preserve the original setting and composition unless the user requests a change
Style/medium: cinematic hand-painted anime rendering, soft linework, detailed background, atmospheric perspective
Lighting/mood: luminous sky, expressive clouds, gentle rim light, film-like glow, emotionally calm atmosphere
Color palette: rich blue and gold with saturated twilight accents that fit the source image
Constraints: change the rendering style only; keep identity, framing, pose, and key objects recognizable; no text or watermark
Avoid: photorealism, plastic 3D, distorted faces, extra fingers, duplicate subjects, random objects, logos, and copied artist signatures
```

## Accuracy and safety

- Separate what is visible in the source photo from what is inferred.
- Do not invent identifying details or claim that a face is unchanged if the result visibly changes it.
- Preserve the user's original file and create a new version for each edit.
- If the source is too blurry, cropped, or occluded for reliable preservation, say so and describe the limitation.
