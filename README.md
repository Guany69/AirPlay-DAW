# 🎸 DigiJam

**Your body is the instrument. AI is the producer.**

---

We turned air guitar into a freaking album.

DigiJam is a real-time machine vision system that transforms human movement into studio-quality music videos — no instruments, no training, no limits. Up to four people stand in front of a single webcam, mime their instruments, and walk away with a professionally mixed track and an AI-generated anime music video of their performance.

**Heads up, this isn't a toy.**

---

## 🔥 How It Works

### 1. Band Assembly
- Users select their instrument: **Drums**, **Guitar**, **Piano**, or **Vocals**
- Everyone positions themselves in front of a single webcam
- Our **multi-person tracking system** locks onto each performer and assigns them to spatial zones

### 2. Performance Capture
- **MediaPipe pose estimation** tracks 33 body landmarks per person at 30+ FPS
- Instrument-specific classifiers detect musical gestures in real-time:
  - `drum_classifier.py` → Detects hits, identifies snare/kick/hi-hat zones based on hand position and velocity
  - `guitar_classifier.py` + `strum_detector.py` → Tracks strumming patterns, chord hand positioning, and attack intensity
  - `piano_classifier.py` + `piano_detector.py` → Maps finger movements across a virtual keyboard spaceDynamic processing, intelligent arrangement
- Every detected gesture is logged with **millisecond-precision timestamps** to structured JSON

### 3. Audio Synthesis
- Gesture JSON is **quantized to a tempo grid** (8th/16th notes) for rhythmic coherence
- Each event triggers from a curated **instrument soundpack**
- Stems are generated per instrument and run through our **AI enhancement pipeline**:
  - Dynamic compression and EQ
  - Reverb and spatial positioning
  - Intelligent fill generation for sparse sections

### 4. The Mixing Console 🎛️
- Users access a **beginner-friendly dashboard** with:
  - Per-instrument volume faders
  - One-knob effects (reverb, drive, width)
  - Genre presets (Rock, Lo-Fi, J-Pop, Electronic)
- No audio engineering experience required — if you can use a slider, you can mix a track

### 5. Music Video Generation 🎬
- Face snapshots from the performance are transformed into **anime-style avatars** via generative AI
- Avatars are composited onto a dynamic stage background
- Character animations are **synced to detected gesture timestamps**
- Final output: a shareable MP4 music video with the mixed master track

## 🚀 Why DigiJam?

Music creation has gatekeepers: expensive instruments, years of practice, access to studios. We're removing all of them.

With DigiJam, a group of friends at a party can produce a music video in under 5 minutes. A kid who's never touched a guitar can feel like a rockstar. A content creator can generate unlimited original music without licensing headaches.
