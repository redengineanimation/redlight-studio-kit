# HDRI

The HDRI section lights the scene with an environment map from your own
folder.

## Setup

1. **Edit > Preferences > Add-ons > RedLight Studio Kit**.
2. Set **HDRI Folder** to a folder of `.hdr` or `.exr` files.
3. Back in the panel, open **HDRI** and click **Refresh**.

RedLight builds a thumbnail for each file the first time it sees it, so a
large folder takes a moment on the first refresh.

## Controls

| Control | What it does |
|---|---|
| Thumbnail grid | Click to pick an HDRI. It is applied to the world straight away. |
| **Strength** | Environment brightness. |
| **Rotation** | Turns the environment around the vertical axis. |
| **Refresh** | Rescans the folder. |
| **Clear** | Removes the RedLight environment from the world. |

!!! tip "Keeping your HDRI when applying kits"
    A kit normally sets a solid world colour, which replaces the HDRI. Turn
    off **Set World** in [Studio Kits](kits.md#set-world-and-set-backdrop) to
    keep it.

No HDRIs are bundled in version 1.0.
