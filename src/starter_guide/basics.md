# Basics

For the basics, we will go through a simple rigging process, as well as a little
tour around the editor.

## Table of Contents

- [Moving & Zooming the Camera](#moving--zooming-the-camera)
- [Your First Bone](#your-first-bone)
- [Parent & Child Bones](#parent--child-bones)
  - [Parent-Child Bone Inheritance](#parent-child-bone-inheritance)
  - [Pivots & Hinges](#pivots--hinges)

## The Camera (Moving & Zooming)

Move the camera by holding left click and dragging the mouse.

Zoom in/out with the scroll wheel or -/+ keys. On a touchpad, drag 2 fingers
up/down.

## Your First Bone

Click the <strong>New Bone</strong> button on the <strong>Armature</strong>
panel (left side) to create a bone.

The <strong>Bone</strong> panel (right side) will show the bone's fields such as
position, scale, etc., and can be edited.

The bone can be edited by dragging the mouse while holding left-click. The field
being edited is based on the top-left bar's selection (<strong>Move</strong>,
<strong>Scale</strong>, <strong>Rotate</strong>).

The camera can still be moved by holding Ctrl/CMD while dragging. This is only
required if a bone is selected.

## Parent & Child Bones

Bones can be connected to others to form joints and the like.

**Example:**

- shoulder -> forearm -> wrist
- neck -> head

Create another bone, then drag either bone to the other:

![highlight_bone](highlight_bone.png)

Once released, the bone you held will be the child of the other!

Changing the parent in any way will affect the child as well. This is easier to
see if the bones are textured.

### Parent-Child Bone Inheritance

Child bones always inherit their parent's properties.

**Example**:

- Child position = (2, 2)
- Parent position = (3, 3)
- Final child position = child + parent = (5, 5)

For scale, the field is multiplied by the parent.

**Note**: The bone panel shows the bone's own field values. A child's position
in (0, 0) means it's in the center of the parent, _not_ necessarily the grid.

### Pivots & Hinges

Child bones will 'orbit' their parent when the parent is rotated. This can be
used to set parents as the 'pivot' to their children.

**Example**: A foot is the child of the knee. When the knee rotates, the foot
'orbits' and correctly stays in place.

Often you may need to create an invisible bone to act as the pivot of another,
textured one.

## Conclusion

Play around with bones and textures, and try to create a rig.

Once you are ready, let's start [animating](./animating.md) it!
