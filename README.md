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

The trailer sound design in 7M1 (the opening hit, the stop on the Sony card, the braam on Marvel Studios, whooshes, hits, the campanile, the risers) is built from real orchestral recordings, processed in the usual trailer way (pitching, layering, saturation, compression, hall reverb):

- **Versilian Community Sample Library (VCSL)**, CC0: concert bass drums, gong, timpani, clash and suspended cymbals, tubular bells, cajon. https://github.com/sgossner/VCSL
- **Versilian Chamber Orchestra 2 Community Edition (VSCO-2 CE)**, CC0: tuba, tenor trombone and horn sustains for the braam, cello tremolos for the risers, bass drum, anvil, brake drum. https://github.com/sgossner/VSCO-2-CE
- **ESC-50** (K. J. Piczak), CC BY-NC 3.0: two aircraft recordings under the take-off (Freesound sounds 24796 and 161103). https://github.com/karolpiczak/ESC-50

The two ESC-50 clips are licensed for non-commercial use only; everything else is public domain.

## Rights

Music by Jean-Marc Fabri. Picture excerpts belong to their owners (Columbia Pictures, Marvel Studios, BBC) and are used only to present rescores; no affiliation.
