# PROMPT LATAR BELAKANG & PROPERTI (GOOGLE GEMINI)

Semua prompt menggunakan rasio **16:9** (sesuai spesifikasi video akhir), gaya **fotorealistis arsitektur / interior kampus**, dan pencahayaan alami.

---

## Ringkasan Latar yang Dibutuhkan

| No | Kode Latar | Lokasi | Pencahayaan & Sudut | Adegan Terkait |
|---|---|---|---|---|
| 1 | `LATAR-01` | Eksterior Gedung USK | Pagi hari cerah, sudut pandang mata / sedikit low-angle | Adegan 1 (Shot 1.1) |
| 2 | `LATAR-02` | Koridor Kampus | Pagi hari, koridor lantai atas dengan pencahayaan jendela samping | Adegan 1, 4 (Shot 1.2, 1.3, 4.2) |
| 3 | `LATAR-03A` | Ruang Kelas - Angle Depan | Pagi hari, menghadap papan tulis & proyektor | Adegan 1, 5, 6 |
| 4 | `LATAR-03B` | Ruang Kelas - Angle Belakang | Pagi hari, dari barisan belakang menghadap podium dosen | Adegan 1, 5 |
| 5 | `LATAR-03C` | Ruang Kelas - Format Diskusi | Siang hari, meja mahasiswa berkelompok | Adegan 2 (Shot 2.1, 2.4) |
| 6 | `LATAR-04` | Ruang Kuliah Ber-AC | Siang hari, interior kelas ber-AC dengan tanda "DILARANG MEROKOK" | Adegan 3 (Shot 3.1, 3.3) |
| 7 | `LATAR-05` | Ruang Kerja Pak Hendra | Siang hari, meja kerja dosen penuh tumpukan kertas & berkas UTS | Adegan 4 (Shot 4.3, 4.4, 4.11) |
| 8 | `LATAR-06` | Ruang Dosen Bersama | Pagi menjelang siang, meja kerja formal & sudut bimbingan rapi | Adegan 6 (Shot 6.4, 6.8, 6.11) |
| 9 | `LATAR-07` | Ruang Lokakarya PEKERTI | Aula/ruang rapat pelatihan dosen, meja U-shape, spanduk resmi | Adegan 7 (Shot 7.1, 7.6) |

---

## 1. Eksterior Gedung Kampus USK (`LATAR-01`)
*Gunakan attachment: Foto asli gedung fakultas/LPM USK yang sudah Anda miliki.*

```
Use the attached photograph of the university building as the primary architectural and color reference. Photorealistic architectural photograph of Universitas Syiah Kuala (USK) faculty building in Banda Aceh, Indonesia. Exterior wide shot during a bright clear morning at 8:00 AM, soft morning sunlight casting gentle diagonal shadows. Modern Indonesian tropical campus architecture with neat tropical landscaping, manicured green grass lawn, palm trees, and clean paved pedestrian pathway leading to the main entrance. No people visible, serene academic atmosphere, clear blue tropical sky with light wispy clouds. Shot on 24mm architectural lens, crisp sharp focus, natural colors, high dynamic range. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, CGI, people, crowded, dark, overcast, rain, distorted building lines, blurry, watermark, low resolution.
```

---

## 2. Koridor Kampus (`LATAR-02`)

```
Photorealistic interior photograph of an Indonesian university academic building hallway and corridor at Universitas Syiah Kuala. Morning sunlight streaming in through large glass windows on the side, clean polished terrazzo tiled floor reflecting the morning light, neatly painted white and cream walls, wooden classroom doors with room number signs along the corridor, ceiling-mounted fluorescent lights turned on. Empty corridor, deep one-point perspective down the hallway, modern, clean, organized academic environment. Shot on 35mm lens, realistic depth of field, natural lighting, high dynamic range. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, dark, dirty, abandoned, derelict, people, messy, distorted perspective, motion blur, watermark.
```

---

## 3. Ruang Kelas — Pagi Hari (`LATAR-03A` & `LATAR-03B`)

