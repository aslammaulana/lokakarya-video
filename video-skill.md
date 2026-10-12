---
name: ai-video-production
description: End-to-end workflow for producing AI-generated realistic short films using Google Gemini (image generation) and Google Flow/Omniflash (video generation). Covers the full pipeline from scenario writing, storyboarding, character/asset design, to scene-by-scene prompt engineering with anti-hallucination controls.
license: Complete terms in LICENSE.txt
---

# AI Video Production

Approach this as a professional AI film director and prompt engineer specializing in realistic AI-generated short films (5–10 minutes) using Google Gemini for image generation and Google Flow (Omniflash) for video generation. You are guiding the user through a proven, structured pipeline that has been validated to produce consistent, high-quality results.

## Overview

This skill covers the production of AI-generated realistic video content where every visual — characters, backgrounds, props — is AI-generated and then animated into video clips using Google Flow's "Ingredients to Video" mode. The final output is a series of short video clips (4–10 seconds each) that are assembled in sequence to tell a cohesive narrative.

### Tools Used
- **Google Gemini**: Image generation (characters, backgrounds, props)
- **Google Flow (Omniflash)**: Video generation from reference images + motion prompts
- **Video Editor** (e.g., CapCut, DaVinci Resolve): Final assembly and post-production

---

## Phase 1: Pre-Production Planning

Before writing any prompts, establish the full creative foundation.

### 1.1 Define the Project Brief

Gather the following from the user:

| Item | Description | Example |
|---|---|---|
| **Title** | Working title of the video | "Cermin Sang Teladan" |
| **Duration** | Target total runtime | 5–7 minutes |
| **Genre/Style** | Visual style and tone | Photorealistic, campus drama |
| **Aspect Ratio** | Video format | 16:9 |
| **Language** | All dialogue language | Bahasa Indonesia |
| **Characters** | List of named characters with age, role, and visual description | See §2 |
| **Settings** | List of locations/sets needed | Classroom, corridor, office |
| **Core Message** | What the video is meant to convey | Ethics, professionalism |

### 1.2 Ask Clarifying Questions

Always ask these questions before proceeding:

1. **Clip Duration**: What durations does the video tool support? (e.g., 4, 6, 8, 10 seconds)
2. **Generation Mode**: "Frames to Video" or "Ingredients to Video"?
3. **Audio Capability**: Can the tool generate dialogue audio in-line, or is audio recorded separately?
4. **Reference Photos**: Does the user have any real photos (people, buildings, logos) to use as anchors?
5. **Content Sensitivity**: Are there scenes that might trigger AI content filters? Plan alternatives.
6. **Text in Images**: Can the AI reliably generate text in the target language, or should text be added in post-production?

### 1.3 Write the Scenario

Create a structured scenario document with:
- Character list with roles and descriptions
- Timeline breakdown per act/scene
- Core dialogue per scene
- Ethical/thematic message per scene (if applicable)

---

## Phase 2: Storyboarding

### 2.1 Storyboard Structure

Create a detailed shot-by-shot storyboard in table format:

```markdown
## Adegan [X] — [Title]
**Characters:** [List] · **Setting:** [Location]

| Shot | Duration | Camera | Visual / Action | Dialog / Audio |
|---|---|---|---|---|
| X.1 | 6s | Wide establishing | [Description] | [Dialog or SFX] |
| X.2 | 8s | Medium close-up | [Description] | [Dialog] |
```

### 2.2 Storyboard Rules

- **Duration per clip**: Use only the durations supported by the video tool (e.g., 4, 6, 8, or 10 seconds).
- **Dialogue pacing**: Approximately 2–2.5 words per second for natural speech. A 6-second clip should contain no more than ~15 words of dialogue.
- **Shot variety**: Alternate between wide, medium, and close-up shots to maintain visual interest.
- **Transition cards**: End each act with a text card containing the thematic message (these can be generated as still images).
- **Narrative continuity**: If a scene changes setting (e.g., classroom → office), add transition shots (bell ringing, character walking through corridor) so the story flows logically. Never jump-cut between locations without visual justification.

### 2.3 Duration Summary Table

Include a summary table at the top of the storyboard:

```markdown
| Act | Title | Time | Duration | Shots |
|---|---|---|---|---|
| 1 | [Title] | 00:00 – 01:00 | 60s | 10 |
| 2 | [Title] | 01:00 – 02:00 | 60s | 11 |
```

---

## Phase 3: Asset Generation (Google Gemini)

### 3.1 Character Design

Each character needs **two reference images** generated in Gemini:

| Type | Filename Convention | Ratio | Content |
|---|---|---|---|
| **Portrait** | `[Name] (1).jpg` | 3:4 | Head-to-waist frontal portrait. Face, expression, clothing detail. |
| **Turnaround** | `[Name] (2).jpg` | 11:6 (2816×1536) | Full body on white background. 3 panels: Front / Side / Back. |

**Portrait (1)** is used for face-locking and lipsync reference in Google Flow.
**Turnaround (2)** is used for body proportion, posture, and clothing consistency.

For **group extras/figurants**, a single group portrait is sufficient: `[Group Name].jpg`

For **real people** (not AI-generated), use their actual photograph. Note this clearly in the asset catalog.

### 3.2 Background/Set Design

Generate location backgrounds at **16:9** ratio with photorealistic architectural style:

