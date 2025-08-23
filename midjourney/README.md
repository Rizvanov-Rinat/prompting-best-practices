# Midjourney Prompt Best Practices (Cheat Sheet)

A practical guide for writing effective prompts in **Midjourney**.

## Mini-Guide: Using ChatGPT to Draft Midjourney Prompts

**Copy‑paste this request to ChatGPT:**
```text
Convert my idea into a Midjourney prompt.

Formula (use exactly this order; keep text concise):
[Medium/Type] of [Subject + 2–3 vivid traits] [Action] in/at [Setting], [Style/Genre/Artist], [Lighting], [Palette], [Composition/Lens] --ar W:H --s N --c N --q 1 --seed SEED [--no X]

Rules: 

- Output in English and return only the final prompt (no quotes, no commentary).
- 8–25 strong words before the parameters. No filler.
- Positive wording only; if excluding, use --no ....
- Prefer numbers over vague plurals (“three lanterns”, “a flock of birds”).
- Front-load essentials (subject + must-have traits first).
- Use 1–2 clear style cues (medium/genre/artist).
- Put all parameters at the end.
- Pick aspect ratio logically: people/portraits --ar 4:5, wide scenes --ar 16:9, products/square graphics --ar 1:1.
- Unless the idea explicitly needs text/logos, add --no text.
- For anime/manga, add --niji (defaults to the latest Niji version).
- Choose sensible defaults if unspecified: --s 150, --c 10, and a 6–8 digit --seed.

My idea: <paste your idea here in any language>
```

Note: It’s recommended to specify the style and any key parameters up front. While tuning, keep the same --seed for comparability, and avoid changing many parameters at once.

---

## Recommended Prompt Algorithm
**[Type/Medium]** of **[subject]** **[doing action]** in/at **[setting]**, **[style/genre/artist]**, **[lighting]**, **[color palette]**, **[composition/lens]**  
Parameters at the end: `--ar W:H --s N --c N --q N --seed N [--no X]`  

### Golden Rules
- Lead with the essentials: put the subject + must-have traits first.
- Be specific, not long: 8–25 strong words > 60+ weak ones.
- Positive wording: say what to include; use --no for hard exclusions.
- Numbers beat plurals: “three lanterns,” “crowded street,” etc.
- One or two clear style cues: medium/genre/artist (don’t stack 5+).
- Change one thing per iteration: A/B compare small edits.  
**Ref:** [Prompt Basics](https://docs.midjourney.com/hc/en-us/articles/32023408776205-Prompt-Basics)

### Building Blocks (mix as needed)
- **Medium/Type:** photo, oil painting, watercolor, pixel art, 3D render, ink sketch, film still.  
- **Subject:** person/character/thing with 2–3 vivid traits (age, attire, texture).  
- **Action:** what the subject is doing (running, gazing, assembling).  
- **Setting/Background:** place, time, weather, ambiance.  
- **Style/Genre:** cyberpunk, film noir, Art Deco, ukiyo-e, surrealism, anime (*Niji*).  
- **Lighting:** soft light, rim light, golden hour, volumetric, chiaroscuro, neon.  
- **Color/Mood:** muted pastels, high-contrast, neon, moody, whimsical, teal–gold.  
- **Composition/Lens:** wide shot, portrait, isometric, macro, bird’s-eye, 35mm, telephoto.  
**Ref:** [Art of Prompting](https://docs.midjourney.com/hc/en-us/articles/32835253061645-Art-of-Prompting)

### Parameters (add at the end)
- `--ar W:H`  Aspect ratio (e.g., `16:9`, `4:5`, `1:2`). **Ref:** [Aspect Ratio](https://docs.midjourney.com/hc/en-us/articles/31894244298125-Aspect-Ratio)  
- `--s 0–1000`  **Stylize** — low = literal to prompt; high = more artistic. **Ref:** [Stylize](https://docs.midjourney.com/hc/en-us/articles/32196176868109-Stylize)  
- `--c 0–100`  **Chaos/Variety** — higher = more diverse grid / looser to prompt. **Ref:** [Chaos / Variety](https://docs.midjourney.com/hc/en-us/articles/32099348346765-Chaos-Variety)  
- `--q 0.25/0.5/1/2`  **Quality** — render time/detail. Use lower for drafts, higher for finals. **Ref:** [Quality](https://docs.midjourney.com/hc/en-us/articles/32176522101773-Quality)  
- `--seed N`  Reproducibility/controlled variations. **Ref:** [Seeds](https://docs.midjourney.com/hc/en-us/articles/32859204029709-Parameter-List)  
- `--no X`  Strongly exclude X (e.g., `--no text`, `--no people`). **Ref:** [`--no` parameter](https://docs.midjourney.com/hc/en-us/articles/32173351982093-No)  
- **Multi-prompt & weights:** `castle::2 mist::0.5` (emphasize/de-emphasize parts). Not compatible with version 7. **Ref:** [Multi-Prompts & Weights](https://docs.midjourney.com/hc/en-us/articles/32658968492557-Multi-Prompts-Weights)  


### Example

```text
Photo of a snow-dusted red cable car crossing a foggy valley at dawn, editorial NatGeo style, soft rim light, muted cool palette, telephoto compression --ar 3:2 --s 120 --c 10 --q 1 --seed 42 --no text
```

---

## Also Good to Know
- **Image prompts** pair well with concise text; match aspect ratios for better alignment. **Ref:** [Image Prompts](https://docs.midjourney.com/hc/en-us/articles/32040250122381-Image-Prompts)
- **Permutations** speed up exploration by expanding a single prompt into many. **Ref:** [Permutations](https://docs.midjourney.com/hc/en-us/articles/32761322355597-Permutations)
- **Remix** enables iterative changes to both prompt and parameters. **Ref:** [Remix/Variations](https://docs.midjourney.com/hc/en-us/articles/33329329805581-Modifying-Your-Creations)
- **Model versions** can change look and defaults; pick what fits your goal. **Ref:** [Version](https://docs.midjourney.com/hc/en-us/articles/32199405667853-Version)
- **Rendered size** depends on version/aspect; V7 1:1 upscales to 2048×2048 px. **Ref:** [Image Size & Resolution](https://docs.midjourney.com/hc/en-us/articles/33329374594957-Image-Size-Resolution)