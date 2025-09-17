# Basics

For the basics, we will go through a simple rigging process, as well as a little
tour around the editor.

## Table of Contents

- [Moving & Zooming the Camera](#moving--zooming-the-camera)
- [Your First Bone](#your-first-bone)
- [Parent & Child Bones](#parent--child-bones)
- [Parent-Child Bone Inheritance](#parent-child-bone-inheritance)
- [Pivots & Hinges](#pivots--hinges)

## Moving & Zooming the Camera

Move the camera by holding left click and dragging the mouse.

Zoom in/out with the scroll wheel or -/+ keys. On a touchpad, drag 2 fingers
up/down.

## Your First Bone

Click the <strong>New Bone</strong> button on the <strong>Armature</strong>
panel (left side) to create a bone.

The <strong>Bone</strong> panel (right side) will show the bone's fields such as
position, scale, etc., and can be edited.

Edit the bone by dragging the mouse while holding left-click. Change which field
is edited from the top left bar (<strong>Move</strong>, <strong>Scale</strong>,
<strong>Rotate</strong>).

Since dragging now edits the bone, the camera can still be moved by holding
Ctrl/Cmd while dragging.

## Parent & Child Bones

Bones can be connected to others to form joints and the like.

Create another bone, then drag either bone to the other.

Once released, the bone you held will be the child of the other.

![highlight_bone](highlight_bone.png)

## Parent-Child Bone Inheritance

Child bones inherit their parent's properties.

**Example**:

- Child position = (2, 2)
- Parent position = (3, 3)
- Final child position = child + parent = (5, 5)

For scale, the field is multiplied by the parent.

**Note**: The bone panel shows the bone's own field values. A child's position
in (0, 0) means it's in the center of the parent, _not_ necessarily the grid.

## Pivots & Hinges

Child bones will 'orbit' their parent when the parent is rotated.

This can be used to set parents as the 'pivot' to their children.

**Example**: A foot is the child of the knee. When the knee rotates, the foot
'orbits' and correctly stays in place.

## Conclusion

Play around with bones and textures, and try to create a rig.

Once you are ready, let's start [animating](./animating.md) it!