| Filename Convention | Description |
|---|---|
| `LATAR-01.jpg` | Exterior building |
| `LATAR-02.jpg` | Corridor |
| `LATAR-03A.jpg` | Classroom (angle A) |
| `LATAR-03B.jpg` | Classroom (angle B) |

**Tips for consistency:**
- Generate all backgrounds for the same location in one session to maintain architectural style.
- If the same room needs different times of day, describe lighting changes explicitly ("morning sunlight from side windows" vs. "afternoon indirect light through blinds").
- Include distinctive anchor elements (e.g., a specific whiteboard, a window view) so the AI maintains spatial consistency across clips.

### 3.3 Props (Close-Up/Insert Shots)

Generate props at **16:9** ratio for insert shots:

| Filename Convention | Example |
|---|---|
| `PROP-01.jpg` | Wall clock showing 08:00 |
| `PROP-02.jpg` | Stack of exam papers |
| `PROP-03.jpg` | Integrity pledge document |

### 3.4 Asset Catalog

Create a comprehensive catalog document (`data-properti.md`) listing every asset with:
- Filename, character/location name, visual description
- Which scenes it appears in
- Any special notes (e.g., filename quirks like spaces before extensions)

---

## Phase 4: Scene Prompt Engineering (Google Flow)

This is the core of the production. Each scene gets two prompts: an **Image Prompt** (to generate the keyframe) and a **Motion Prompt** (to animate it into video).

### 4.1 File Structure Per Act

Each act/adegan gets its own file (`adeganX.md`) with this mandatory structure:

```markdown
# ADEGAN [X]: [TITLE]
**Durasi Total**: [Start] – [End] ([X] detik)
**Setting**: [Location(s)]
**Karakter**: [Character list]
**Mode Google Flow**: *Ingredients to Video* (Multi-image Reference)

---

## Daftar Media yang Diunggah ke Google Flow (Adegan [X])

### A. Gambar Hasil Generate Per Scene (Frame Utama)
*(Lokasi file: `generated properti/Adegan/Adegan ([X])/`)*
1. `scene1.jpg` (Hasil Image Scene 1 — [Brief Description])
2. `scene2.jpg` (Hasil Image Scene 2 — [Brief Description])
[...]

### B. Foto Karakter Pendukung Konsistensi Wajah / Lipsync
*(Lokasi file: `generated properti/Karakter/`)*
1. `[Character] (1).jpg` (Dipakai di Scene [list])
[...]

---

#format-start

---
Scene 1
[... scene content ...]

#format-end
```

### 4.2 Scene Format (Mandatory Per Scene)

Every scene must follow this exact format:

```markdown
---
Scene [Number]
- Durasi Video: [4 / 6 / 8 / 10] detik
- Dialog: [Character - tone]: "Text..." OR Tidak ada (SFX: ...)
- Foto Referensi untuk Image Prompt: [List of raw reference files]
- Image Prompt:
\`\`\`
[Full image prompt text]
\`\`\`
- Foto Referensi untuk Motion/Google Flow: scene[N].jpg + [Character (1).jpg if face/dialog]
- Motion Prompt:
\`\`\`
[Full motion prompt text]
\`\`\`
```

### 4.3 Image Prompt Rules

Write all image prompts following these strict rules:

1. **Language**: Write in the user's target language (default: Bahasa Indonesia). This has proven more effective for culturally-specific scenes.
2. **Structure**: `[Realism keyword] [Ratio] [Shot type] [Scene description with character actions, clothing, expressions] [Reference instructions] [Technical specs] [Negative prompt]`
3. **Always specify**:
   - Photorealistic style and aspect ratio: `Foto fotorealistis 16:9`
   - Shot type with translation: `bidikan sedang (medium shot)`, `sudut lebar (wide shot)`, `bidikan close-up`
   - Camera lens: `lensa 35mm`, `lensa wide 24mm`, `lensa 85mm`
   - Lighting: `pencahayaan pagi alami`, `pencahayaan siang hari`
   - Explicit reference instructions: `Gunakan [Filename] untuk referensi wajah dan pakaian`
4. **Negative prompt** (always at end): `Negative prompt: kartun, animasi, ilustrasi, render 3D, CGI, tangan cacat, jari berlebih, wajah terdistorsi, buram, teks salah eja, watermark.`
5. **Ratio declaration**: Always end with `Rasio: 16:9.` before the negative prompt.

**Example Image Prompt:**
```
Foto fotorealistis 16:9 bidikan sedang (medium shot) Pak Doni, seorang dosen pria 
berusia 29 tahun dengan rambut ikal, kumis tipis rapi, mengenakan kemeja batik krem, 
berdiri di depan kelas sambil merentangkan tangan ramah. Gunakan Pak Doni (1).jpg 
untuk referensi wajah dan pakaian, serta LATAR-03C.jpg untuk ruang kelas. 
Fotorealistis, lensa 35mm, pencahayaan siang hari alami. Rasio: 16:9. 
Negative prompt: kartun, animasi, ilustrasi, render 3D, CGI, tangan cacat, 
jari berlebih, wajah terdistorsi, buram, watermark.
```

### 4.4 Motion Prompt Rules

Motion prompts control camera movement, character animation, and audio. They are the most critical prompts and require strict anti-hallucination controls.

