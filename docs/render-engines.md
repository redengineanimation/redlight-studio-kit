# EEVEE & Cycles

RedLight works in both render engines. Two features need Cycles, and EEVEE
has one setting worth knowing about.

| Feature | EEVEE | Cycles |
|---|---|---|
| All 60 studio kits | Yes | Yes |
| Projection kits (pattern masks) | Yes | Yes |
| Backdrops, shadow-catcher floor | Yes | Yes |
| Cameras, HDRI | Yes | Yes |
| Gobo images | No | Yes |
| IES profiles | No | Yes |

Gobo images and IES profiles rely on light textures, which EEVEE does not
support. That is a Blender limitation. The panel warns you when the engine
is not Cycles.

## Missing shadows in EEVEE

Kits with many lights, such as **Ring Catchlight** (12 lights), can fill
EEVEE's shadow memory. EEVEE then drops shadows without an error in the
interface; the console prints `Shadow buffer full`.

Fix: **Render Properties > Shadows > Pool Size**, raise it to **1024 MB**.

## Looks differ slightly between engines

Cycles traces bounced light, so a brightly lit floor lifts the walls around
it. EEVEE approximates this, so the same kit can look a little darker in the
shadows. Turning on **Render Properties > Raytracing** in EEVEE brings the
two closer.
