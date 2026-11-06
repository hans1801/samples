# ☕ Mi primer video con IA: prompts de la campaña

Prompts usados en el video para crear dos comerciales y tres reels de **Sorbazo**, una marca de café inventada, con Higgsfield.

> 📺 **Video en YouTube:** [Ver el tutorial en el canal](https://youtube.com/@hansacha)

---

## 📋 Orden de uso

| Paso | Qué se crea | Modelo |
|---|---|---|
| **1** | Logo y vaso | GPT Image 2.6 Flare |
| **2** | Vaso con logo | GPT Image 2.6 Sunburst |
| **3** | Personaje | GPT Image 2.6 Flare |
| **4** | Hoja de personaje | GPT Image 2.6 Sunburst |
| **5** | Oficina oscura e iluminada | Flare y Sunburst |
| **6** | Comercial | Seedance 2.5 |
| **7** | Versión en la biblioteca | Flare, Sunburst y Seedance 2.5 |
| **8** | Reels | Genjutsu |

En Seedance y Genjutsu, escribe `@` y elige cada imagen en el menú. No basta con pegar el texto.

---

## 🖼️ Imágenes

### Logo

Flare · 1:1 · calidad alta · 2K

```text
Original logo design for an energizing iced coffee brand called "SORBAZO". A single bold coffee bean, tilted upward, whose center line is a sharp rising spark, with small radiating strokes around the top like a sunrise bursting with energy. Below the bean, the word "SORBAZO" in bold rounded uppercase letters, spelled exactly S-O-R-B-A-Z-O. Confident, modern, hand-crafted coffee-shop feeling, simple enough to print in one color. Solid warm white mark and text on a flat deep espresso brown background, centered, clean edges, no shadows, no mockup. No other words, no numbers, no slogan, no lightning bolt, not resembling any existing brand.
```

### Vaso

Flare · 1:1 · calidad alta · 2K

```text
Clean product photograph of one original takeaway iced coffee in a clear plastic cup, filled with creamy iced coffee and ice cubes, with a matte black flat lid and a bright orange straw. No icon, no words, no letters, no brand name, no logos. Centered, plain light-grey studio background, soft even lighting, sharp focus, realistic condensation.
```

### Vaso con logo

Sunburst · 1:1 · calidad alta · 2K · `@Image 1` vaso · `@Image 2` logo

```text
Keep the exact same cup from @Image 1, with the same lid, straw, coffee and lighting. Print the logo from @Image 2, including its word, on the front as a real one-color warm white screen print, without its brown background, medium size. Copy the logo and lettering exactly. The ink follows the curve of the cup, with condensation droplets over the print, so it looks printed at the factory and not like a sticker. Plain light-grey studio background, realistic product photography. No other words, no other logos.
```

### Personaje

Flare · 3:4 · calidad alta · 2K

```text
Full-body character design photograph of an original adult male office worker, about 35 years old, exhausted but likable. Short messy dark hair, dark under-eye circles, two-day stubble, tired expressive face. He wears a wrinkled light-blue dress shirt half untucked, a loose red tie, plain grey trousers and worn black shoes. Standing straight, facing the camera, both hands empty and clearly visible. Plain light-grey studio background, soft even lighting, realistic proportions, natural skin texture. One person only. No glasses, no badge, no logos, no text.
```

### Hoja de personaje

Sunburst · 16:9 · calidad alta · 2K · adjuntar el personaje

```text
Using the attached image @Image 1 as the identity reference, create a clean three-panel character reference sheet of exactly the same man. Left panel: full-body front view. Center panel: full-body right profile view. Right panel: a large close-up of his face from the front. Preserve the exact same face, messy dark hair, under-eye circles, stubble, wrinkled light-blue shirt, loose red tie, grey trousers and worn black shoes in all panels. Plain light-grey background, even lighting, realistic photo. No extra people, no labels, no text, no logos.
```

### Oficina oscura

Flare · 16:9 · calidad alta · 2K

```text
Empty ordinary office at night, photographed from the visitor side of one desk, at seated eye level, looking directly at the empty office chair, which faces the camera. On the desk there is a keyboard in front of the chair, tall stacks of white paper on both sides, and a computer monitor seen from behind, pushed to the far left so it does not block the chair. Behind the chair, grey cubicles, a printer and rows of ceiling lights, all switched off. The room is dark and dull, with a cold blue glow from the hidden screen falling on the chair and one flickering fluorescent tube. Realistic photography, sharp details. No people, no cups, no logos, no text.
```

### Oficina iluminada

Sunburst · 16:9 · calidad alta · 2K · adjuntar la oficina oscura

```text
Using the attached image @Image 1 as the location reference, show exactly the same office from exactly the same camera angle, with the same desk, keyboard, chair, monitor seen from behind, paper stacks, cubicles, printer and ceiling. Change only the lighting and energy: every ceiling light is now on, the room is bright and vivid with warm white light and clean, saturated colors, as if the whole office has just woken up. No people, no cups, no logos, no text.
```

---

## 🎬 Comercial

### Comercial en la oficina

Seedance 2.5 · 15 s · 16:9 · `@Image 1` hoja · `@Image 2` vaso con logo · `@Image 3` oficina oscura · `@Image 4` oficina iluminada

```text
@Image 1 is the only person, one office worker. Use the sheet only for his identity and wardrobe, never as a layout. Keep his face, messy hair, wrinkled light-blue shirt and loose red tie the same throughout. @Image 2 is the only coffee, the same cup with black lid, orange straw and the white coffee bean logo with the word SORBAZO printed on the plastic. @Image 3 is the office at the start, dark and dull. @Image 4 is exactly the same office after it transforms, bright and vivid. A fast 15-second comedy commercial with quick cuts. Continuity rule for every shot: the camera is always on the visitor side of the desk, in front of him. He sits in the chair, always facing the camera, with the keyboard in front of him and the back of the monitor at the left of the frame. Never show him from behind and never show the front of the screen. 0-2 seconds: dark office, he is already nodding off, his head dropping toward the keyboard, the cup on the desk. 2-4 seconds: close-up, his hand lifts the cup to his mouth, he takes one sip through the straw and his eyes snap wide open. 4-7 seconds: medium shot of him staring ahead as the ceiling lights turn on row after row from the back of the room toward the camera, and the whole office changes from dark and grey to bright and colorful, with natural skin tones on his face. 7-10 seconds: he types at impossible speed, his fingers a blur, then throws his arms up as white sheets of paper fly into the air around him. 10-15 seconds: he grins at the camera, lifts the cup and holds it out toward the lens until the printed coffee bean logo and the word SORBAZO are sharp and centered, papers still falling behind him. Sound: buzzing light, a soft snore, ice and one long sip, a loud click for each row of lights, frantic typing, a rush of paper, then one final sip. No music, no dialogue, no text on screen, no extra people.
```

---

## 📚 Versión en la biblioteca

### Biblioteca oscura

Flare · 16:9 · calidad alta · 2K

```text
Empty grand old library at night, photographed from the opposite side of one wooden desk, at seated eye level, looking directly at the empty chair, which faces the camera. On the desk there is a laptop seen from behind, pushed to the far left so it does not block the chair, and tall stacks of white paper on both sides. Behind the chair, dark carved wood, tall bookshelves, an upper balcony and rows of hanging brass lamps, all switched off. The room is dark and dull, with a cold glow from the hidden laptop screen falling on the chair. Realistic photography, sharp details. No people, no cups, no logos, no text.
```

### Biblioteca iluminada

Sunburst · 16:9 · calidad alta · 2K · adjuntar la biblioteca oscura

```text
Using the attached image @Image 1 as the location reference, show exactly the same library from exactly the same camera angle, with the same desk, chair, laptop seen from behind, paper stacks, bookshelves and balcony. Change only the lighting and energy: every hanging lamp is now on, the room is warm, golden and vivid, as if the whole library has just woken up. No people, no cups, no logos, no text.
```

### Comercial en la biblioteca

Seedance 2.5 · 15 s · 16:9 · 720p · `@Image 1` hoja · `@Image 2` vaso con logo · `@Image 3` biblioteca oscura · `@Image 4` biblioteca iluminada

```text
@Image 1 is the only person, one office worker. Use the sheet only for his identity and wardrobe, never as a layout. Keep his face, messy hair, wrinkled light-blue shirt and loose red tie the same throughout. @Image 2 is the only coffee, the same cup with black lid, orange straw and the white coffee bean logo with the word SORBAZO printed on the plastic. @Image 3 is a grand old library at the start, dark and dull. @Image 4 is exactly the same library after it transforms, warm, golden and vivid. A fast 15-second comedy commercial with quick cuts. Continuity rule for every shot: the camera is always on the opposite side of the wooden desk, in front of him. He sits in the chair, always facing the camera, with a laptop keyboard in front of him and the back of the laptop at the left of the frame. Never show him from behind and never show the front of the screen. 0-2 seconds: dark library, he is already nodding off, his head dropping toward the keyboard, the cup on the desk. 2-4 seconds: close-up, his hand lifts the cup to his mouth, he takes one sip through the straw and his eyes snap wide open. 4-7 seconds: medium shot of him staring ahead as the hanging lamps turn on row after row from the back of the room toward the camera, and the whole library changes from dark and grey to warm and golden, with natural skin tones on his face. 7-10 seconds: he types at impossible speed, his fingers a blur, then throws his arms up as white sheets of paper fly into the air around him. 10-15 seconds: he grins at the camera, lifts the cup and holds it out toward the lens until the printed coffee bean logo and the word SORBAZO are sharp and centered, papers still falling behind him. Sound: quiet ticking clock, a soft snore, ice and one long sip, a soft clunk for each row of lamps, frantic typing, a rush of paper, then one final sip. No music, no dialogue, no text on screen, no extra people.
```

---

## 📱 Reels

Genjutsu → Community trending → Recreate · 720p

### Prompt 1

`@Image 1` bebida · `@Image 2` persona · `@Video 1` plantilla

```text
Face identity is the highest priority: the man's face must stay identical to @Image 2 in every frame, above everything else.
Recreate the motion, camera movement, lighting, pacing and timing of @Video 1 exactly, but replace the man in the video with the real man from @Image 2, and replace the drink in the video with the drink from @Image 1.
The man: @Image 2 shows the same real man from several angles, wearing sunglasses. In every frame he wears the exact same sunglasses as in @Image 2, with the same frame shape, color, lens tint and size, sitting naturally on his face. Never remove, change or swap them. His face must be an exact match to @Image 2 in every frame: same face shape, jawline, nose, mouth, cheeks, ears, dark groomed beard with gray streaks, hairstyle, hairline and skin tone. Do not invent a different person. Keep his face recognizable from every camera angle. Serious calm expression, absolutely no smile. He looks like a real human filmed with a real camera: natural skin with visible pores and fine lines, realistic hair and beard strands, natural hands and body movement. Photorealistic live-action footage only, not AI-looking, not waxy or airbrushed, not a painting, not an illustration, not 3D.
His outfit and body build must also match @Image 2 exactly in every frame.
The drink: use the drink from @Image 1 exactly as it appears, with the same cup, shape, colors, lid, straw or opening, and the same logo and printing. Copy the logo and all its text exactly from @Image 1, never rewrite, redraw or change them. The logo side of the cup faces the camera in every frame and is never turned away or covered by his hand.
Action: he picks up the drink and drinks it the natural way for this type of cup, with the same motion and timing as @Video 1, then lowers it.
Remove any text, logo or watermark that appears in @Video 1. No added text anywhere.
Keep the same environment, lighting and camera movement as @Video 1. Cinematic, realistic, no extra objects.
```

### Prompt 2

`@Image 1` hoja · `@Image 2` vaso con logo

```text
Keep the exact motion, camera, timing and location of the video. Replace the person with @Image 1, using the sheet only for his identity and wardrobe, and keep his face, messy hair, wrinkled light-blue shirt and loose red tie the same in every frame, with no sunglasses. Replace the drink with @Image 2, keeping the white coffee bean logo and the word SORBAZO printed on the cup and clearly visible. Everything else stays the same. No other text, no captions, no other logos, no watermark.
- No text anywhere
```

### Prompt 3

`@Image 1` hoja · `@Image 2` vaso con logo

```text
Keep the exact motion, camera, timing and location of the video. Replace the person with @Image 1, using the sheet only for his identity and wardrobe, and keep his face, messy hair, wrinkled light-blue shirt and loose red tie the same in every frame, with no sunglasses. Replace the drink with @Image 2, keeping the white coffee bean logo and the word SORBAZO printed on the cup and clearly visible. Everything else stays the same. No other text, no captions, no other logos, no watermark.
```
