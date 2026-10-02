# FAQ

## Does it work in EEVEE?

Yes. Every kit, including the projection patterns, renders in EEVEE and
Cycles. Gobo images and IES profiles need Cycles. See
[EEVEE & Cycles](render-engines.md).

## Which Blender versions are supported?

Blender 4.2 and newer. It is tested on 4.5 LTS, 5.0, 5.1 and 5.2.

## Will applying a kit delete my own lights?

No. A swap only replaces lights that came from a kit. Lights you added with
Add Light stay, and so do the floor and cameras.

## My model is huge or tiny. Will the kits still work?

Yes. Select the model and click **Fit Rig to Selection**. The studio is
scaled to the model and light power is adjusted so the look stays the same.

## Some kits lose shadows in EEVEE. Why?

Kits with many lights can fill EEVEE's shadow memory. Raise **Render
Properties > Shadows > Pool Size** to 1024 MB. Cycles is not affected.

## I can't see the lights in my render. Is that right?

Yes. RedLight's lights are hidden from the camera on purpose. They still
light the scene and appear in reflections.

## Rig Transform doesn't move my floor or backdrop.

That is by design, so you can sweep the lighting around a fixed set. Use
**Fit Rig to Selection** to move the floor and backdrop under a model.

## My gobo or IES has no effect.

Check the render engine. Both need Cycles. Also check that the light named
at the top of the Light Texture section is the one you meant.

## Are HDRIs included?

The HDRI browser works with your own HDRI folder. None are bundled in
version 1.0. 32 IES profiles are included.

## Can I make my own kits?

Yes. See [Custom Kits](custom-kits.md).

## Do I need the license key?

No. The add-on works without it. The key identifies your order when you ask
for support.

## I had LuxKit installed. Anything to do?

Uninstall LuxKit before installing RedLight Studio Kit. They cannot be
enabled together. Rigs made with LuxKit keep working.
