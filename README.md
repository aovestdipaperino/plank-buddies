# plank-buddies

Buddies for [plank](https://github.com/aovestdipaperino/plank)'s `/buddy` command: a small animated character standing on the rule above the prompt while plank is idle.

Each top-level folder is one buddy. `/buddy on` (with no buddy installed) and `/buddy replace` list the folders here; picking one downloads it into `~/.plank/buddy/`, replacing the buddy you had.

## What a buddy folder holds

`.mp4` clips on a white background. plank decodes them once with `ffmpeg` at half their resolution, keys the white background out, and plays them one after another. The last character of a clip's name decides how often it plays:

- **ends in a letter** (`minionA.mp4`): picked at random among the letter clips, three times out of four;
- **ends in a digit** (`minion1.mp4`): the remaining time, in rotation, `1`, `2`, `3`, ... and back.

Clips whose names end in anything else are ignored.

## Terminals

The buddy is drawn with the kitty graphics protocol: kitty, Ghostty and Warp, outside tmux.
