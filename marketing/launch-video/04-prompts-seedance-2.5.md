# Seedance 2.5 prompts (run inside Higgsfield)

Two ways to generate. Use **A** first. If a shot drifts, regenerate only that shot with **B** and cut it in.

Reference slots (upload in this order so the `@Image` numbers match):

| Slot | File | What it locks |
|---|---|---|
| @Image1 | assets/phone-01-lab-history.png | Lab History screen |
| @Image2 | assets/phone-02-home-current-status.png | Home, eGFR gauge |
| @Image3 | assets/phone-03-food-guide.png | Food Guide (English) |
| @Image4 | assets/phone-04-blood-pressure.png | Blood Pressure screen |
| @Image5 | assets/phone-05-spanish-food-guide.png | Guía de alimentos |
| @Image6 | rosa-character.png (generate first, see workflow step 2) | Rosa's face and outfit |
| @Image7 | ana-character.png (generate first) | Ana's face and outfit |

Rules baked into every prompt:

- No on-screen text is requested. Words, captions, and the end card go in the editor.
- Phone screens are pinned to the reference image, described as "exactly the screen in @ImageN," and shown at an angle that lets you do a screen replacement in post if the UI drifts.
- Sound is ambient only, in `< >`. No `{dialogue}`: the voiceover is recorded separately so the English and Spanish cuts share one render.
- Camera moves are slow. Older audience, small screens.

---

## A. Master prompt, one 30-second pass (9:16)

Paste this whole block. Set duration 30 s, aspect 9:16, resolution 1080p or higher, audio on.

```
A quiet, warm, documentary-style commercial for a kidney-health phone app. Realistic, contemporary, natural light, shallow depth of field, gentle handheld or slow dolly only. Muted palette: cream, soft grey, wood, one teal accent from the phone screen. No text, captions, logos, or watermarks anywhere. Phone screens must match the reference images exactly.

Lead: the woman in @Image6, Rosa, 58, reading glasses, grey-streaked hair, oatmeal cardigan over a plain white tee. Same face and clothes in every shot.
Second: the woman in @Image7, Ana, early 30s, Rosa's daughter, dark ponytail, navy sweater. Appears only from 15s.

0-3s: Small sunlit kitchen, early morning, window light raking across a wooden table. Rosa sits holding a folded paper lab printout, glasses on, brow slightly furrowed, reading. Slow push in from medium shot to a close-up of her face. <kettle ticking, faint birdsong outside>

3-6s: Rack focus from the printout down to an iPhone lying face-up on the table. Rosa picks it up. The screen shows exactly the app home screen in @Image2, a yellow semicircle gauge with a large number and a "My Kidney Team" heading. Slight tilt up from the screen to her face as she reads it. <a single soft phone tap>

6-9s: Same kitchen, brighter, later morning. Static tabletop shot. A grey digital blood-pressure cuff is wrapped on Rosa's upper arm; her forearm rests on the table. The iPhone is propped against a mug beside it, screen toward camera, showing exactly the blood-pressure screen in @Image4 with a green check card. The cuff finishes deflating. <cuff releasing air with a soft hiss>

9-12s: Grocery store produce aisle, cool daylight, handheld over Rosa's shoulder. Her right hand hovers between a pile of apricots and a pile of green apples. In her left hand the iPhone shows exactly the food list in @Image3, green dot beside Apple, red dot beside Apricot. She picks up an apple. <store air-conditioning hum, paper bag crinkle>

12-15s: Plain bright clinic front desk. A nurse in navy scrubs, seen only from the shoulders down, slides a printed lab sheet across the counter. Medium close-up on Rosa's hands as she holds the sheet in one hand and, with the other, taps a teal plus button on the iPhone, which shows exactly the lab history screen in @Image1. <pen on paper, one tap>

15-21s: Kitchen at dusk, warm lamp light. Rosa at the table turns the iPhone toward Ana, who has just sat down opposite. Screen shows exactly the line chart in @Image1, a teal line with dots rising gently left to right. Slow push in on the phone, then rack focus to the two faces. Rosa gives a small, tired, genuine smile. Ana squeezes her hand. <chair scrape, quiet room tone>

21-25s: Same table, same light. Ana takes the phone and taps once; the screen now shows exactly the Spanish food list in @Image5. She turns it back to Rosa, who leans in and reads, nodding. Two-shot, static. <quiet room tone>

25-30s: Slow fade to a plain soft-grey background, evenly lit, empty. Nothing else in frame. Hold. <room tone fades to silence>
```

Negative guidance (put in the negative-prompt field if the UI offers one, otherwise append as a final line): `no text, no subtitles, no logos, no watermark, no extra fingers, no doctors in white coats, no hospital beds, no dialysis machines, no fast cuts, no whip pans, no lens flare, no dramatic music, no smiling stock-photo energy, phone screen must not invent new UI`.

