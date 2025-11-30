# 🎥 Camera Movements

This section defines the core camera movements used in video generation. Using precise terminology in your prompts helps the AI (Sora, Runway, Pika, Deforum) accurately visualize the physical motion in the scene.

## 1. Dolly Zoom / Dolly-in & Dolly-out
Physical movement of the camera towards or away from the subject. Unlike a digital zoom, this changes the perspective and depth, creating an immersive effect.

* **Dolly-in:** The camera physically moves forward. The background expands, and the subject becomes larger.
* **Dolly-out:** The camera physically moves backward. The subject shrinks, revealing more of the environment.

> **Prompts:** `dolly in`, `camera moving forward`, `approaching the subject`, `zooming in`
> `dolly out`, `camera pulling back`, `receding view`, `moving away`

## 2. Camera Pushes / Pulls Back
A variation of the Dolly move, often used for narrative emphasis.

* **Push in:** An aggressive or focused move towards a specific detail or face.
* **Pull back:** A retreat to reveal the full scene or context (The "Reveal" shot).

> **Prompts:** `slow push in`, `intense push towards face`, `creeping forward`
> `pull back to reveal whole city`, `slowly retreating camera`, `pulling away from subject`

## 3. Orbit Shot
The camera moves in a circle around a stationary subject. This allows the viewer to see the character or object from all angles while keeping them centered.

> **Prompts:** `orbit shot`, `camera circling around`, `360 degree view`, `arc shot`, `rotating camera`

## 4. Dolly-in/out + Orbit (Combined)
A complex move combining a push/pull with rotation. This creates a dynamic, sometimes dizzying effect (often associated with the "Vertigo" effect if combined with lens zoom).

> **Prompts:** `dynamic orbiting with dolly in`, `spiraling closer to subject`, `circling and pulling back`, `vortex camera movement`, `spiral shot`

## 5. Tilt Up / Tilt Down
The camera stays in a fixed position but rotates up or down (vertical panorama). Used to reveal the height of a building or follow a character's gaze.

* **Tilt Up:** Camera looks from bottom to top.
* **Tilt Down:** Camera looks from top to bottom.

> **Prompts:** `tilt up`, `tilting up to the sky`, `camera looks up`, `scanning upwards`
> `tilt down`, `tilting down to feet`, `looking down from building`

## 6. Pan / Horizontal & Vertical Move
Movement of the camera along the X or Y axis (sliding). Unlike Tilting, the camera itself physically shifts position.

* **Truck / Pan (Horizontal):** The camera moves left or right, parallel to the scene.
* **Pedestal (Vertical):** The camera physically rises or lowers (like an elevator).

> **Prompts:** `panning right`, `trucking left`, `camera sliding sideways`, `tracking shot`
> `pedestal up`, `camera rising vertically`, `slow lift up`, `drone rising`

## 7. Handheld Camera
Simulates shooting without a tripod/stabilizer. Adds realism, "shake," and a documentary or action movie feel.

> **Prompts:** `handheld camera style`, `shaky footage`, `documentary feel`, `rough camera movement`, `GoPro footage`, `pov shaking`, `amateur footage`

## 8. Tilt-Shift
An effect where the focus area is very narrow, and the top/bottom of the frame are blurred. This makes real cities or landscapes look like miniature toy models.

> **Prompts:** `tilt-shift photography`, `miniature effect`, `blur top and bottom`, `macro view of city`, `toy-like look`, `shallow depth of field`

## 9. Time-lapse
Fast-forwarded video showing long processes in seconds (clouds moving, city traffic, flowers blooming).

> **Prompts:** `time-lapse`, `fast forward`, `speeded up footage`, `clouds moving fast`, `hyperlapse`, `flow of time`

---

## ⚡ Tech Tip: Parameter Mapping

If you are using tools that allow parameter control (like Deforum or Motion LoRA), use this mapping:

| Movement Type | Parameter Example (Translation X/Y/Z) |
| :--- | :--- |
| **Dolly In** | `Translation Z: 1.0` (Positive) |
| **Dolly Out** | `Translation Z: -1.0` (Negative) |
| **Pan Right** | `Translation X: 1.0` |
| **Tilt Up** | `Rotation X: 1.0` |
| **Orbit** | `Translation X` + `Rotation Y` (Counter-balance) |