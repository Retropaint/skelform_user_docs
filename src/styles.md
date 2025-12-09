# Styles

Styles are groups of textures, and can be used to create skins and/or outfits.

One or multiple styles may be assigned to bones, which will use the
corresponding texture based on index.

Styles can be accessed via the dropdown next to the `New Bone` button in the
**Armature** panel, or on a particular bone in the **Bone** panel (next to
`Styles:`). Clicking `[Setup]` will open the styles modal.

## Table of Contents

- [Styles Modal](#styles-modal)
  - [Styles Section](#styles-section)
  - [Textures Section](#textures-section)
  - [Bones Section](#assigned-bones-section)
  - [Assigned Textures Section](#assigned-textures-section)
- [Style Visibility](#styles-visibility)
- [Style Priority](#styles-priority)
- [Changing Per Bone](#changing-per-bone)

## Styles Modal

The Styles modal can be opened via the `[Setup]` option in styles dropdowns, and
comprises 3 sections:

![styles_modal](../assets/styles_modal_filled.png)

### Styles Section

Lists all available styles, as well as their visibility.

Click on `New` to create a new style and give it a name.

This section will display details of a hovered texture in the textures section.

### Textures Section

Bones with the same name as the texture will automatically use it, assuming
style priority.

Textures can be renamed by double clicking.

If a different style is hovered in the Style section, this list will instead
show all textures in it.

### Bones Section

Simply lists bones. Helps with the section to the right (assigned textures).

Dragging a texture on a bone will set it as the bone's texture.

### Assigned Textures Section

Lists the assigned textures of the corresponding bone to the left.

Clicking on them will open a dropdown to select a texture from the chosen style.

## Style Visibility

Styles can be made visible/hidden via the dropdown in the **Armature** panel, or
in the styles modal.

Bones will ignore hidden styles, and will be untextured if it's the only one
they have.

![hidden styles](../assets/hidden_styles.png)

## Style Priority

Bones will always use the texture of the same name in the first active style in
the list.

The order of styles can be changed by dragging them.