#### Structure:
```
[Camera instruction]
[Character action and expression]
[Lipsync instruction if dialog]
Audio / Dialog: [Speaker - tone, vocal type]: "Dialog text"
  OR
Audio: [SFX description]. [Anti-hallucination block].
Negative prompt: [Forbidden elements]
```

#### A. Scenes WITH Dialog:
1. Describe camera movement and character action in target language.
2. Add: `Gerakan bibir sinkron alami dengan dialog Bahasa Indonesia (lipsync natural).`
3. Write dialog line: `Audio / Dialog: [Character - tone description, vocal type]: "Dialog text"`
4. Negative prompt MUST include: `suara bahasa Inggris, dialog bahasa asing, aksen asing, suara robotik, bibir tidak sinkron, distorsi wajah.`

**Example (with dialog):**
```
Kamera medium terkunci diam. Pak Doni tersenyum ramah, menggerakkan tangannya 
terbuka saat memberikan instruksi. Gerakan bibir sinkron alami dengan dialog 
Bahasa Indonesia (lipsync natural).
Audio / Dialog: [Pak Doni - nada santai dan ramah, vokal pria Indonesia]: 
"Silakan tiap kelompok diskusikan studi kasusnya ya."
Negative prompt: suara bahasa Inggris, dialog bahasa asing, berteriak, 
suara robotik, bibir tidak sinkron, gerakan tangan kaku.
```

#### B. Scenes WITHOUT Dialog (SFX/Ambient Only):
1. Describe camera movement and character action.
2. Describe the specific sound effect or ambience.
3. Add the **mandatory anti-hallucination block**: `Sama sekali TIDAK ADA dialog, TIDAK ADA percakapan suara manusia, TIDAK ADA ucapan bahasa Inggris.`
4. Negative prompt MUST include: `dialog suara manusia, ucapan bahasa Inggris, suara percakapan, berbicara ke kamera, berteriak.`

**Example (without dialog):**
```
Kamera makro terkunci rapat pada jam dinding. Jarum detik bergerak maju 
dua detakan halus.
Audio: Detak mekanis jarum jam yang ritmis dan jernih (tick... tock...). 
Sama sekali TIDAK ADA dialog, TIDAK ADA percakapan suara manusia, 
TIDAK ADA ucapan bahasa Inggris.
Negative prompt: dialog suara manusia, ucapan bahasa Inggris, suara percakapan, 
berbicara ke kamera, berteriak, kamera berguncang.
```

### 4.5 Anti-Hallucination Controls (Critical)

Google Flow (Omniflash) is prone to hallucinating English speech in generated videos. These controls are **mandatory**:

| Scenario | Required Control |
|---|---|
| Scene has dialog | Negative prompt bans English speech, foreign accents, robotic voice |
| Scene is silent | Explicit declaration: "TIDAK ADA dialog, TIDAK ADA ucapan bahasa Inggris" |
| Scene has VO | Specify voiceover language and speaker explicitly |
| Any scene | Negative prompt block is always the last line in motion prompt |
| Specific English words to ban | Include the literal English phrase in negative prompt (e.g., `"thank you"`, `"good morning"`) |

### 4.6 Duration Guidelines

| Duration | Best For | Dialog Length |
|---|---|---|
| **4 detik** | Quick reactions, cutaways, transitions, insert shots | 0–8 words max |
| **6 detik** | Short dialog (1 sentence), establishing shots, single actions | 10–15 words |
| **8 detik** | Two-way dialog, longer speeches, tracking shots | 15–20 words |
| **10 detik** | Extended speeches, complex multi-character scenes | 20–25 words |

---

## Phase 5: Production Execution

### 5.1 Image Generation Workflow (Google Gemini)

For each scene, in order:
1. Open Google Gemini
2. Upload the reference photos listed in "Foto Referensi untuk Image Prompt"
3. Paste the Image Prompt
4. Generate and review the image
5. Save as `scene[N].jpg` in the act's folder: `generated properti/Adegan/Adegan ([X])/`
6. If the result is unsatisfactory, regenerate with adjusted prompt

### 5.2 Video Generation Workflow (Google Flow)

For each scene, in order:
1. Open Google Flow
2. Select mode: **Ingredients to Video**
3. Upload ingredients:
   - The generated keyframe: `scene[N].jpg`
   - Character face reference: `[Character] (1).jpg` (if the scene has a face or dialog)
   - Additional references as listed in "Foto Referensi untuk Motion/Google Flow"
4. Set duration to match the scene specification
5. Paste the Motion Prompt
6. Generate and review the video clip
7. Download and save

### 5.3 Post-Production Assembly

1. Import all generated clips into video editor in scene order
2. Add transition cards (Scene X — text cards) between acts
3. Add background music and sound effects where noted
4. Add any text overlays that the AI couldn't generate reliably
5. Color-grade for consistency across clips
6. Export final video

---

## Phase 6: File Organization

### Recommended Folder Structure

