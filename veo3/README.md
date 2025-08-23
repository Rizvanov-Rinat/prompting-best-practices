# Veo 3 Prompt Best Practices (Cheat Sheet)

A practical, compact guide for writing **video** prompts for **Google DeepMind Veo 3**. Links point to official docs.

## Mini‑Guide: Using Gemini/ChatGPT to Draft Veo 3 Prompts
**Copy‑paste this request to ChatGPT:**
```text
Convert my idea into a Veo 3 prompt.

Formula (use exactly this order; keep it concise and visual):
[Subject + 2–3 vivid traits] [Action] in/at [Context/Setting], [Style/Genre], [Camera/Composition], [Lighting/Color].
Audio: [Ambience/SFX/Music/Dialogue].
Negative: [comma‑separated items to avoid].
(no subtitles)

Rules:
- Output in English. Return only the final prompt (no explanations).
- One coherent shot; present tense; 12–40 impactful words before the “Audio/Negative” lines.
- Prioritize: Subject → Context → Action → Style → Camera → Lighting.
- Use concrete, visible details; avoid abstract feelings unless shown on screen.
- Numbers beat plurals (e.g., “five lanterns”, “two trucks”).
- State 1–2 style cues (cinematic, documentary‑style, anime, stop‑motion, etc.).
- Keep the same seed across iterations if your UI/API exposes it; change one variable at a time.
- Add “(no subtitles)” after dialogue to avoid fake captions.
- If needed, add a short “Negative:” list instead of saying “no …” inside the main sentence.

My idea: <paste your idea here in any language>
```

## Recommended Prompt Algorithm
1) **Subject** (who/what) → 2) **Context** (where/when) → 3) **Action** (doing what) → 4) **Style** (look/genre) → 5) **Camera/Composition** (shot type/motion) → 6) **Lighting/Color** (mood) → 7) **Audio** (ambience/music/dialogue) → 8) **Negative** (things to exclude).  
*Reference: “Core prompt elements”, “Ambiance/lighting”, “Camera & composition”, “Add audio”, “Negative prompts”.*

## Golden Rules
- **One shot per prompt.** Don’t cram multiple scenes; iterate instead.  
- **Front‑load essentials.** Put critical numbers/constraints early (“exactly six lanterns”).  
- **Stay visual.** Describe what the camera sees and hears.  
- **Iterate surgically.** Refine wording to fix faces, motion, or background drift.  
- **Consistency.** Reuse identical character/outfit descriptions to keep looks stable across clips.

## Building Blocks (mix as needed)
- **Style/Aesthetic:** cinematic; film noir; documentary‑style; anime; 3D cartoon; stop‑motion; surreal/abstract.  
- **Camera/Composition:** wide establishing shot; medium shot; close‑up; POV; handheld shaky; slow dolly‑in; tracking; aerial/drone; shallow depth of field.  
- **Lighting/Color:** golden hour; neon glow; cool blue night; high‑contrast chiaroscuro; soft diffuse light; warm key + cool rim.  
- **Audio:** ambience/SFX (*rain, city hum, waves*); music (*soft piano, suspenseful strings*); dialogue (*He says: “…”*). Add “(no subtitles)”.  
- **Negative (examples):** text, subtitles, wall, frame, logo, gore, watermark, extra hands.

## Audio & Dialogue (Veo 3 supports native audio)
- Put sound cues on a separate **Audio:** line for clarity.  
- For exact lines, write dialogue in quotes and identify the speaker if needed (*The man in the red hat says: “…”*).  
- To avoid hardcoded captions, append **(no subtitles)** after the audio lines.

## Negative Prompts
Use a short **Negative:** line with comma‑separated items (or the API/UI **negativePrompt** field). Prefer descriptors (“text, wall, subtitles”) over “don’t/no …” in the main sentence.

## Parameters / API Notes (check your runtime)
- **Aspect ratio / duration / resolution**: depend on model version & host (Vertex AI vs Gemini API). Default outputs are commonly **landscape**; verify current limits in docs.  
- **Reference images:** you can drive style/content by adding 1–N images + a prompt; refer to subjects unambiguously (*“the woman in the red coat”*).  
- **Seed:** if exposed by your UI/API, keep it fixed while tuning wording to compare results.  
- **People generation:** subject to regional policy; check the current limits in docs.

## Example
```
On a soft rug in a child’s bedroom lies a large illustrated picture book, closed and pristine. The camera hovers above it as the book suddenly flips open, and—boom!—a colorful arc of miniature castles, model towns, toy soldiers, trains, and dragons explodes outward. Buildings unfold mid-air, a drawbridge slams down, and a tiny hot air balloon spins before landing atop a storybook mountain. Plush animals bounce into place beside trees and toy tents. The motion is whimsical, elastic, full of playful energy. The camera glides through the scene, revealing a miniature dreamworld built from stories. The book stays open at the center, pages fluttering slightly in the breeze.
```

Note: This prompt was taken from [FlowTV](https://labs.google/flow/tv/channel/boomtown). Testing different prompts is good practice.

## Scope & Defaults
- **Model**: Veo 3 (Gemini API). Generates **8‑second, 720p, 24 fps** video **with native audio**.
- **Aspect ratios**: **16:9** for Veo 3/3 Fast. Vertex AI docs show 9:16 examples but note **`veo-3.0-generate-001` does not support 9:16**.
- **People generation**: Region‑dependent restrictions.

---

## References & Further Reading
- **Veo Prompt Guide (DeepMind):** define style, camera, and use dialogue to set tone.  
  https://deepmind.google/models/veo/prompt-guide/
- **Vertex AI: Video prompt guide for Veo** — subject, context, action, camera, lighting refinements.  
  https://cloud.google.com/vertex-ai/generative-ai/docs/video/video-gen-prompt-guide
- **Veo on Vertex AI (model reference):** inputs, image‑to‑video, parameters.  
  https://cloud.google.com/vertex-ai/generative-ai/docs/model-reference/veo-video-generation
- **Veo overview & Responsible AI (Vertex AI):** approvals for people/children, safety notes.  
  https://cloud.google.com/vertex-ai/generative-ai/docs/video/overview
- **Gemini API: Video with Veo 3 (audio prompting):** dialogue, SFX, ambient noise cues.  
  https://ai.google.dev/gemini-api/docs/video
- **Veo 3 on DeepMind:** native audio, realism, prompt adherence.  
  https://deepmind.google/models/veo/
- **FYI (current limits & tips):** Preview models often cap clip length (~8s) and subtitles may appear; iterate with concise dialogue and **(no subtitles)**.  
  8s discussion: https://support.google.com/gemini/thread/346858612  ·  Subtitle tips: https://discuss.ai.google.dev/t/how-to-fix-and-disable-veo-subtitle-errors/98636