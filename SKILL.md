---
name: cai-de-meihua
description: Conservatively beautify an attached dish or food photograph, restore a cropped plate with minimal outpainting, and produce a high-definition image while preserving everything else. Use for requests such as 菜的美化、美化菜品、补全盘子、盘子完整、高清菜品图, especially when the user says 其他不变. Do not use for removing clutter or text, changing the background, replacing props, rearranging food, or standardizing the camera angle unless the user explicitly requests those changes.
---

# 菜的美化

Use the image generation/editing tool for every edit. Treat the supplied photograph as the visual source of truth.

## Required result

- Improve the dish only with restrained, photorealistic adjustments: natural clarity, micro-detail, exposure, contrast, highlight recovery, and appetizing but source-faithful color and texture.
- Preserve the original food ingredients, portions, piece count where discernible, shapes, doneness, garnish, arrangement, and relative positions.
- Preserve the original camera angle, orientation, plate pose and decoration, crop character, background, table surface, lighting direction, shadows, reflections, and depth of field.
- If any part of the plate is cropped, outpaint only the smallest area needed to reveal the complete plate with a small natural margin. Reconstruct its curvature, rim thickness, material, decoration, highlights, and perspective from visible evidence.
- If the plate is already complete, do not change its geometry or expand the canvas unnecessarily.
- Produce a clean high-definition result without oversaturation, fake gloss, plastic texture, halos, excessive sharpening, blur patches, or HDR artifacts.

## Hard boundaries

Do not remove or alter visible text, logos, clutter, table seams, utensils, props, background objects, or surface imperfections unless the user explicitly requests that specific change. Do not convert to another camera angle. Do not rotate or tilt the plate. Do not add, remove, move, replace, restyle, or duplicate food. Do not invent garnish, tableware, a second plate, lettering, logos, or watermarks.

When a requested enhancement conflicts with preserving the source, choose preservation and make the enhancement more subtle. Do not claim pixel-exact preservation after generative editing.

## Workflow

1. Inspect the attached image before editing. Identify the food, full plate boundary, any cropped edges, background, lighting, angle, and details that must remain unchanged.
2. Use the attached image as the edit reference. If a provided local path is unavailable but the image is present in the conversation, use the smallest recent-image reference that includes it.
3. In the edit prompt, explicitly list the visible ingredients and the elements that must remain unchanged. Repeat that the original angle and background must be preserved.
4. Apply only the requested beautification and the minimum plate completion needed.
5. Inspect the result at normal and close view. Confirm that the full plate is coherent, food has not been added or duplicated, no text or objects were introduced, and the background and angle remain consistent. If a clear defect exists, run one narrow corrective edit limited to that defect.
6. Return the edited image and briefly state that the dish was enhanced, the plate was completed only if needed, and other elements were preserved as closely as generative editing allows.

## Prompt core

Adapt this intent to the specific image:

> Edit the supplied food photograph conservatively and photorealistically. Beautify only the dish with restrained natural clarity, exposure, contrast, highlight recovery, and source-faithful color and texture. Preserve the exact visible ingredients, portions, arrangement, garnish, plate identity and decoration, original camera angle, orientation, background, table surface, lighting direction, shadows, reflections, and depth of field. If the plate is cropped, outpaint only the smallest amount required to reveal the complete plate with a small natural margin; otherwise do not alter the canvas or plate geometry. Do not remove clutter or text, change the background, change the camera angle, add or remove food, rearrange the dish, add props, duplicate objects, or introduce text or logos. Output a clean high-definition photograph without oversaturation, fake gloss, plastic texture, halos, excessive sharpening, blur, or HDR artifacts.
