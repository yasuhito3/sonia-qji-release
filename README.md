# Sonia 奏在 / Qji
### High-Fidelity Linux Audio Environment · Xubuntu 24.04 Disk Image

A ready-to-run Linux audio system focused on:
- time-coherent playback
- low-level ambience retrieval
- direct ALSA output
- acoustic space simulation
- intelligent music analysis

Write the image, boot the system, add music, and listen.

## Download

| | Link | Size |
|--|------|------|
| 🔗 **Torrent file** | [sonia-en-i-small.img_archive.torrent](./sonia-en-i-small.img_archive.torrent) | 43 KB |
| 🌐 **Internet Archive** | [archive.org/details/sonia-en-i-small.img](https://archive.org/details/sonia-en-i-small.img) | ~22 GB |

The torrent is recommended. Open it with [qBittorrent](https://www.qbittorrent.org/) (free).  
Or download directly from the Internet Archive page without a torrent client.

**Verify your download:**
```bash
sha256sum -c Sonia_en_I_small.img.xz.sha256
```

**Write to USB drive (macOS/Linux):**
```bash
xz -d Sonia_en_I_small.img.xz          # decompress first
sudo dd if=Sonia_en_I_small.img of=/dev/sdX bs=4M status=progress
```



Remark!!!
☆☆☆
###Making bootable sonia disk###

1. Open the GitHub page and download the .torrent file.
(It’s a small file, only a few dozen KB.) [1]
2. Open the file with a BitTorrent client.
(For Windows, qBittorrent is recommended. Download Sonia_en_I_small.img.xz. This file is over 10GB, so it will take some time.)
3. Decompress (Extract) the file.
Linux/Mac: Run xz -d Sonia_en_I_small.img.xz in the terminal.
Windows: Right-click the file and use 7-Zip to extract it.
(This will create a 22GB file named Sonia_en_I_small.img.)
4. Flash the image to a USB drive (64GB or larger).
Linux/Mac:
sudo dd if=Sonia_en_I_small.img of=/dev/sdb bs=4M status=progress
(Make sure to replace /dev/sdb with your actual USB device name.)
Windows:
Use Rufus (free software). Open Rufus, select your USB drive, choose the .img file, and click "Start."
5. Restart your PC and boot from the USB drive.
Enter the BIOS/Boot menu (usually by pressing F12, F2, or Delete during startup) and select the USB drive.
The Sonia/Qji screen should now load.


注目！！！
###torrentから起動ディスク作成###

① GitHubページを開く
   → .torrentファイルをダウンロード（数十KB）

② BitTorrentクライアントで開く
   Windowsなら qBittorrent（無料）
   → Sonia_en_I_small.img.xz を受信（10数GB、時間がかかる）

③ 解凍する
   Linux/Mac: xz -d Sonia_en_I_small.img.xz
   Windows:   7-Zip で右クリック→解凍
   → Sonia_en_I_small.img ができる（22GB）

④ USBメモリ（64GB以上）に書き込む
   Linux/Mac:
     sudo dd if=Sonia_en_I_small.img of=/dev/sdb bs=4M status=progress
     (/dev/sdb の部分は自分のUSBのデバイス名に変える)

   Windows:
     Rufus（無料ソフト）で書き込む
     → Rufusを起動 → USBを選択 → imgファイルを選択 → スタート

⑤ PCを再起動してUSBから起動
   BIOSでUSBブートを選択（F12 か F2 か Delete）
   → Sonia/Qji の画面が起動する







###
Quick Start
1. Write the disk image

sudo dd if=sonia_v1.0.img of=/dev/sdX bs=16M status=progress
sync

Use a 64GB or larger SSD / USB / microSD card.

2. Boot Sonia

Boot from the written disk image.

3. Add your music

Either:

copy music into ~/Music
or connect an external USB drive
4. Build the music library

Double-click:

Music Library Analyzer

Wait for analysis to finish.

5. Start playback

Double-click:

Qji 奏在

Playback starts directly through ALSA.
---

###

## What Is Sonia?

Sonia 奏在 is not a commercial product.
It is a personal high-fidelity listening environment built around a specific idea:

that musical realism emerges not only from frequency response,
but from timing precision, microdynamics,
and retrieval of low-level ambience.

The system attempts to reduce the psychological distance
between listener and performer through direct ALSA playback,
carefully tuned ffmpeg processing,
and acoustic-space modeling.

##What Can Sonia Do?

- Play local music directly through ALSA
- Simulate concert hall acoustics
- Automatically analyze your music library
- Organize tracks by mood and atmosphere
- Stream Qobuz lossless audio
- Save personalized acoustic profiles
- Operate without PulseAudio
- Run on modest Linux hardware

##Typical Workflow
1. Boot Sonia
2. Connect your DAC
3. Add music to ~/Music or external drive
4. Run Music Library Analyzer
5. Launch Qji
6. Choose acoustic space presets
7. Listen and refine





**Sonia 奏在** (Souzai) is an independent, high-fidelity audio player system for Linux, conceived and built by a single developer/audiophile. It is not a product. It is a personal aesthetic statement — an attempt to bring the listening experience of a dedicated hi-fi setup into the Linux command line and desktop environment.

**Qji** is the player engine at the heart of Sonia. It drives audio playback through a carefully tuned ffmpeg filter chain — concert hall simulation, multi-band EQ, dynamics processing, and an optional Air Particle Layer — and sends the result directly to ALSA, bypassing PulseAudio entirely.

This disk image is a ready-to-run Xubuntu 24.04 environment with Sonia / Qji and all dependencies pre-installed. Boot it, connect your DAC, and listen.

---

## System Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| CPU | x86_64 dual-core | Quad-core or better |
| RAM | 4 GB | 8 GB |
| Storage | 25 GB free | 40 GB free (for your music library) |
| Audio | Any ALSA-compatible output | USB DAC (e.g. Amanero-based) |
| OS | — | Bare metal or VM (VirtualBox / VMware) |

> **Note:** Qji writes audio directly to ALSA. For USB DAC users, PulseAudio is disabled in this image. If you need PulseAudio for other applications, you may need to re-enable it manually.

---

## What Is Included

```
Desktop shortcuts:
  Qji Player              → Launch the main player (qji.py / qji_en.py)
  Music Analyzer          → Analyze and tag your local music library
  Sonia Intelligence      → AI acoustic personalization module

Core scripts:
  qji_en.py               → Main player (English UI)
  music_analyzer2.py      → Music library database builder
  genre_presets.py        → Genre-based acoustic presets
  acoustic_spaces.py      → Physical models of concert halls

Sonia Intelligence (SI) module:
  sonia_intelligence/
    profile_db.py         → Per-album acoustic profiles, persistent storage
    filter_builder.py     → Converts SI profiles → ffmpeg filter chains
    acoustic_spaces.py    → (shared)
```

---

## Audio Architecture

```
Music file / Stream
      │
      ▼
  ffmpeg decoder
      │
      ▼
┌─────────────────────────────────┐
│       Sonia Filter Chain        │
│                                 │
│  1. Input gain / normalization  │
│  2. Multi-band EQ               │
│  3. Compressor + Limiter        │
│  4. Concert Hall Simulation     │
│     (Early Reflections +        │
│      Late Reverb via aecho)     │
│  5. Air Particle Layer          │
│     (optional pink noise layer) │
│  6. Output limiter (alimiter)   │
└─────────────────────────────────┘
      │
      ▼
  aplay → ALSA → DAC → Amplifier
```

The filter chain is not a plugin. It is a hand-crafted ffmpeg filtergraph, tuned to a specific listening environment (Mark Levinson amplifier · Vienna Acoustics speakers · Amanero USB DAC). Adjust the presets in `genre_presets.py` and `acoustic_spaces.py` to match your own system.

---

## Acoustic Space Presets

Qji includes physical models of real acoustic spaces, each defined by early reflection geometry, RT60 reverberation time, room EQ signature, and dry/wet balance.

| Preset | Hall | RT60 |
|--------|------|------|
| `musikverein` | Musikverein Großer Saal, Vienna | 2.0 s |
| `concertgebouw` | Concertgebouw, Amsterdam | 2.2 s |
| `carnegie_hall` | Carnegie Hall, New York | 1.8 s |
| `berliner_philharmonie` | Berliner Philharmonie | 2.0 s |
| `salle_pleyel` | Salle Pleyel, Paris | 1.7 s |
| `small_chamber` | Chamber music space | 0.9 s |
| `church` | Stone church | 3.5 s |
| `jazz_club` | Jazz club | 0.5 s |
| `studio_dry` | Dry studio (minimal reverb) | 0.3 s |

---

## Qji Player — Key Controls

| Key | Action |
|-----|--------|
| `Space` | Play / Pause |
| `N` | Next track |
| `P` | Previous track |
| `A` | Cycle acoustic space preset |
| `G` | Cycle genre preset |
| `+` / `-` | Volume up / down |
| `J` | Cover art view (album art mode) |
| `K` | Return from cover art view |
| `Q` | Open Qobuz streaming menu |
| `S` | Save current preset |
| `L` | Load saved preset |
| `I` | Sonia Intelligence — acoustic feedback |
| `Ctrl+C` | Quit |

> The player runs in the terminal. A web-based browser UI for Qobuz (port 8080) is also available via a separate desktop shortcut.

---

## Music Analyzer (music_analyzer2.py)

Scans your local music library and builds a JSON database of mood, genre, tempo, and acoustics for each track. Used by Qji for intelligent playlist generation and automatic genre-preset switching.

**Scanned directories by default:**
- `/var/lib/mpd/music`
- `~/Music`
- `~/AudioFiles`
- `/media` · `/mnt`

To run manually:
```bash
python3 ~/Sonia/music_analyzer2.py
```

The database is saved to `~/music_mood_db.json`. Analysis uses MusicBrainz and Last.fm APIs for metadata enrichment — see **Last.fm API Key Setup** below. An internet connection is recommended for first run.

---

## Last.fm API Key Setup

Last.fm provides rich music metadata — genre tags, mood classifications, artist information — that significantly improves the accuracy of the Music Analyzer. A **free API key** is required.

### Do I need to do this?

- **If you use the Music Analyzer:** Yes, strongly recommended. Without a key, mood and genre tagging falls back to local audio analysis only (still functional, but less accurate).
- **If you only use Qji for playback:** No. You can skip this entirely.

### First-Run Automatic Guide

The **first time you launch the Music Analyzer**, it will detect that no API key is configured and walk you through the setup interactively, step by step. Just follow the on-screen instructions — the whole process takes about two minutes.

```
════════════════════════════════════════════════════════════
  Sonia 奏在 — Last.fm API Key Setup
════════════════════════════════════════════════════════════

  Last.fm provides music metadata (mood, genre tags, etc.)
  that make the Music Analyzer much more accurate.
  A free API key is required. Setup takes about 2 minutes.

  ── How to get your free API key ──────────────────────

  Step 1.  Go to:  https://www.last.fm/api/account/create

  Step 2.  If you don't have a Last.fm account, click
           'Sign up for free' first, then return here.

  Step 3.  Fill in the form:
           · Application name : Sonia  (any name is fine)
           · Application description : Personal music player
           · Callback URL : (leave blank)
           · Click 'Submit'

  Step 4.  Copy the 'API key' shown on the next page.
           It looks like:  a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4

  Paste your API key here: _
```

Once entered, the key is saved permanently to `~/.sonia_config.json`. You will never be asked again.

Pressing **Enter without typing** skips the step — the analyzer will run without Last.fm enrichment, and you can always add the key later.

### Manual Setup (if you prefer)

If you already have a Last.fm API key, or want to set it up before first launch, simply edit (or create) the file `~/.sonia_config.json`:

```json
{
  "lastfm_api_key": "paste_your_key_here"
}
```

Save and close. The Music Analyzer will pick it up automatically on next run.

### Step-by-Step: Getting a Last.fm API Key

1. Open your web browser and go to **https://www.last.fm/join** (create a free account if you don't have one — it takes 30 seconds)
2. Go to **https://www.last.fm/api/account/create**
3. Fill in the application form:

   | Field | What to enter |
   |-------|---------------|
   | Application name | `Sonia` (or anything you like) |
   | Application description | `Personal music player` |
   | Application homepage | (leave blank) |
   | Callback URL | (leave blank) |

4. Click **Submit**
5. On the next page, you will see your **API key** — a 32-character string like `a1b2c3d4e5f6...`
6. Copy it and paste it when the Music Analyzer prompts you (or paste it into `~/.sonia_config.json` manually)

> **Privacy note:** The API key is stored only on your local machine in `~/.sonia_config.json`. It is not transmitted anywhere except to Last.fm's servers for metadata lookups.

---

## Sonia Intelligence (SI)

SI is an AI acoustic personalization layer. It learns your preferences through natural language feedback and adjusts the filter chain parameters — hall selection, EQ curves, dynamics — on a per-album basis.

**Example interaction:**
```
> The piano sounds slightly harsh in the upper mids.
SI → Reducing presence band by 1.2 dB · Saved to album profile.
```

Profiles are stored in `~/.sonia_profiles/` as JSON files, one per album. They persist across sessions and accumulate over time.

SI is optional. If the `sonia_intelligence/` directory or its dependencies are missing, Qji will run normally without it (the ⚠️ message at startup is non-fatal).

---

## Qobuz Streaming
Under construction



**Setup required:**
1. A valid Qobuz subscription (Sublime or Hi-Fi tier recommended for lossless)
2. Browser token extraction — see `~/Sonia/docs/qobuz_setup.md` for the one-time setup procedure

A web UI (port 8080) allows browsing and playing your Qobuz favorites from any browser on the same network.

---

## Dependencies

All of the following are pre-installed in this disk image. Listed here for reference if you install on your own system.

**System packages:**
```
ffmpeg  alsa-utils  python3  python3-pip  python3-mutagen
```

**Python packages:**
```
mutagen  librosa  numpy  requests  urllib3
vosk  sounddevice  (optional — for voice control)
```

**Install on a fresh system:**
```bash
sudo apt install ffmpeg alsa-utils python3 python3-pip
pip3 install mutagen librosa numpy requests vosk sounddevice
```

---

## Known Limitations

- **Japanese strings:** Some internal comments and a few UI labels remain in Japanese. This does not affect functionality.
- **PulseAudio conflict:** Qji uses ALSA directly. If another application holds the ALSA device, playback will fail. Stop any PulseAudio-managed applications before starting Qji, or run: `pulseaudio --kill`
- **librosa startup time:** The music analyzer takes several seconds to import librosa on first run. This is normal.
- **Qobuz tokens expire:** If Qobuz playback stops authenticating, re-run the token extraction procedure.
- **VM audio latency:** Running in a virtual machine may introduce audio latency or glitches, especially with USB DAC passthrough. Bare metal is strongly recommended for serious listening.

---

##Screenshots
Desktop environment
  Screenshot_desktop.png
Qji playback screen
  Screenshot_desktop.png
  Screenshot_radio_selection.png
  Screenshot_playing_radio.png
Acoustic space selection
  Screenshot_select_play_factors.png
  Screenshot_audiopresets.png
Music Analyzer
  Screenshot_music_analyzer.png
  Screenshot_music_analyzer2.png
Qobuz interface
  will be presented in the next version


##Designed For
Sonia is designed for listeners who care about:

- low-level detail
- hall ambience
- microdynamics
- acoustic realism
- direct DAC playback
- reproducible Linux audio environments

Sonia is not optimized for convenience,
streaming ecosystems,
or polished commercial UX.

It is designed for focused listening.







## A Note on This Project

Sonia 奏在 is not designed to be the most convenient or feature-rich audio player. It is designed to sound as good as possible within the constraints of Linux, ffmpeg, and ALSA — and to express a specific listening philosophy: that the acoustic space matters as much as the recording itself.

The concert hall simulation models are not presets borrowed from a plugin library. They are hand-parameterized from descriptions of real halls — their dimensions, materials, and reverberation measurements — translated into aecho filter coefficients. The result is imperfect and entirely intentional.

If you adjust something and it sounds worse, adjust it back. If you adjust something and it sounds better, open a pull request or leave a note.

---

## Contact / Source

- **Developer:** Yasuhito (康人)
- **GitHub:** [yasuhito3/Sonia-for-Android](https://github.com/yasuhito3/Sonia-for-Android) *(related project)*
- **Notes / Articles:** note.com (search: Sonia 奏在)

This project is released for personal, non-commercial use. No warranty is expressed or implied. The acoustic filter parameters reflect one person's listening room, one amplifier, one pair of speakers. Your mileage will vary — and that is the point.

---

*"The concert hall is not an accident. It is the instrument."*
