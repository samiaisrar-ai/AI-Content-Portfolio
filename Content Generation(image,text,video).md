
# Content Generation with AI (Image • Text • Video)

**Purpose:** This document is a master template for writing and explaining each step of your AI-powered content workflow. Use it to document how you transform a raw input (e.g., a single bracelet photo) into multiple high-quality outputs (images, captions, hashtags, video scripts). Copy the relevant sections into your GitHub repo or case-study page.

---

## Table of contents

1. How to write & explain *each step* (single reusable template)
2. Example: Image step ("Cup hold" pose) — fully filled
3. Sections for Images, Text, Video — process checklists
4. Metadata, file naming & versioning
5. Repo & README presentation template
6. QA checklist and export specs
7. Small utilities: commit message / PR template

---

# 1. How to write & explain *each step* (Reusable Step Template)

For every discrete action you document (e.g., "Generate lifestyle image — Cup Hold") use the same small structure so readers quickly understand *what*, *why*, *how*, and *what to check*.

### Step header (one line)

`## Step X — Short descriptive title` (e.g., `## Step 02 — Lifestyle image: Cup hold`)

### 1. Objective

* Short sentence: what this step produces and why it matters. (1–2 lines)

### 2. Inputs

* Raw files (e.g., `raw.jpg`) and relevant assets (brand colors, logo)
* Prompts used (link to `prompts.md` or paste short prompt)
* Model / Tool / App used (e.g., Stable Diffusion XL via \[service], Photoshop 2025)

### 3. Output(s)

* Files produced (filenames + brief note: size, version) e.g., `cup_01.jpg (2048x2048)`, `cup_01_web.jpg (1200px)`

### 4. Step-by-step process (concise)

* 1–6 short bullet steps showing the exact actions (generate → select → edit → refine → export).
* Include commands or prompt variants with parameters when relevant.

### 5. Rationale / Design choices

* Why this style or setting? (audience, platform, tone)
* Anything intentionally omitted or emphasized (e.g., avoid busy backgrounds)

### 6. Quality checks (QA)

* How to inspect the output: sharpness, reflection artifacts, skin tones, color accuracy, alt text presence
* Minimum acceptance criteria (e.g., no visible seam lines; bracelet is in focus)

### 7. Notes & next steps

* Any follow-ups: alternate crops, reels, A/B test suggestions, hashtag sets

---

# 2. Example: Image step (Filled Template — *Cup hold*)

## Step 02 — Lifestyle image: Cup hold

**Objective**

* Create a realistic lifestyle image showing the uploaded bracelet on a hand holding a ceramic coffee cup. Use for Instagram and product pages.

**Inputs**

* `raw.jpg` (client-provided)
* Prompt (used for image generation / composition): *See `prompts.md` — "Place the uploaded bracelet on a well-groomed hand with fuchsia pink nails holding a ceramic coffee cup..."*
* Tools: Image generator (Stable Diffusion XL v1), Photoshop (retouch and color match), Lightroom (final tone)

**Outputs**

* `cup_01_highres.jpg` — 4000×4000 px (master)
* `cup_01_ig.jpg` — 1080×1350 px (Instagram portrait)
* `cup_01_thumb.jpg` — 400×400 px (preview)

**Process (short)**

1. Generate 8 variations with the prompt (adjust composition: cup angle, hand position).
2. Pick top 3 variations.
3. Patch-repair any artifact areas in Photoshop (skin smoothing, bracelet shadow alignment).
4. Color-correct to match brand tone (HSL, white balance).
5. Export master + social sizes and save to `images/` with version suffix.

**Rationale**

* Cup-hold is relatable and immediately shows scale and fit. It converts well on Instagram and lifestyle catalog pages.

**QA checks**

* Bracelet is in focus; no weird reflections.
* Skin tone natural and consistent across crops.
* Nail polish color matches fuchsia sample.
* No obvious generative artifacts near fingers.

**Next steps**

* Produce an alternate crop for a carousel cover.
* Generate 3 caption options + 10 hashtags in `captions.md`.

