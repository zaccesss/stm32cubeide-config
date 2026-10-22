# Contributing

Thanks for taking an interest. Contributions are welcome: preference fixes, key binding
corrections, colour mapping fixes, merge script fixes and guide improvements.

## What belongs here

- A wrong key or value in `shared/prefs/` or a platform's `prefs/`
- A key binding whose command or context id is wrong for a current STM32CubeIDE release
- A C colour mapped from the wrong Java colour in `scripts/build-themes.py`
- A merge script bug: a line it drops, mangles or duplicates
- A workspace path or install step that is wrong for a platform
- Improvements to the guides

## What does not belong here

- A preference that only reflects one person's taste rather than something broadly useful, keep
  that in your own copy
- Hand edits to `shared/theme/`: the themes are built by `scripts/build-themes.py`, so a colour fix
  goes in the script

## How to contribute

1. Fork the repository and create a branch named `fix/<short-description>` or
   `feat/<short-description>`.
2. Change values in the `prefs/` fragments only, never in a script. Keep `mac/apply.sh` and
   `linux/apply.sh` identical.
3. Run the script against a copy of a real workspace, open STM32CubeIDE on it and confirm the change
   shows in the preferences.
4. Open a pull request with a clear title and a one-paragraph description of what changed and
   why. CI checks the fragments and the themes and runs the merge twice.

## Reporting bugs

Open an issue with your STM32CubeIDE version, platform and the merge script's output, what you
expected versus what happened.

More about me and my work: [isaacadjei.me](https://isaacadjei.me).