Generate 4 seeds. Judge on: Rosa's face consistent across all seven scenes, phone screens legible and close to the references, no invented text. Expect the phone UI to be roughly right and plan on screen replacement for the close-ups.

---

## B. Per-shot prompts (5–8 s each, for repairs or for a Cinema Studio pass)

Same references, same negative guidance. Set the duration to the range shown. Pair each with the Higgsfield Cinema Studio preset noted.

**Shot 1, 4 s, preset "Slow Push In"**
```
Small sunlit kitchen, early morning, low window light across a wooden table. The woman in @Image6 (Rosa, 58, reading glasses, oatmeal cardigan) sits holding a folded paper lab printout, brow slightly furrowed, reading. Slow push in from medium to close-up. Realistic, shallow depth of field, muted warm palette. No text on screen. <kettle ticking, faint birdsong>
```

**Shot 2, 4 s, preset "Rack Focus" then "Tilt Up"**
```
Same kitchen table. Rack focus from a folded lab printout to an iPhone lying face-up beside it. Rosa (the woman in @Image6) picks it up; the screen shows exactly @Image2, a yellow semicircle gauge on a white card. Slight tilt from the screen up to her face as she reads. No text overlays. <one soft phone tap>
```

**Shot 3, 4 s, preset "Static" or "Locked Off"**
```
Tabletop-level static shot, kitchen, bright morning. Rosa (the woman in @Image6) has a grey digital blood-pressure cuff on her upper arm, forearm resting on the wooden table. An iPhone is propped against a ceramic mug beside her arm, screen toward camera, showing exactly @Image4 with its green check card. The cuff finishes deflating. Realistic, shallow depth of field. <cuff hissing softly as it releases>
```

**Shot 4, 4 s, preset "Handheld" (light)**
```
Grocery produce aisle, cool daylight, handheld over-the-shoulder behind Rosa (the woman in @Image6). Her right hand hovers between a pile of orange apricots and a pile of green apples. Her left hand holds an iPhone showing exactly @Image3, a food list with a green dot beside Apple and a red dot beside Apricot. She picks up an apple. No text overlays. <store hum, paper bag crinkle>
```

**Shot 5, 4 s, preset "Static", medium close-up**
```
Plain bright clinic front desk, white counter. A nurse in navy scrubs, framed shoulders-down only, slides a printed lab sheet across. Medium close-up on the hands of Rosa (the woman in @Image6) holding the sheet and tapping a teal plus button on an iPhone showing exactly @Image1. Realistic, soft light. No text overlays. <pen on paper, one tap>
```

**Shot 6, 7 s, preset "Slow Push In" then "Rack Focus"**
```
Kitchen at dusk, warm lamp light. Rosa (the woman in @Image6) at the table turns an iPhone toward Ana (the woman in @Image7, early 30s, navy sweater) who has just sat down opposite. The screen shows exactly @Image1, a teal line chart rising gently left to right. Slow push in on the phone, then rack focus to both faces. Rosa gives a small, tired, genuine smile; Ana squeezes her hand. No text overlays. <chair scrape, quiet room tone>
```

**Shot 7, 4 s, preset "Static" two-shot**
```
Same dusk kitchen table. Ana (the woman in @Image7) taps the iPhone once and turns it back to Rosa (the woman in @Image6); the screen now shows exactly @Image5, the Spanish food list. Rosa leans in and reads, nodding. Static two-shot, warm lamp light. No text overlays. <quiet room tone>
```

**Shot 8, 5 s, no preset**
```
Plain soft-grey background, evenly lit, nothing in frame, slow gentle fade in from the previous warm kitchen tone. Hold still. No text, no objects. <room tone fading to silence>
```
(The end card, logo, tagline, CTA and disclaimer are laid over this in the editor.)

---

## C. Character stills (generate before anything else, in Higgsfield's image tool)

**Rosa (@Image6)**
```
Photorealistic portrait, natural window light, a 58-year-old Latina woman with grey-streaked dark hair pulled back, reading glasses pushed up on her head, an oatmeal-coloured cardigan over a plain white tee, kind tired eyes, small closed-mouth smile, seated at a wooden kitchen table. 3:4, shallow depth of field, no text.
```

**Ana (@Image7)**
```
Photorealistic portrait, warm lamp light, a woman in her early 30s, Latina, dark hair in a low ponytail, navy crew-neck sweater, no makeup, attentive expression, seated at a wooden kitchen table. 3:4, shallow depth of field, no text.
```

Save the chosen stills as `assets/rosa-character.png` and `assets/ana-character.png`, lock them as Soul characters in Higgsfield, and upload them as references 6 and 7 for every video generation.
