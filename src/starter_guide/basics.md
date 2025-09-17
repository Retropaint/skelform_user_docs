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

To move the camera, drag the mouse around while holding left click.

To zoom in/out, edit the zoom value in the bottom right, or press the -/+ keys
on your keyboard (located to the right of the number keys).

The camera can also be controlled with touchpad gestures (double-swipe to move,
pinch to zoom).

## Your First Bone

Click the <strong>New Bone</strong> button on the <strong>Armature</strong>
panel (left side). This will create a new bone as well as automatically select
it.

The <strong>Bone</strong> panel (right side) will show the bone's fields and
properties such as position, scale, etc., and can be edited.

The bone can also be edited by dragging the mouse while holding left-click. This
will edit the corresponding field that is selected on the top left bar
(<strong>Move</strong>, <strong>Scale</strong>, <strong>Rotate</strong>).

Since left-click dragging now moves the bone, the camera can still be moved
around with the mouse by holding the Modifier key (<strong>CTRL</strong> on
Windows/Linux, <strong>CMD</strong> on Mac).

## Parent & Child Bones

Your only bone is acting on it's own, but it can also be connected to others to
form joints and the like.

Create another bone, then drag either bone to the other. Once released, the bone
you held will be a child of the other.

![highlight_bone](highlight_bone.png)

## Parent-Child Bone Inheritance

Child bones inherit all of their properties from their parent's. This means that
if a parent's position is (2, 2), for example, then the bone's position will be
it's own, plus (2, 2).

This also means the child bone's properties are relative to the parent. If a
child bone's position is set to (0, 0), for example, this will <em>not</em>
necessarily position it to the center of the grid. Instead, it will be exactly
where it's parent is.

## Pivots & Hinges

In addition to the above, child bones inherit a parent's rotation in a way that
it's 'orbiting'. This orbiting behaviour allows the parent to act as the pivot
point of it's child(ren).

It is good to note that bones <em>do not</em> need a texture and can be
invisible, so there is nothing wrong with having a parent bone that only serves
the purpose of being a pivot.

## Conclusion

By now you have hopefully gotten a good idea of how bones work. Play around wtih
them a little more and see what you can make!

Once you are ready, let's start [animating](./animating.md) it!