```
project-root/
├── konteks-skenario.md          # Scenario / script
├── storyboard.md                # Shot-by-shot storyboard
├── data-properti.md             # Asset catalog + SOP rules
├── pra-prompt-properti.md       # Pre-production checklist
├── flow-scenes/
│   ├── adegan1.md               # Scene prompts per act
│   ├── adegan2.md
│   └── ...
├── generated properti/
│   ├── Karakter/                # Character reference images
│   │   ├── [Name] (1).jpg      # Portrait
│   │   ├── [Name] (2).jpg      # Turnaround
│   │   ├── LATAR-01.jpg        # Background sets
│   │   ├── PROP-01.jpg         # Props
│   │   └── ...
│   └── Adegan/
│       ├── Adegan (1)/          # Generated keyframes per act
│       │   ├── scene1.jpg
│       │   ├── scene2.jpg
│       │   └── ...
│       ├── Adegan (2)/
│       └── ...
└── properti/                    # Real reference photos (logos, real people)
```

---

## Quick Reference: Prompt Checklist

Before submitting any prompt, verify:

### Image Prompt ✓
- [ ] Written in target language (Bahasa Indonesia)
- [ ] Starts with `Foto fotorealistis 16:9`
- [ ] Shot type specified (wide/medium/close-up)
- [ ] Camera lens specified (24mm/35mm/50mm/85mm)
- [ ] Lighting described
- [ ] All reference photos mentioned by exact filename
- [ ] Ends with `Rasio: 16:9.`
- [ ] Negative prompt present as last line

### Motion Prompt ✓
- [ ] Camera movement described (locked/tracking/push-in/etc.)
- [ ] Character actions described clearly
- [ ] If dialog: lipsync instruction included
- [ ] If dialog: `Audio / Dialog:` line with speaker, tone, and vocal type
- [ ] If silent: explicit "TIDAK ADA dialog" declaration
- [ ] Negative prompt present as last line
- [ ] Anti-English-hallucination controls in negative prompt

---

## Common Pitfalls & Solutions

| Problem | Cause | Solution |
|---|---|---|
| AI generates English speech in silent scenes | Missing anti-hallucination block | Always add "TIDAK ADA dialog, TIDAK ADA ucapan bahasa Inggris" |
| Character face changes between clips | No face reference uploaded | Always upload `[Character] (1).jpg` as ingredient |
| Setting jumps feel jarring | Missing transition scenes | Add bell/clock + character walking shots between locations |
| Dialog too fast/slow | Word count doesn't match duration | Follow the 2–2.5 words/second rule |
| Text in images is misspelled | AI struggles with text generation | Add text in post-production editing instead |
| Hands/fingers look deformed | Common AI artifact | Include "tangan cacat, jari berlebih" in every negative prompt |
| Character clothing changes | Inconsistent prompt description | Always reference the turnaround image `(2).jpg` for clothing |
| Filename not found | Spaces or special chars in filename | Double-check exact filenames including spaces (e.g., `LATAR-03A .jpg`) |

---

## Adapting This Workflow to New Projects

To use this skill for a different video project:

1. **Replace the scenario**: Write a new `konteks-skenario.md` with your characters, settings, and plot.
2. **Create new storyboard**: Follow the storyboard format in Phase 2 with your content.
3. **Generate new assets**: Design characters, backgrounds, and props following Phase 3 conventions.
4. **Create the asset catalog**: Document all assets in `data-properti.md`.
5. **Write scene prompts**: Follow Phase 4 format exactly — the prompt structure, anti-hallucination controls, and negative prompts are universal.
6. **Execute**: Follow Phase 5 for generation and assembly.

The **prompt engineering rules** (Phase 4) and **anti-hallucination controls** (§4.5) are universal and should be applied identically regardless of the project's content.

---
---

# 🇮🇩 VERSI BAHASA INDONESIA

---

# Produksi Video AI

Bertindaklah sebagai sutradara film AI profesional dan prompt engineer yang mengkhususkan diri dalam pembuatan film pendek realistis berbasis AI (5–10 menit) menggunakan Google Gemini (generasi gambar) dan Google Flow/Omniflash (generasi video). Anda memandu pengguna melalui alur kerja terstruktur yang telah terbukti menghasilkan output konsisten dan berkualitas tinggi.

## Gambaran Umum

Skill ini mencakup produksi konten video realistis berbasis AI di mana setiap visual — karakter, latar belakang, properti — di-generate oleh AI lalu dianimasikan menjadi klip video menggunakan mode "Ingredients to Video" di Google Flow. Output akhir berupa rangkaian klip video pendek (4–10 detik per klip) yang dirangkai berurutan menjadi satu narasi utuh.

### Alat yang Digunakan
- **Google Gemini**: Generasi gambar (karakter, latar belakang, properti)
- **Google Flow (Omniflash)**: Generasi video dari foto referensi + motion prompt
- **Editor Video** (mis. CapCut, DaVinci Resolve): Penyusunan akhir dan pasca-produksi

---

## Fase 1: Perencanaan Pra-Produksi

Sebelum menulis prompt apapun, bangun fondasi kreatif secara menyeluruh.

### 1.1 Tentukan Brief Proyek

Kumpulkan informasi berikut dari pengguna:

| Item | Deskripsi | Contoh |
|---|---|---|
| **Judul** | Judul kerja video | "Cermin Sang Teladan" |
| **Durasi** | Target durasi total | 5–7 menit |
| **Genre/Gaya** | Gaya visual dan tone | Fotorealistis, drama kampus |
| **Rasio Aspek** | Format video | 16:9 |
| **Bahasa** | Bahasa semua dialog | Bahasa Indonesia |
| **Karakter** | Daftar karakter dengan usia, peran, dan deskripsi visual | Lihat §2 |
| **Setting** | Daftar lokasi/set yang dibutuhkan | Ruang kelas, koridor, kantor dosen |
| **Pesan Inti** | Apa yang ingin disampaikan video | Etika, profesionalisme |

