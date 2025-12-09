# Runtime API

This section will only acknowledge runtimes included in the
[Engine Runtimes Table](https://skelform.org#runtimes). Others may be used, but
could have a different API that is not supported.

For _developing_ runtimes, please see the
[Developer Documentation](https://skelform.org/dev-docs).

## Functions

- [`Load()`](#load)
- [`FormatFrame()`](#format-frame)
- [`timeFrame()`](#time-frame)
- [`animate()`](#animate)
- [`draw()`](#draw)

## `Load()`

```c
(root, texture) = Load("skellington.skf")
```

Loads the SkelForm file that is provided.

Returns the root (containing the armature, among other data) and texture.

## `FormatFrame()`

```c
frame: int = FormatFrame(20, armature.animations[0], false, true)
```

A helper function to format the provided number into a usable frame for the
animation, with options like reversing or looping.

If first animation has 14 frames, `frame` will be 6 (since loop is true).

`frame` will be used later for [`animate()`](#function-animate).

## `TimeFrame()`

```c
frame: int = TimeFrame(time.duration(), armature.animations[0], false, true)
```

A helper function to format the provided time into a usable frame for the
animation, with the same options as [`formatFrame()`](#function-format-frame):

Assuming:

- `time.Duration()` is 0.5s
- Animation is 60 FPS
- Animation is 60 frames long

`frame` will be 30.

## `Animate()`

```c
animOptions = {
  blendFrames: [20]
}

drawnBones = Animate(armature, [armature.animations[0]], [frame], animOptions)
```

Takes the armature, as well as the animation(s) and frame(s). The bones in the
armature are then processed accordingly.

Returns a new set of bones to be later drawn via [`draw()`](#function-draw).

Additional options may be given such as speed, transform modifiers, and blending
(per animation).

Blending will 'blend' animations transforms. This is great for eg; smooth
animation transitions.

## `Draw()`

```c
Draw(drawnBones, armature.styles, texture)
```

Draw the provided bones on-screen.

The bones provided must be from [`animate()`](#function-animate). It cannot be
the armature's bones directly.

The `???` parameter is engine-dependent, but usually just requires passing the
renderer.
