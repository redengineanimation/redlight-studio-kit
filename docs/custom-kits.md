# Custom Kits

Kits are plain JSON files. Add your own and they show up in the grid.

## Where they go

Put a `.json` file in the add-on's `kits` folder, with a preview image named
`<kit id>.png` next to it (256 x 256 works well). Restart Blender.

The folder is inside the installed add-on:

- Windows: `%APPDATA%\Blender Foundation\Blender\<version>\extensions\user_default\redlight_studio_kit\kits`
- macOS: `~/Library/Application Support/Blender/<version>/extensions/user_default/redlight_studio_kit/kits`
- Linux: `~/.config/blender/<version>/extensions/user_default/redlight_studio_kit/kits`

!!! warning "Keep a copy"
    Updating or uninstalling the add-on replaces this folder. Keep your kit
    files somewhere else too and copy them back after an update.

## Format

A file holds one kit, or a list of kits.

```json
{
  "id": "MY_KIT",
  "name": "My Kit",
  "category": "PRODUCT",
  "description": "Key from the right, soft fill, cool rim",
  "target": [0, 0, 0.4],
  "world": {"color": [0.02, 0.02, 0.02], "strength": 1.0},
  "backdrop": {"shape": "L_CURVE", "color": [0.2, 0.2, 0.2], "roughness": 0.6},
  "lights": [
    {"role": "KEY", "type": "AREA", "pos": [3, -3, 2.7], "energy": 650,
     "size": 2.0, "size_y": 1.5, "shape": "RECTANGLE", "color": [1, 1, 1]},
    {"role": "FILL", "type": "AREA", "pos": [-3, -2.4, 1.5], "energy": 260,
     "size": 2.8, "temperature": 7000},
    {"role": "RIM", "type": "SPOT", "pos": [0, 3, 3], "energy": 800,
     "spot_size": 25, "spot_blend": 0.3, "radius": 0.05}
  ]
}
```

Only `id`, `lights` and each light's `type`, `pos` and `energy` are required.

## Kit fields

| Field | Meaning |
|---|---|
| `id` | Unique id, also the preview file name. |
| `name`, `description` | Shown in the grid and under the thumbnail. |
| `category` | `PRODUCT`, `PORTRAIT`, `DRAMATIC`, `COLOR`, `GLASS`, `NATURAL` or `PATTERN` (Projection). |
| `target` | The point lights aim at, unless a light sets its own. Default `[0, 0, 0.4]`. |
| `world` | World `color` and `strength`. |
| `backdrop` | `shape`, `color`, `roughness`. The shape is only used when the rig has no backdrop yet. |

## Light fields

| Field | Applies to | Meaning |
|---|---|---|
| `type` | all | `AREA`, `SPOT`, `SUN` or `POINT` |
| `pos` | all | Position in metres, relative to the rig |
| `energy` | all | Watts (Sun: W/m2) |
| `role` | all | `KEY`, `FILL`, `RIM`, `BACK` or `TOP` |
| `name` | all | Object name |
| `color` | all | Linear RGB |
| `temperature` | all | Kelvin |
| `target` | all | Aim point for this light |
| `size`, `size_y`, `shape`, `spread` | Area | Size in metres; `RECTANGLE`, `SQUARE`, `DISK` or `ELLIPSE`; spread in degrees |
| `spot_size`, `spot_blend`, `radius` | Spot | Cone in degrees, edge blend, source radius |
| `radius` | Point | Source radius |
| `angle` | Sun | Angular size in degrees |
| `mask` | Spot | A projection mask, see below |

Author kits for a subject about 1 m tall at rig scale 1.

## Projection masks

Add a `mask` to a spot light to project a pattern:

```json
{"type": "SPOT", "pos": [-3, -2, 4], "energy": 1800, "spot_size": 80,
 "radius": 0.015, "target": [0, 1, 0],
 "mask": {"pattern": "blinds", "twist": 0}}
```

`pattern` is one of `blinds`, `window`, `lattice`, `slash`, `foliage`,
`checker`, `pinholes` or `bars`. `twist` rotates the pattern, in degrees.
Use a small `radius` (0.015) for crisp edges and about 0.05 for `foliage`.