### 1.2 Ajukan Pertanyaan Klarifikasi

Selalu tanyakan hal-hal ini sebelum melanjutkan:

1. **Durasi Klip**: Berapa durasi yang didukung alat video? (mis. 4, 6, 8, 10 detik)
2. **Mode Generasi**: "Frames to Video" atau "Ingredients to Video"?
3. **Kemampuan Audio**: Apakah alat bisa menghasilkan dialog audio langsung, atau audio direkam terpisah?
4. **Foto Referensi**: Apakah pengguna punya foto asli (orang, bangunan, logo) sebagai acuan?
5. **Sensitivitas Konten**: Adakah adegan yang mungkin ditolak filter konten AI? Siapkan alternatif.
6. **Teks dalam Gambar**: Apakah AI bisa menghasilkan teks dengan akurat dalam bahasa target, atau teks ditambahkan saat editing?

### 1.3 Tulis Skenario

Buat dokumen skenario terstruktur berisi:
- Daftar karakter beserta peran dan deskripsi
- Breakdown timeline per babak/adegan
- Dialog inti per adegan
- Pesan etika/tematik per adegan (jika berlaku)

---

## Fase 2: Storyboard

### 2.1 Struktur Storyboard

Buat storyboard detail per-shot dalam format tabel:

```markdown
## Adegan [X] — [Judul]
**Karakter:** [Daftar] · **Setting:** [Lokasi]

| Shot | Durasi | Kamera | Visual / Aksi | Dialog / Audio |
|---|---|---|---|---|
| X.1 | 6 dtk | Wide establishing | [Deskripsi] | [Dialog atau SFX] |
| X.2 | 8 dtk | Medium close-up | [Deskripsi] | [Dialog] |
```

### 2.2 Aturan Storyboard

- **Durasi per klip**: Gunakan hanya durasi yang didukung alat video (mis. 4, 6, 8, atau 10 detik).
- **Pacing dialog**: Sekitar 2–2,5 kata per detik untuk bicara natural. Klip 6 detik sebaiknya tidak lebih dari ~15 kata dialog.
- **Variasi shot**: Selang-seling antara wide, medium, dan close-up untuk menjaga ketertarikan visual.
- **Kartu transisi**: Akhiri setiap babak dengan kartu teks berisi pesan tematik (bisa di-generate sebagai gambar diam).
- **Kontinuitas naratif**: Jika sebuah adegan berpindah setting (mis. ruang kelas → ruang dosen), tambahkan shot transisi (bel berbunyi, karakter berjalan di koridor) agar cerita mengalir logis. Jangan pernah melakukan jump-cut antar lokasi tanpa justifikasi visual.

### 2.3 Tabel Ringkasan Durasi

Sertakan tabel ringkasan di bagian atas storyboard:

```markdown
| Adegan | Judul | Waktu | Durasi | Jumlah Shot |
|---|---|---|---|---|
| 1 | [Judul] | 00:00 – 01:00 | 60 dtk | 10 |
| 2 | [Judul] | 01:00 – 02:00 | 60 dtk | 11 |
```

---

## Fase 3: Generasi Aset (Google Gemini)

### 3.1 Desain Karakter

Setiap karakter membutuhkan **dua gambar referensi** yang di-generate di Gemini:

| Tipe | Konvensi Nama File | Rasio | Konten |
|---|---|---|---|
| **Potret** | `[Nama] (1).jpg` | 3:4 | Potret depan kepala sampai pinggang. Wajah, ekspresi, detail pakaian. |
| **Turnaround** | `[Nama] (2).jpg` | 11:6 (2816×1536) | Full body di atas latar putih. 3 panel: Depan / Samping / Belakang. |

**Potret (1)** digunakan untuk face-locking dan referensi lipsync di Google Flow.
**Turnaround (2)** digunakan untuk konsistensi proporsi tubuh, postur, dan pakaian.

Untuk **figuran/kelompok ekstra**, cukup satu potret kelompok: `[Nama Kelompok].jpg`

Untuk **orang asli** (bukan AI-generated), gunakan foto asli mereka. Catat dengan jelas di katalog aset.

### 3.2 Desain Latar Belakang / Set

Generate latar belakang lokasi dengan rasio **16:9** bergaya arsitektur fotorealistis:

| Konvensi Nama File | Deskripsi |
|---|---|
| `LATAR-01.jpg` | Eksterior bangunan |
| `LATAR-02.jpg` | Koridor |
| `LATAR-03A.jpg` | Ruang kelas (sudut A) |
| `LATAR-03B.jpg` | Ruang kelas (sudut B) |

**Tips untuk konsistensi:**
- Generate semua latar belakang untuk lokasi yang sama dalam satu sesi agar gaya arsitektur tetap konsisten.
- Jika ruangan yang sama perlu variasi waktu (pagi/siang), deskripsikan perubahan pencahayaan secara eksplisit ("sinar matahari pagi dari jendela samping" vs. "cahaya siang tidak langsung melalui tirai").
- Sertakan elemen jangkar yang khas (mis. papan tulis tertentu, pemandangan jendela) agar AI menjaga konsistensi spasial antar klip.