---

# 3. Sections for Images • Text • Video — Quick Process Checklists

## Images — Minimal process flow

1. **Generate / shoot**: create variations.
2. **Select**: mark 3 finalists.
3. **Edit**: retouch, color match, remove artifacts.
4. **Crop & export**: output master + platform sizes.
5. **Document**: save prompt, tool, parameters in `prompts.md` + add metadata.

**Image QA checklist (short)**

* Sharpness, focus on bracelet
* Correct exposure & white balance
* No pixel stretching/artifacts
* Right crop for platform

## Text — Caption & Hashtag flow

1. **Prompt generation**: create 5 caption variants (tone: playful, elegant, informative).
2. **Select + refine**: choose best 2 per platform.
3. **SEO/Keywords**: add 2–4 target keywords for blog or product page.
4. **Hashtag sets**: prepare 3 rotating sets (broad / niche / branded).
5. **Document**: add captions + hashtags to `captions.md` and `hashtags.md`.

**Text QA**

* Tone matches brand voice
* No grammar or cultural sensitivity issues
* Includes CTA where needed

## Video — Short Reels / Promo flow

1. **Script**: hook (0–3s), body (3–22s), CTA (22–30s).
2. **Shot list**: list frames/poses (cup hold, hair adjust, diary).
3. **Generate captions & subtitles**.
4. **Edit**: assemble, color grade, sound design.
5. **Export**: vertical 9:16 for reels, 1:1 for feed, MP4 H.264

**Video QA**

* Hook present and visible in first 3s
* Captions synced and legible
* Audio levels normalized

---

# 4. Metadata, File Naming & Versioning

**Filename pattern:**  `{assetType}_{style}_{seq}_v{version}.{ext}`

* Example: `img_cuphold_01_v1.jpg`, `txt_igcap_cup_v2.md`, `vid_reel_cup_v1.mp4`

**Metadata to store per asset** (add to `notes.md` or frontmatter in each markdown):

* `title:`
* `client:`
* `date:`
* `source_file:` (raw\.jpg)
* `prompt:` (exact string or link)
* `tool:` (model + parameters)
* `editor:` (who edited)
* `license:` (if any)

**Prompt history:** keep a short changelog with prompt variants and parameter tweaks so you can reproduce or A/B test later.

---

# 5. Repo & README presentation template

**Front README (quick structure):**

* Project overview + one-line result
* Before (raw\.jpg)
* After gallery (each with 1-line caption)
* How it was made (link to `text_generation_with_ai/prompts.md`)
* How to reproduce (requirements & commands)

**Case-study.md layout:**

1. Problem statement (what client gave)
2. Goal (what we aimed for)
3. Process (link to step-by-step entries)
4. Gallery (images with captions)
5. Results & metrics (if available)
6. Next steps

---

# 6. QA & Export Specs (recommended)

**Master images:** TIFF or max-quality JPG at original generation size (keep one master).
**Web exports:** JPG at 72–96ppi, sRGB, widths: 400, 1200, 2048 px depending on use.
**Instagram:** 1080×1080 (square), 1080×1350 (portrait)
**Reels:** MP4 H.264, 1080×1920, 30 fps

**Accessibility:** always include `alt` text for images in markdown and a short description for the visually impaired.

---

# 7. Small utilities (commit messages, PR template)

**Commit message template:**

```
feat(images): add cup-hold image variants (cup_01_highres.jpg, cup_01_ig.jpg)

chore(prompts): add prompt v3 for cup-hold image
```

**PR template (short):**

* Summary of changes
* Files added/updated
* How to preview
* QA checklist complete: yes/no

---

# Final notes & tips

* Keep each step short and consistent — readers should be able to skim and find the "Inputs" and "Outputs" quickly.
* Save prompts verbatim so you can reproduce results later.
* Use the metadata block at the top of each step for easy search and filtering inside the repo.

---

If you want, I can now **populate this template** with entries for your 6–8 bracelet images (prompts, captions, filenames), and generate the `captions.md` & `hashtags.md` ready for your repo.
