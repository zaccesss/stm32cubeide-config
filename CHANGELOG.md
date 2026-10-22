# Changelog

All notable changes to this project are recorded here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### Fixed

- The themes colour the Terminal in STM32CubeIDE 2.2. It moved to Eclipse 4.38's `org.eclipse.terminal.control` plugin, so each theme now writes the Terminal colours for that plugin as well as for the older `org.eclipse.tm.terminal.control` 2.1 used.

### Added

- `shared/prefs/` fragments for STM32CubeIDE 2.1.1 (Eclipse 4.33 with CDT): autosave every 20 seconds, line numbers, spaces for tabs at width 4, current line highlight, spell checking in British English for C files and other text and 15 VS Code style key bindings. The bindings are the Eclipse setup's with the Java actions moved to the C editor: `F2` renames, `F12` opens the declaration, `Shift+Alt+F` formats and `F5` and `Ctrl+Shift+F5` debug and run the last launch again, which builds and flashes the board.
- `<platform>/prefs/` font overlays: GeistMono Nerd Font for the text and C/C++ editor fonts and its Mono build for the Terminal, at 18 points on the Mac and 14 on Windows and Linux.
- The eight Zacess themes for STM32CubeIDE in `shared/theme/`, built by `scripts/build-themes.py` from the Zacess Eclipse themes 0.3.0. Each Java colour moves to the C key that plays the same part. Macros and directives take the colour of Java's `return` keyword, so they stay apart from functions in every theme. The Terminal colours move to the `org.eclipse.tm.terminal.control` plugin STM32CubeIDE ships.
- `mac/apply.sh`, `linux/apply.sh` (identical) and `windows/apply.ps1`: find the newest `STM32CubeIDE/workspace_<version>` when no workspace is given, refuse to run while STM32CubeIDE is open, merge the fragments and a theme key by key and print each key as added, changed or unchanged. They make no backup: every value they write is in this repo.
- A `README.md` per platform with the STM32CubeIDE install steps, including the RPM bundle for Fedora.
- `guides/setup.md` and `guides/reference.md`, plus the community-health files.
- CI: every fragment line is a note or `key=value`, the key binding XML parses with 15 bindings, every theme carries the C colours and no Java ones, shellcheck, the two shell scripts are identical, a double run on a throwaway workspace changes nothing and leaves no backup, the default workspace is found and the PowerShell script parses.
