# Higgsfield workflow (Seedance 2.5)

Menu labels move around on Higgsfield. The steps below describe what to do; if a button is named differently on the day, look for the equivalent.

## 0. Before you open Higgsfield

- Have the seven reference images ready (five phone screens in `assets/`, plus Rosa and Ana once generated).
- Record the VO. Two takes each, English and Spanish, from `03-script-and-storyboard.md`. A human reader is better; if you use a voice model, pick a warm mid-50s female voice and slow it down. Export 48 kHz WAV.
- Pick one soft piano track, 30 s, no build, no drop.

## 1. Set up the project

1. Open Higgsfield, go to the video generator, choose **Seedance 2.5** as the model.
2. Aspect **9:16**, resolution **1080p** (4K if the plan allows, you'll downscale anyway), duration **30 s**, audio **on**.
3. Creative controls (these are set outside the prompt on Seedance 2.5): Era **contemporary**, Genre **documentary commercial**, Lighting **natural soft daylight**, Physics **realistic**.

## 2. Make the two characters

1. In Higgsfield's image generator, run the Rosa and Ana prompts from section C of `04-prompts-seedance-2.5.md`. Generate 4 of each, pick the one with the calmest, most real face.
2. Save each as a **Soul** character (or whatever the character-lock feature is called today) so the same face can be pinned across shots.
3. Save the PNGs into `assets/` as `rosa-character.png` and `ana-character.png`.

**Already generated (2026-09-06), pending your approval:** two candidate stills were produced outside Higgsfield and are hosted here. Open each, check the face reads as real and warm, then download and upload as references 6 and 7. If either misses, regenerate it in Higgsfield with the section C prompt.

- Rosa: https://cdn.gamma.app/rf4e5jwe01g0ap7/design-anything/9UulD8JSN3VqmBvGXqAwF/LeWhFE05nTN1TgS7RvLzv.jpg
- Ana: https://cdn.gamma.app/rf4e5jwe01g0ap7/design-anything/6VSLH6CcEcc2eYMPjU4HC/KtTdUrDf4P8tr4qdf7Se0.jpg

These have not been visually reviewed. Egress policy in the session that made them blocked the download, so treat them as unvetted candidates, not approved references.

## 3. Upload references

Upload in this exact order so `@Image1` through `@Image7` match the prompt: the five phone screens, then Rosa, then Ana. References go in before the prompt, not after.

## 4. Generate the master pass

1. Paste the master prompt (section A). Put the negative line in the negative-prompt field if there is one.
2. Generate **4 seeds**. Don't judge on the first one.
3. If Higgsfield Assist offers a rewrite, only accept changes that keep the timestamps, the `@Image` pins, and the "no text" lines.
4. Pick the best. Use Seedance 2.5's timestamp editing to re-roll any single time range that broke (a wrong face, a phone showing invented UI) without touching the rest.

## 5. Repair or upgrade individual shots

For any scene that still won't behave, switch to per-shot prompts (section B):

1. Open **Cinema Studio**, choose a full-frame body and a 35 mm or 50 mm lens, then apply the preset named next to each shot (Slow Push In, Rack Focus, Static, Handheld).
2. Keep the same references and negative line.
3. Generate 3–4 seeds per shot and stitch in the editor.

## 6. Edit (CapCut, DaVinci Resolve, or Higgsfield's own editor)

1. Lay the 30 s render or the stitched shots on the timeline.
2. **Screen replacement** on every phone close-up (shots 2, 3, 4, 5, 6, 7): track the phone screen and drop in the real screenshot from `assets/`. This is the single step that keeps a nephrologist's app from looking fake. Do it even if the render looks close.
3. VO on its own track. Music at about -24 LUFS under the VO. Keep the generated ambient sound, ducked.
4. Lower thirds at 6 s, 9 s, 12 s: **Check**, **Pick**, **Log** (Spanish: Mide, Elige, Anota). At 21 s: **English · Español**.
5. End card at 25 s on the grey hold: teal app icon, **My Kidney Team**, *Kidneys don't hurt. They send numbers.*, **Free on the App Store**, and a small but readable **Not medical advice. Talk to your care team.**
6. Burn open captions.

## 7. Export

| Cut | Size | Codec | Notes |
|---|---|---|---|
| 9:16 hero | 1080×1920, 30 fps | H.264, ~12 Mbps | Reels, TikTok, Shorts |
| 16:9 | 1920×1080 | same | Re-frame, don't just letterbox; the kitchen shots have room |
| 1:1 | 1080×1080, 15 s | same | Shots 1, 2, 3, 4, 8 |
| Spanish 9:16 | 1080×1920 | same | Same render, Spanish VO, captions, and @Image5 on the phone in shots 3–6 via screen replacement |

## 8. Before publishing

- Watch it once muted. Does it still make sense from captions and screens alone?
- Watch it once at phone size, arm's length. Can you read the lower thirds and the disclaimer?
- Show it to one person over 55 who isn't in healthcare. Ask what the app does. If they can't say "track blood pressure, food, and labs," fix the cut, not the copy.

## Connector status note

As of 2026-09-06 the Higgsfield connector is installed on this account but shows
`enabledInChat: false`, so its tools are not loaded in an agent session and the
render cannot be triggered from Claude Code. Enable Higgsfield in the chat's
connector settings (the toggle beside the connector in this conversation), start
a fresh session, and the master prompt in `04-prompts-seedance-2.5.md` can be
submitted directly. Until then, run steps 1 through 7 in the Higgsfield web app.
