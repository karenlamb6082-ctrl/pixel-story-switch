# Adapting the bundled demo

[assets/demo.html](../assets/demo.html) is a self-contained starting point with a sunny desk, a walk to the bed, and a rainy night. Its code is divided into scene painting, glass compositing, and interaction. Read the functions for the part you are changing.

| To change | Start here |
| --- | --- |
| Order and timing of story beats | `readScene()` turns the normalized position into named values for the screen, weather, lighting, and poses. |
| Scene composition | `paintRoom()` sets the world origin and draws the furniture. `paintWindow()`, `paintPerson()`, and `paintQuilt()` draw the animated parts. |
| Capsule width or thumb travel | Keep the CSS stage aspect ratio and hit area in step with `frameWidth`, `trackRadius`, and `lensTravel`. The capsule width is twice the sum of the radius and thumb travel. Give the scene texture enough extra width for the lens to sample past the visible edge. |
| Lens character | The fragment shader maps lens pixels back into the room texture. The 2D renderer uses a clipped, magnified copy of that texture with a soft rim. |
| Drag or release feel | Pointer handlers choose `target`. `tick()` updates position with separate drag tracking and release settling. |

When changing a walking route, use distance along the route to advance the step cycle. The demo walks 72 scene pixels over 4.8 cycles. In the planted part of a cycle, a foot moves 9 pixels backward relative to the hips over 60% of a cycle. This cancels the 9 pixels of forward hip motion over that interval. The other foot swings forward and lifts, and the two phases are offset by half a cycle. When changing distance or cycle count, adjust the planted distance to match. Scale the gait in and out at the edges of the walk so the transition into sitting or standing reads cleanly.

Use the actual switch to hold the character at several progress values. Check that idle effects can continue while the story pose holds, that the glass still samples moving details, and that both scene and thumb settle at the chosen end. If the scene embeds into a larger page, keep the switch's hit area and touch gesture handling scoped to the component.
