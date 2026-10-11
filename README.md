# Jean-Marc Fabri, Composer

Portfolio site: film and trailer cues, each playable as the piano take and as the full orchestral score, on the same timeline.

## Editing

Everything you will normally change is in `index.html`, in the block marked `EDIT HERE` near the top of the `<script>`:

- `linkedin`, `youtube`, `email`: contact links. Leave a value as `""` to hide it.
- `cues`: one entry per cue, in the order they appear. `no` is the label shown (1M1, 2M1 ...), `title`, `film` and `scene` are the text, `dur` is the length in seconds, `ar` the picture's aspect ratio.

On GitHub you can edit `index.html` directly in the browser (pencil icon), then **Commit changes**. The site updates by itself within a minute or two.

A link ending in `#3m1` (any cue number) opens the page on that cue.

## Media

Each cue uses files named after its `id` in `media/`:

- `<id>-v-init.mp4`, `<id>-v-0.mp4` ...: the picture, full quality, in parts
- `<id>-picture.mp4`: the picture in one lighter file, for browsers that cannot stream the parts
- `<id>-score.mp4`, `<id>-piano.mp4`: the two soundtracks, already locked to the picture
- `<id>-poster.jpg`: the still shown before playback

Adding a new cue means preparing these files (the sync and encoding are the hard part) and adding one entry to `cues`.

## Publishing

GitHub publishes the site after every commit, usually within a few minutes. If a publication fails on GitHub's side (an outage, a machine that never starts), the **Pages watchdog** in `.github/workflows/pages-watchdog.yml` catches it: it runs after every publication attempt and every three hours, compares the live site with `main`, and asks GitHub to publish again when they differ. Nothing to do by hand.

To republish on demand: **Actions**, then **Pages watchdog**, then **Run workflow**, with *force* ticked.

## Sound effects in 7M1

The sound design under the first act of 7M1 (and the cymbal swells and hits around the music) uses these libraries:

- **Versilian Community Sample Library (VCSL)**, CC0: suspended cymbal crescendos, clash cymbals, gong, bass drum, timpani, mark tree. https://github.com/sgossner/VCSL
- **MS-SNSD** (Microsoft), noise recordings: crowd babble and air-conditioning hum from Freesound under CC0; traffic, square, corridor, living room, café, office and restaurant ambiences from the DEMAND corpus (Thiemann, Ito, Vincent), CC BY-SA 3.0. https://github.com/microsoft/MS-SNSD
- **ESC-50** (K. J. Piczak), CC BY-NC 3.0, clips drawn from Freesound: https://github.com/karolpiczak/ESC-50
  - 1-105224-A-22 (clapping), Freesound sound 105224
  - 1-110537-A-22 (clapping), Freesound sound 110537
  - 1-24796-A-47 (airplane), Freesound sound 24796
  - 1-47709-A-16 (wind), Freesound sound 47709
  - 1-47714-A-16 (wind), Freesound sound 47714
  - 1-62565-A-44 (engine), Freesound sound 62565
  - 1-76831-A-42 (siren), Freesound sound 76831
  - 1-81001-A-30 (door wood knock), Freesound sound 81001
  - 2-120333-A-32 (keyboard typing), Freesound sound 120333
  - 2-160888-A-47 (airplane), Freesound sound 160888
  - 2-25292-A-22 (clapping), Freesound sound 25292
  - 3-246513-A-16 (wind), Freesound sound 246513
  - 3-94343-A-25 (footsteps), Freesound sound 94343
  - 4-161103-A-47 (airplane), Freesound sound 161103
  - 4-176631-A-43 (car horn), Freesound sound 176631
  - 4-205738-A-22 (clapping), Freesound sound 205738
  - 5-180156-B-43 (car horn), Freesound sound 180156
  - 5-198373-A-46 (church bells), Freesound sound 198373
  - 5-213077-A-11 (sea waves), Freesound sound 213077
  - 5-250026-B-30 (door wood knock), Freesound sound 250026
  - 5-254160-A-22 (clapping), Freesound sound 254160
  - 5-262957-A-22 (clapping), Freesound sound 262957

The ESC-50 clips are licensed for non-commercial use only. If this cue is ever used commercially, they need replacing.

## Rights

Music by Jean-Marc Fabri. Picture excerpts belong to their owners (Columbia Pictures, Marvel Studios, BBC) and are used only to present rescores; no affiliation.