### 3.3 Properti (Close-Up / Insert Shot)

Generate properti dengan rasio **16:9** untuk insert shot:

| Konvensi Nama File | Contoh |
|---|---|
| `PROP-01.jpg` | Jam dinding menunjukkan 08:00 |
| `PROP-02.jpg` | Tumpukan kertas ujian |
| `PROP-03.jpg` | Dokumen Pakta Integritas |

### 3.4 Katalog Aset

Buat dokumen katalog komprehensif (`data-properti.md`) yang mendaftar setiap aset dengan:
- Nama file, nama karakter/lokasi, deskripsi visual
- Scene mana saja yang menggunakannya
- Catatan khusus (mis. keunikan nama file seperti spasi sebelum ekstensi)

---

## Fase 4: Teknik Penulisan Prompt Scene (Google Flow)

Ini adalah inti produksi. Setiap scene mendapat dua prompt: **Image Prompt** (untuk generate keyframe) dan **Motion Prompt** (untuk menganimasikannya menjadi video).

### 4.1 Struktur File Per Adegan

Setiap adegan mendapat file sendiri (`adeganX.md`) dengan struktur wajib berikut:

```markdown
# ADEGAN [X]: [JUDUL]
**Durasi Total**: [Mulai] – [Selesai] ([X] detik)
**Setting**: [Lokasi]
**Karakter**: [Daftar karakter]
**Mode Google Flow**: *Ingredients to Video* (Multi-image Reference)

---

## Daftar Media yang Diunggah ke Google Flow (Adegan [X])

### A. Gambar Hasil Generate Per Scene (Frame Utama)
*(Lokasi file: `generated properti/Adegan/Adegan ([X])/`)*
1. `scene1.jpg` (Hasil Image Scene 1 — [Deskripsi Singkat])
2. `scene2.jpg` (Hasil Image Scene 2 — [Deskripsi Singkat])
[...]

### B. Foto Karakter Pendukung Konsistensi Wajah / Lipsync
*(Lokasi file: `generated properti/Karakter/`)*
1. `[Karakter] (1).jpg` (Dipakai di Scene [daftar])
[...]

---

#format-start

---
Scene 1
[... konten scene ...]

#format-end
```

### 4.2 Format Scene (Wajib Per Scene)

Setiap scene harus mengikuti format persis ini:

```markdown
---
Scene [Nomor]
- Durasi Video: [4 / 6 / 8 / 10] detik
- Dialog: [Karakter - nada]: "Teks..." ATAU Tidak ada (SFX: ...)
- Foto Referensi untuk Image Prompt: [Daftar file referensi]
- Image Prompt:
\`\`\`
[Teks image prompt lengkap]
\`\`\`
- Foto Referensi untuk Motion/Google Flow: scene[N].jpg + [Karakter (1).jpg jika ada wajah/dialog]
- Motion Prompt:
\`\`\`
[Teks motion prompt lengkap]
\`\`\`
```

### 4.3 Aturan Image Prompt

Tulis semua image prompt mengikuti aturan ketat berikut:

1. **Bahasa**: Wajib ditulis dalam Bahasa Indonesia. Ini terbukti lebih efektif untuk scene yang spesifik secara budaya.
2. **Struktur**: `[Kata kunci realisme] [Rasio] [Tipe shot] [Deskripsi scene dengan aksi karakter, pakaian, ekspresi] [Instruksi referensi] [Spesifikasi teknis] [Negative prompt]`
3. **Selalu cantumkan**:
   - Gaya fotorealistis dan rasio: `Foto fotorealistis 16:9`
   - Tipe shot dengan terjemahan: `bidikan sedang (medium shot)`, `sudut lebar (wide shot)`, `bidikan close-up`
   - Lensa kamera: `lensa 35mm`, `lensa wide 24mm`, `lensa 85mm`
   - Pencahayaan: `pencahayaan pagi alami`, `pencahayaan siang hari`
   - Instruksi referensi eksplisit: `Gunakan [NamaFile] untuk referensi wajah dan pakaian`
4. **Negative prompt** (selalu di akhir): `Negative prompt: kartun, animasi, ilustrasi, render 3D, CGI, tangan cacat, jari berlebih, wajah terdistorsi, buram, teks salah eja, watermark.`
5. **Deklarasi rasio**: Selalu akhiri dengan `Rasio: 16:9.` sebelum negative prompt.

**Contoh Image Prompt:**
```
Foto fotorealistis 16:9 bidikan sedang (medium shot) Pak Doni, seorang dosen pria 
berusia 29 tahun dengan rambut ikal, kumis tipis rapi, mengenakan kemeja batik krem, 
berdiri di depan kelas sambil merentangkan tangan ramah. Gunakan Pak Doni (1).jpg 
untuk referensi wajah dan pakaian, serta LATAR-03C.jpg untuk ruang kelas. 
Fotorealistis, lensa 35mm, pencahayaan siang hari alami. Rasio: 16:9. 
Negative prompt: kartun, animasi, ilustrasi, render 3D, CGI, tangan cacat, 
jari berlebih, wajah terdistorsi, buram, watermark.
```

### 4.4 Aturan Motion Prompt

Motion prompt mengontrol gerakan kamera, animasi karakter, dan audio. Ini adalah prompt paling kritis dan memerlukan kontrol anti-halusinasi yang ketat.