### Angle Depan (Menghadap Papan Tulis & Layar Proyektor) — `LATAR-03A`
```
Photorealistic interior photograph of a modern Indonesian university classroom at Universitas Syiah Kuala, view facing the front lecture area. Wide shot showing a clean lecturer's wooden desk and podium on the side, a large white magnetic whiteboard, an overhead motorized projector screen displaying a lecture slide, and an AC unit mounted high on the wall. Large windows on the left with sheer blinds letting in bright morning daylight, clean tiled floor, neat and spacious layout, empty room with no students. Shot on 28mm wide-angle lens, sharp focus, natural daylight balanced with soft interior lighting. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, people, crowded, dark, messy, dirty, cluttered, distorted lines, watermark.
```

### Angle Belakang (Sudut Pandang dari Kursi Mahasiswa ke Depan) — `LATAR-03B`
```
Photorealistic interior photograph of a university classroom, eye-level perspective from the back row looking forward towards the lecturer podium and whiteboard. In the foreground are rows of neatly arranged student wooden-topped desks and chairs. In the background, the front lecture area with a large whiteboard, projector screen, and lecturer desk are visible. Bright morning light entering from tall side windows. Empty classroom, calm and quiet atmosphere before lecture starts. Shot on 50mm lens, shallow depth of field with foreground desk in subtle soft focus and front room in sharp focus. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, people, clutter, messy, trash on floor, distorted geometry, watermark.
```

---

## 4. Ruang Kelas — Format Diskusi Siang Hari (`LATAR-03C`)

```
Photorealistic interior photograph of a university classroom arranged for collaborative group study and seminar discussions. Midday lighting with natural light filtered through blinds. The student desks are grouped together into small collaborative clusters (pods of 4-5 chairs facing each other). On the front wall is a whiteboard with dry-erase marker notes and a digital clock. Empty classroom setting, neat and ready for group workshop. Shot on 35mm lens, natural midday interior lighting, realistic textures of wood, metal, and floor tiles. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, people, dark, chaotic, broken furniture, blurry, low resolution, watermark.
```

---

## 5. Ruang Kuliah Ber-AC dengan Tanda Dilarang Merokok (`LATAR-04`)

```
Photorealistic interior photograph of an air-conditioned university lecture hall classroom. On the clean off-white wall, a modern split-unit wall-mounted air conditioner is visibly on with a subtle cool air indicator. Directly below the AC unit mounted on the wall is an official, clear sign with an international red circular no-smoking prohibition symbol and prominent bold text reading: "DILARANG MEROKOK / NO SMOKING". In the background, classroom desks and lecture podium are visible under soft cool-white indoor lighting, clean windows with closed blinds. Empty room, crisp architectural details. Shot on 35mm lens, sharp detail on the wall sign and AC unit. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, people, smoke, fire, messy room, spelling errors, distorted circle symbol, blurry, watermark.
```

---

## 6. Ruang Kerja Dosen Pak Hendra — Penuh Berkas (`LATAR-05`)

```
Photorealistic interior photograph of an Indonesian male lecturer's private academic office room at Universitas Syiah Kuala. Midday interior lighting. In the center is a wooden office desk heavily cluttered with tall, disheveled stacks of printed student exam papers, manila grading folders, red grading pens, an open laptop displaying an academic portal, and a ceramic coffee mug. Bookcases lining the wall behind are packed with textbooks, university binders, and academic journals. On the wall hangs a small academic calendar and certificates. Empty chair behind the desk, authentic lived-in faculty office atmosphere. Shot on 35mm lens, rich detail, natural lighting. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, completely clean empty desk, people, futuristic room, messy trash, extreme dirt, dark room, blurry, watermark.
```

---

## 7. Ruang Kerja Dosen Bersama & Bimbingan (`LATAR-06`)

