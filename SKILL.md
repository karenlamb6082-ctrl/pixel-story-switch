---
name: pixel-story-switch
description: Build or refine draggable pixel-art switches where the thumb scrubs a miniature scene between two states, such as a day-to-night room or a character going to bed. Use for 像素场景开关、昼夜切换、可拖动剧情 and liquid-glass lenses that refract the scene beneath them.
---

# Pixel Story Switch

Make the route between the two switch states visible. Pick two readable endpoint poses and give the user something to discover when they stop halfway.

1. **Lay out the scene for the thumb's path.** Put the main subject of each state near its thumb endpoint. Leave a readable route for movement. For a new standalone scene, copy [assets/demo.html](assets/demo.html) to the destination and adapt it. For an existing app, reuse its component and input patterns and take only the scene or rendering techniques the task calls for.
2. **Make drag position the story clock.** Use one normalized position from 0 to 1 for scene poses, lighting, props, and effects. Give each beat a progress range so the pose holds at mid-drag and scrubs cleanly in reverse. Use elapsed time for idle details such as drifting clouds, rain, or breathing. Keep committed on/off state separate from the animated position.
3. **Paint the scene before compositing the lens.** Render a low-resolution room with nearest-neighbor sampling. Clip it inside the capsule and resample that same room inside the lens. Use a stable magnified center, stronger bending near the rim, and restrained reflection. If retaining the bundled renderer, keep its Canvas 2D fallback and update both rendering paths when changing geometry.
4. **Check the handoff from gesture to state.** Let a click and keyboard activate the control. Use pointer capture during a drag, choose an endpoint on release, and return to the committed endpoint on cancellation. Use an accessible switch and update its checked state when the endpoint is chosen. Respect reduced motion.

Read [references/adapting-demo.md](references/adapting-demo.md) when modifying the bundled geometry, scene timeline, or character gait. In a browser, check both endpoints, a held midpoint, reverse drag, and keyboard activation. When walking is part of the story, inspect consecutive mid-stride positions and check that the supporting shoe stays on the floor.