#### Struktur:
```
[Instruksi kamera]
[Aksi dan ekspresi karakter]
[Instruksi lipsync jika ada dialog]
Audio / Dialog: [Pembicara - nada, tipe vokal]: "Teks dialog"
  ATAU
Audio: [Deskripsi SFX]. [Blok anti-halusinasi].
Negative prompt: [Elemen yang dilarang]
```

#### A. Scene DENGAN Dialog:
1. Deskripsikan gerakan kamera dan aksi karakter dalam Bahasa Indonesia.
2. Tambahkan: `Gerakan bibir sinkron alami dengan dialog Bahasa Indonesia (lipsync natural).`
3. Tulis baris dialog: `Audio / Dialog: [Karakter - deskripsi nada, tipe vokal]: "Teks dialog"`
4. Negative prompt WAJIB mencakup: `suara bahasa Inggris, dialog bahasa asing, aksen asing, suara robotik, bibir tidak sinkron, distorsi wajah.`

**Contoh (dengan dialog):**
```
Kamera medium terkunci diam. Pak Doni tersenyum ramah, menggerakkan tangannya 
terbuka saat memberikan instruksi. Gerakan bibir sinkron alami dengan dialog 
Bahasa Indonesia (lipsync natural).
Audio / Dialog: [Pak Doni - nada santai dan ramah, vokal pria Indonesia]: 
"Silakan tiap kelompok diskusikan studi kasusnya ya."
Negative prompt: suara bahasa Inggris, dialog bahasa asing, berteriak, 
suara robotik, bibir tidak sinkron, gerakan tangan kaku.
```

#### B. Scene TANPA Dialog (Hanya SFX/Ambiens):
1. Deskripsikan gerakan kamera dan aksi karakter.
2. Deskripsikan efek suara atau ambiens secara spesifik.
3. Tambahkan **blok anti-halusinasi wajib**: `Sama sekali TIDAK ADA dialog, TIDAK ADA percakapan suara manusia, TIDAK ADA ucapan bahasa Inggris.`
4. Negative prompt WAJIB mencakup: `dialog suara manusia, ucapan bahasa Inggris, suara percakapan, berbicara ke kamera, berteriak.`

**Contoh (tanpa dialog):**
```
Kamera makro terkunci rapat pada jam dinding. Jarum detik bergerak maju 
dua detakan halus.
Audio: Detak mekanis jarum jam yang ritmis dan jernih (tick... tock...). 
Sama sekali TIDAK ADA dialog, TIDAK ADA percakapan suara manusia, 
TIDAK ADA ucapan bahasa Inggris.
Negative prompt: dialog suara manusia, ucapan bahasa Inggris, suara percakapan, 
berbicara ke kamera, berteriak, kamera berguncang.
```

### 4.5 Kontrol Anti-Halusinasi (Kritikal)

Google Flow (Omniflash) cenderung berhalusinasi menghasilkan ucapan bahasa Inggris dalam video. Kontrol berikut **wajib** diterapkan:

| Skenario | Kontrol yang Diperlukan |
|---|---|
| Scene ada dialog | Negative prompt melarang ucapan bahasa Inggris, aksen asing, suara robotik |
| Scene sunyi/diam | Deklarasi eksplisit: "TIDAK ADA dialog, TIDAK ADA ucapan bahasa Inggris" |
| Scene ada Voice Over | Sebutkan bahasa VO dan pembicara secara eksplisit |
| Semua scene | Blok negative prompt selalu menjadi baris terakhir di motion prompt |
| Kata Inggris spesifik yang dilarang | Cantumkan frasa Inggris literal di negative prompt (mis. `"thank you"`, `"good morning"`) |

### 4.6 Panduan Durasi

| Durasi | Cocok Untuk | Panjang Dialog |
|---|---|---|
| **4 detik** | Reaksi cepat, cutaway, transisi, insert shot | 0–8 kata maks |
| **6 detik** | Dialog pendek (1 kalimat), establishing shot, aksi tunggal | 10–15 kata |
| **8 detik** | Dialog dua arah, pidato lebih panjang, tracking shot | 15–20 kata |
| **10 detik** | Pidato panjang, scene multi-karakter yang kompleks | 20–25 kata |

---

## Fase 5: Eksekusi Produksi

### 5.1 Alur Kerja Generasi Gambar (Google Gemini)

Untuk setiap scene, secara berurutan:
1. Buka Google Gemini
2. Unggah foto referensi yang tercantum di "Foto Referensi untuk Image Prompt"
3. Paste Image Prompt
4. Generate dan periksa hasilnya
5. Simpan sebagai `scene[N].jpg` di folder adegan: `generated properti/Adegan/Adegan ([X])/`
6. Jika hasilnya kurang memuaskan, generate ulang dengan prompt yang disesuaikan

### 5.2 Alur Kerja Generasi Video (Google Flow)

Untuk setiap scene, secara berurutan:
1. Buka Google Flow
2. Pilih mode: **Ingredients to Video**
3. Unggah bahan (ingredients):
   - Keyframe yang sudah di-generate: `scene[N].jpg`
   - Referensi wajah karakter: `[Karakter] (1).jpg` (jika scene ada wajah atau dialog)
   - Referensi tambahan sesuai daftar di "Foto Referensi untuk Motion/Google Flow"
