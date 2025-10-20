<style>
  .ik-code {
    margin: 0
  }
</style>

# PSD Rigging

SkelForm supports importing Photoshop Document (PSD) files to turn into an
armature. To do this, a specific structure is needed.

## Table of Contents

- [Sample File](#sample-file)
- [Main Structure](#main-structure)
- [Pivots](#pivots)

## Sample File

A sample PSD file may be
[downloaded](https://github.com/Retropaint/SkelForm/blob/master/skellington.psd?raw=true)
to be kept as a reference, and will automatically form a proper rig when
imported in SkelForm.

![sample_psd](sample_psd.png)

## Main Structure

Bones are made out of groups, and all layers of a group will be merged to form
it's texture:

![group](group.png)

## Child Bones

Groups in groups will be children, however they must be first in the hierarchy.
They will be otherwise ignored if below a layer.

## Pivots

By default, bones created from groups will not have a dedicated pivot parent,
and will be centered.

To add a dedicated pivot, create a layer specifically named
<strong>$pivot</strong>, and make it a child of the group in question. The
pivot's position will be based on the top-left corner of the layer:

![pivot](pivot.png)

Although this layer will be invisible in the rig, you may need to draw on it to
be able to position it in your art program.

When importing the PSD, that group should now be comprised of 2 bones: the main
bone (pivot), and the texture. From here on out, it is recommended to only edit
the main bone.

## Inverse Kinematics

Layers starting with `$ik_` will be used to set IK properties to their
respective bones:

Effectors:

- <p class="ik-code"><code>$ik_start</code></p>
- <p class="ik-code"><code>$ik_middle</code></p>
- <p class="ik-code"><code>$ik_end</code></p>

Constraints:

- <p class="ik-code"><code>$ik_clockwise</code></p>
- <p class="ik-code"><code>$ik_counterclockwise</code></p>

![psd_ik](psd_ik.png)

Once imported, a target bone will be automatically generated and assigned.
