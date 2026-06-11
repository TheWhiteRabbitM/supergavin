# 🕹️ SUPER GAVIN

**Gavin Wood's cyberpunk alter ego.** A retro side-scrolling platformer in the spirit of
Super Mario — except the plumber is the co-founder of Ethereum and creator of Polkadot,
the coins are DOTs, the enemies are literal bugs, and an extremely annoying **White Rabbit**
has locked every Parachain Portal in town.

Single HTML file. No frameworks, no build step, no assets — every sprite is drawn on a
`<canvas>` and every note of music is synthesized live with the Web Audio API.

## ▶️ How to play

Just open `index.html` in any modern browser (double-click it). That's it.

If you prefer serving it (or your browser is picky about `file://`):

```
python -m http.server 8000
# then open http://localhost:8000
```

## 🎮 Controls

| Key | Action |
|-----|--------|
| `←` `→` or `A` `D` | Move |
| `SPACE` / `↑` / `W` | Jump — **hold it for a higher jump** |
| `X` or `C` | Fire antivirus bolt (requires the ETH crystal) |
| `P` | Pause |
| `M` | Music on/off |
| `ENTER` | Start / next sector / retry |

## 🌆 The four sectors

Each sector has its own layout, sky, soundtrack, and introduces a new enemy.
The White Rabbit guards the portal at the end of **every** sector — and he gets
tougher each time (3 → 4 → 5 → 6 hits).

| Sector | Vibe | Music | New enemy |
|--------|------|-------|-----------|
| **1-1 · RELAY CHAIN** | Neon city at dusk | Brooding darksynth, 120 BPM | 🪲 Walker & 🪰 Flyer bugs |
| **1-2 · KUSAMA WASTES** | Amber chaos — expect chaos | Frantic chaos-rave, 147 BPM | 🌵 **Spike Bug** — armoured. Do *not* jump on it. Shoot it or go around |
| **1-3 · EVM DEPTHS** | Indigo caves, heavy air | Doomy half-time dirge, 97 BPM | 🦗 **Hopper Bug** — winds up and leaps straight at you |
| **1-4 · JAM CITADEL** | Crimson final gauntlet | Heroic synth finale, 134 BPM | 👻 **Phantom Process** — drifts through walls, homes in on you, can't be stomped. Antivirus only |

## 🧱 Things you will meet

- **Bricks `▤`** — smash them with your head, like a certain plumber
- **`?` blocks** — pop out spinning **DOT tokens** (+100 and one more for the stack)
- Some `?` blocks hide the **ETH crystal** — grab it for **YELLOW PAPER MODE**:
  a pink aura and the ability to fire antivirus bolts with `X`. Survives between
  sectors, lost when you take a hit
- **Validator antenna** — mid-level checkpoint ("BLOCK FINALIZED!")
- **Parachain Portal** — the exit. **LOCKED** until you deal with the rabbit
- **🐇 The White Rabbit** — hops at you, taunts you (`TOO SLOW!`, `WRONG CHAIN!`,
  `FUD FUD FUD!`, `NGMI!`), and needs 3–6 stomps (or bolts) to be REKT.
  He also has a habit of dashing past you mid-level just to be irritating

## 🏆 Scoring

| Action | Points |
|--------|--------|
| Brick smashed | 50 |
| DOT collected | 100 |
| Bug stomped | 200 |
| Bug shot | 150 |
| Rabbit hit | 300 |
| Rabbit REKT | 2000 |
| ETH crystal | 1000 |

Lives: 3 per sector. Game over restarts the current sector (score rolls back to
what you had when you entered it). Falling into the void is, as always, fatal.

## 🔧 Tech notes

- **One file**, vanilla JavaScript, HTML5 Canvas, ~60 fps fixed-timestep loop
- **Pixel-art sprites** defined as character grids in code (see `HEAD_PIX` and
  `RABBIT_PIX`) — Gavin's head is a 16×18 dot-matrix recreated from a photo:
  faded-red trucker cap, amber aviators, grey stubble
- **Procedural music**: kick, hats, snare, bass, pads and arps are all raw
  oscillators / filtered noise scheduled ahead of time with the Web Audio API.
  Each sector swaps tempo, chord progression and drum patterns (see `MUSIC`)
- **Parallax cyberpunk backdrop**: layered skylines, twinkling windows, neon
  signs, synthwave sun, rain, and a pre-rendered CRT scanline overlay
- Levels are data: each entry in `LEVELS` declares its pits, block layout,
  enemy roster, palette and boss HP — adding sector 1-5 is ~30 lines

## ⚠️ Disclaimer

A fan-made parody for fun. Not affiliated with, endorsed by, or associated with
Gavin Wood, Parity Technologies, the Web3 Foundation, Polkadot, Kusama, or
Ethereum. No rabbits were REKT in the making of this game.

---

*Built with Claude Code. The chain won't finalize itself — jack in.* 🐇⛓️
