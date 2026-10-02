# Installation

Blender 4.2 or newer.

## Install

Install the **zip file**. Do not unzip it into Blender's folders by hand: a
hand-copied folder has no Uninstall button and can misbehave.

Easiest:

1. Drag `redlight_studio_kit-x.x.x.zip` onto the Blender window.
2. Confirm the install prompt.

Or:

1. **Edit > Preferences > Add-ons**.
2. Open the dropdown in the top-right corner and choose **Install from
   Disk...**
3. Pick `redlight_studio_kit-x.x.x.zip`.
4. Tick the checkbox next to **RedLight Studio Kit**.

The panel appears in the 3D Viewport sidebar. Press `N` and open the
**RedLight** tab.

## Update

Install the new zip the same way, over the top. Blender replaces the old
version. Rigs in your existing files keep working.

## Uninstall

1. **Edit > Preferences > Add-ons**.
2. Find **RedLight Studio Kit** and expand its row.
3. Click **Uninstall**.

??? note "No Uninstall button?"
    The add-on was copied onto disk by hand instead of installed from the
    zip. Untick it in Preferences, quit Blender, then delete this folder
    (`<version>` is your Blender version, for example `4.5`):

    - Windows: `%APPDATA%\Blender Foundation\Blender\<version>\extensions\user_default\redlight_studio_kit`
    - macOS: `~/Library/Application Support/Blender/<version>/extensions/user_default/redlight_studio_kit`
    - Linux: `~/.config/blender/<version>/extensions/user_default/redlight_studio_kit`

## Optional setup

In **Preferences > Add-ons > RedLight Studio Kit** you can set:

| Setting | What it does |
|---|---|
| **HDRI Folder** | A folder of `.hdr` / `.exr` files. They appear in the [HDRI](hdri.md) grid. |
| **Gobo / IES Folder** | A folder of gobo images and `.ies` profiles. They appear in the [Gobo & IES](light-textures.md) grids next to the 32 bundled IES profiles. |
| **License Key** | Optional. It identifies your order for support. The add-on works without it. |