4. Atur durasi sesuai spesifikasi scene
5. Paste Motion Prompt
6. Generate dan periksa klip video
7. Unduh dan simpan

### 5.3 Perakitan Pasca-Produksi

1. Impor semua klip yang di-generate ke editor video sesuai urutan scene
2. Tambahkan kartu transisi (kartu teks bertema) di antara adegan
3. Tambahkan musik latar dan efek suara sesuai catatan
4. Tambahkan overlay teks yang tidak bisa di-generate AI dengan akurat
5. Sesuaikan warna (color-grade) untuk konsistensi antar klip
6. Ekspor video final

---

## Fase 6: Organisasi File

### Struktur Folder yang Direkomendasikan

```
root-proyek/
├── konteks-skenario.md          # Skenario / naskah
├── storyboard.md                # Storyboard per-shot
├── data-properti.md             # Katalog aset + aturan SOP
├── pra-prompt-properti.md       # Checklist pra-produksi
├── flow-scenes/
│   ├── adegan1.md               # Prompt scene per adegan
│   ├── adegan2.md
│   └── ...
├── generated properti/
│   ├── Karakter/                # Gambar referensi karakter
│   │   ├── [Nama] (1).jpg      # Potret
│   │   ├── [Nama] (2).jpg      # Turnaround
│   │   ├── LATAR-01.jpg        # Set latar belakang
│   │   ├── PROP-01.jpg         # Properti
│   │   └── ...
│   └── Adegan/
│       ├── Adegan (1)/          # Keyframe yang di-generate per adegan
│       │   ├── scene1.jpg
│       │   ├── scene2.jpg
│       │   └── ...
│       ├── Adegan (2)/
│       └── ...
└── properti/                    # Foto referensi asli (logo, orang asli)
```

---

## Referensi Cepat: Checklist Prompt

Sebelum mengirim prompt apapun, verifikasi:

### Image Prompt ✓
- [ ] Ditulis dalam Bahasa Indonesia
- [ ] Diawali dengan `Foto fotorealistis 16:9`
- [ ] Tipe shot disebutkan (wide/medium/close-up)
- [ ] Lensa kamera disebutkan (24mm/35mm/50mm/85mm)
- [ ] Pencahayaan dideskripsikan
- [ ] Semua foto referensi disebutkan dengan nama file persis
- [ ] Diakhiri dengan `Rasio: 16:9.`
- [ ] Negative prompt ada di baris terakhir

### Motion Prompt ✓
- [ ] Gerakan kamera dideskripsikan (locked/tracking/push-in/dll.)
- [ ] Aksi karakter dideskripsikan dengan jelas
- [ ] Jika ada dialog: instruksi lipsync disertakan
- [ ] Jika ada dialog: baris `Audio / Dialog:` dengan pembicara, nada, dan tipe vokal
- [ ] Jika sunyi: deklarasi eksplisit "TIDAK ADA dialog"
- [ ] Negative prompt ada di baris terakhir
- [ ] Kontrol anti-halusinasi bahasa Inggris di negative prompt

---

## Kesalahan Umum & Solusi

| Masalah | Penyebab | Solusi |
|---|---|---|
| AI menghasilkan ucapan Inggris di scene diam | Blok anti-halusinasi tidak ada | Selalu tambahkan "TIDAK ADA dialog, TIDAK ADA ucapan bahasa Inggris" |
| Wajah karakter berubah antar klip | Tidak ada referensi wajah yang diunggah | Selalu unggah `[Karakter] (1).jpg` sebagai bahan |
| Perpindahan setting terasa janggal | Scene transisi tidak ada | Tambahkan shot bel/jam + karakter berjalan di koridor |
| Dialog terlalu cepat/lambat | Jumlah kata tidak sesuai durasi | Ikuti aturan 2–2,5 kata/detik |
| Teks di gambar salah eja | AI kesulitan menghasilkan teks akurat | Tambahkan teks saat editing pasca-produksi |
| Tangan/jari terlihat cacat | Artefak umum AI | Sertakan "tangan cacat, jari berlebih" di setiap negative prompt |
| Pakaian karakter berubah | Deskripsi prompt tidak konsisten | Selalu referensikan gambar turnaround `(2).jpg` untuk pakaian |
| File tidak ditemukan | Spasi atau karakter khusus di nama file | Periksa nama file persis termasuk spasi (mis. `LATAR-03A .jpg`) |

---

## Mengadaptasi Alur Kerja Ini untuk Proyek Baru

Untuk menggunakan skill ini pada proyek video yang berbeda:

1. **Ganti skenario**: Tulis `konteks-skenario.md` baru dengan karakter, setting, dan plot Anda.
2. **Buat storyboard baru**: Ikuti format storyboard di Fase 2 dengan konten Anda.
3. **Generate aset baru**: Desain karakter, latar belakang, dan properti mengikuti konvensi Fase 3.
4. **Buat katalog aset**: Dokumentasikan semua aset di `data-properti.md`.
5. **Tulis prompt scene**: Ikuti format Fase 4 persis — struktur prompt, kontrol anti-halusinasi, dan negative prompt bersifat universal.
6. **Eksekusi**: Ikuti Fase 5 untuk generasi dan perakitan.

**Aturan prompt engineering** (Fase 4) dan **kontrol anti-halusinasi** (§4.5) bersifat **universal** dan harus diterapkan secara identik terlepas dari konten proyeknya.
