# Using Runtimes

To use armatures and animations from SkelForm in your game, you need a
plugin/library to run them. Those are called **runtimes**!

This section will only acknowledge runtimes included in the
[Engine Runtimes Table](https://skelform.org#runtimes). Others may be used, but
could have a different API that is not supported.

For _developing_ runtimes, please see the
[Developer Documentation](https://skelform.org/dev-docs).

## Table of Contents

- [Installation](#installation)
- [The API](#the-api)

## Installation

In the terminal and in their respective environments:

- Macroquad - `cargo add rusty_skelform_macroquad`
- pygame - `pip install skelform_pygame`
- Ebiten - `go get skelform_ebiten`

Using the languages and/or game engines, outside of the runtimes, is out of
scope for this section.

## The API

- [Function `load()`](#function-load)
- [Function `formatFrame()`](#function-format-frame)
- [Function `timeFrame()`](#function-time-frame)
- [Function `animate()`](#function-animate)
- [Function `draw()`](#function-draw)

<h3 id="function-load"><a class="header" href="#function-load">Function <code>load(filePath)</code></a></h3>

```go
armature, texture := skelform_ebiten.load("skellington.skf")
```

This function will load the SkelForm file that is provided.

It will return back the armature and texture. Don't lose them!

<h3 id="function-format-frame"><a class="header" href="#function-format-frame">Function <code>formatFrame(int, animation, reverse, loop)</code></a></h3>

```go
frame := formatFrame(20, armature.Animations[0], false, true)
```

A helper function to format the provided number into a usable frame for the
animation, with options like reversing or looping.

If first animation has 14 frames, `frame` will be 6 (since loop is true)

`frame` will be used later for `animate()`.

<h3 id="function-time-frame"><a class="header" href="#function-time-frame">Function <code>timeFrame(time, animation, reverse, loop)</code></a></h3>

```go
frame := timeFrame(time.Duration(), armature.Animations[0], false, true)
```

A helper function to format the provided time into a usable frame for the
animation, with the same options as `formatFrame()`:

Assuming `time.Duration()` is 0.5s, the animation is 60 fps, and animation is 60
frames long, `frame` will be 30.

`frame` will be used later for `animate()`.

<h3 id="function-animate"><a class="header" href="#function-animate">Function <code>animate(armature, animations, frames, options)</code></a></h3>

```go
animOptions := {
  blendFrames: [20]
}

drawnBones := animate(armature, [armature.Animations[0]], [frame], animOptions)
```

Takes the armature, as well as the animation(s) and frame(s). The bones in the
armature are then processed accordingly, but it will also return a separate
group of bones to be drawn on-screen later.

It also includes additional options, such as speed, transform modifiers, and
blending.

Blending will 'blend' animations transforms. This is great for smooth animation
transitions.

<h3 id="function-draw"><a class="header" href="#function-draw">Function <code>draw(bonesToDraw, styles, texture, ???)</code></a></h3>

```go
draw(drawnBones, armature.Styles, texture)
```

This function will draw the provided bones on-screen.

The bones provided must be from `animate()`. It cannot be the armature's bones
directly.

The `???` parameter is dependent on the engine. It's engine-dependent, but
usually just requires passing the renderer.