```
Photorealistic interior photograph of a respectable Indonesian university faculty shared consultation office at Universitas Syiah Kuala. Bright and neat morning atmosphere. Two orderly wooden lecturer workstations with desktop monitors, neat book stacks, stationery organizers, and an adjoining small meeting table with two guest chairs for student thesis consultations. Warm academic aesthetic with wooden bookshelves, framed academic credentials on white walls, and a large window looking out onto campus greenery. Empty room, professional and welcoming environment. Shot on 28mm wide lens, balanced daylight and soft warm ceiling lights. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, chaotic clutter, trash, dark, dreary, people, distorted furniture, blurry, watermark.
```

---

## 8. Ruang Lokakarya PEKERTI USK (`LATAR-07`)
*Gunakan attachment: Logo USK dan Logo LPM USK.*

```
Use the attached USK logo and LPM logo as exact reference for the institutional emblems. Photorealistic interior photograph of an Indonesian university training seminar hall prepared for the PEKERTI workshop at Universitas Syiah Kuala (USK), Banda Aceh. Wide shot of the room featuring a formal U-shaped or classroom-style long conference tables with dark table skirts, matching conference chairs, microphones, bottled water, and notepad folders placed neatly at each seat. At the front wall hangs a large professional backdrop banner with the USK and LPM logos in the corners, prominent clean typography reading: "LOKAKARYA PEKERTI - LPM UNIVERSITAS SYIAH KUALA". Professional conference room lighting, clean acoustic ceiling panels, polished floor, dignified and inspiring atmosphere, empty room ready for participants. Shot on 24mm wide-angle lens, sharp focus, vibrant yet natural colors. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, people, distorted logo, illegible text gibberish, messy tables, dark room, blurry, watermark.
```

---

## 9. Properti Close-Up / Insert Shots Tambahan

### A. Kalender Akademik "MINGGU TENANG" (`PROP-01`)
```
Photorealistic close-up macro photograph of a university wall calendar and notice board. The calendar is flipped to the examination month, with the current week highlighted in red marker pen and clear printed text reading: "MINGGU TENANG". Beside the calendar are pinned official university exam schedules. Soft office lighting, shallow depth of field focusing on the highlighted calendar text. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, blurry text, illegible text, gibberish, 3D render, hands, people.
```

### B. Tumpukan Lembar Jawaban UTS Mahasiswa (`PROP-02`)
```
Photorealistic close-up photograph of a tall disorganized stack of printed A4 exam answer sheets on a wooden lecturer desk. The top sheet clearly shows an official university header and printed title: "LEMBAR JAWABAN UJIAN TENGAH SEMESTER (UTS)". Manila folders and blue and red ballpoint pens rest next to the paper stacks. Shallow depth of field, warm indoor office lighting, sharp paper texture. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, digital tablet, blank paper, messy trash, hands, people.
```

### C. Jam Dinding Analog Kampus — Tepat Pukul 08:00 (`PROP-03`)
```
Photorealistic straight-on close-up photograph of a classic round analog wall clock mounted on a white classroom wall. The clock hands clearly indicate exactly 8:00 (hour hand pointing precisely at 8, minute hand pointing straight up at 12, red second hand). Clean glass cover with subtle light reflection, sharp numerals on a crisp white dial. High detail, neutral indoor lighting. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, distorted clock face, wrong time, melting clock, numbers missing, blurry.
```

### D. Dokumen Pakta Integritas Dosen PEKERTI (`PROP-04`)
*Gunakan attachment: Logo USK.*

```
Use the attached USK logo as reference for the letterhead header emblem. Photorealistic close-up photograph of a formal Indonesian university document lying flat on a conference table next to a luxury black fountain pen. The document has an official USK letterhead at the top and a prominent bold centered title: "PAKTA INTEGRITAS DAN RENCANA AKSI KETELADANAN DOSEN PEKERTI". Clean printed clauses in Indonesian text below, followed by designated signature lines for faculty lecturers. Natural seminar room lighting, high detail, sharp focus on the header and title. Aspect ratio 16:9.
Negative prompt: cartoon, illustration, 3D render, blank document, crumpled paper, hands, coffee stains, blurry.
```
