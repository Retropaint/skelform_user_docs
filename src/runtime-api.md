# Runtime API

This section will only acknowledge runtimes included in the
[Engine Runtimes Table](https://skelform.org#runtimes). Others may be used, but
could have a different API that is not supported.

For _developing_ runtimes, please see the
[Developer Documentation](https://skelform.org/dev-docs).

## Functions

- [Function `load()`](#function-load)
- [Function `formatFrame()`](#function-format-frame)
- [Function `timeFrame()`](#function-time-frame)
- [Function `animate()`](#function-animate)
- [Function `draw()`](#function-draw)

<h3 id="function-load"><a class="header" href="#function-load">Function <code>load(filePath)</code></a></h3>

```go
root, texture := skelform_ebiten.load("skellington.skf")
```

Loads the SkelForm file that is provided.

Returns the root (containing the armature, among other data) and texture.

<h3 id="function-format-frame"><a class="header" href="#function-format-frame">Function <code>formatFrame(int, animation, reverse, loop)</code></a></h3>

```go
frame := formatFrame(20, armature.Animations[0], false, true)
```

A helper function to format the provided number into a usable frame for the
animation, with options like reversing or looping.

If first animation has 14 frames, `frame` will be 6 (since loop is true).

`frame` will be used later for [`animate()`](#function-animate).

<h3 id="function-time-frame"><a class="header" href="#function-time-frame">Function <code>timeFrame(time, animation, reverse, loop)</code></a></h3>

```go
frame := timeFrame(time.Duration(), armature.Animations[0], false, true)
```

A helper function to format the provided time into a usable frame for the
animation, with the same options as [`formatFrame()`](#function-format-frame):

Assuming:

- `time.Duration()` is 0.5s
- Animation is 60 FPS
- Animation is 60 frames long

`frame` will be 30.

<h3 id="function-animate"><a class="header" href="#function-animate">Function <code>animate(armature, animations, frames, options)</code></a></h3>

```go
animOptions := {
  blendFrames: [20]
}

drawnBones := animate(armature, [armature.Animations[0]], [frame], animOptions)
```

Takes the armature, as well as the animation(s) and frame(s). The bones in the
armature are then processed accordingly.

Returns a new set of bones to be later drawn via [`draw()`](#function-draw).

Additional options may be given such as speed, transform modifiers, and blending
(per animation).

Blending will 'blend' animations transforms. This is great for eg; smooth
animation transitions.

<h3 id="function-draw"><a class="header" href="#function-draw">Function <code>draw(bonesToDraw, styles, texture, ???)</code></a></h3>

```go
draw(drawnBones, armature.Styles, texture)
```

Draw the provided bones on-screen.

The bones provided must be from [`animate()`](#function-animate). It cannot be
the armature's bones directly.

The `???` parameter is engine-dependent, but usually just requires passing the
renderer.
