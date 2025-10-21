# Styles

Styles are groups of textures, and can be used to create skins/outfits.

One or multiple styles may be assigned to bones, which will use the
corresponding texture based on index.

Styles can be accessed via the dropdown next to the `New Bone` button in the
**Armature** panel, or on a particular bone in the **Bone** panel (next to
`Styles:`). Clicking `[Setup]` will open the styles modal.

## Table of Contents

- [Styles Modal](#styles-modal)
  - [Styles Section](#styles-section)
  - [Textures Section](#textures-section)
  - [Assigned Bones Section](#assigned-bones-section)
- [Style Visibility](#styles-visibility)
- [Style Priority](#styles-priority)
- [Changing Per Bone](#changing-per-bone)

## Styles Modal

The Styles modal can be opened via the `[Setup]` option in styles dropdowns, and
comprises 3 sections:

### Styles Section

Lists all available styles, as well as their visibility.

Click on `New` to create a new style and give it a name.

This section will display details of a hovered texture in the textures section.

### Textures Section

Lists all textures of the selected Style.

All textures will have indices in front of their names, starting with `0)`.
Bones will use the corresponding texture based on index.

This section will display all textures of a hovered style in the styles section.

### Assigned Bones Section

Lists all bones and their assigned texture index (if said bone uses the selected
style).

Clicking on a bone will either add or remove it from the style. It's texture
index can be changed with either the dropdown to the right, or by dragging a
texture onto it.

## Style Visibility

Styles can be made visible/hidden via the dropdown in the **Armature** panel, or
in the styles modal.

Bones will ignore hidden styles, and will be untextured if it's the only one
they have.

## Style Priority

Bones with multiple selected styles will use the first visible one in the list.

## Changing Per Bone

The bone panel displays the selected bone's selected styles and texture index.
Clicking on a style in the styles dropdown will toggle it for this bone only.

While this doesn't allow for adding new styles/textures, it can be great for
quick edits over opening the styles modal.
