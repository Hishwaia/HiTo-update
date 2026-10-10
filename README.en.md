[Русский](README.md) · **English**

# HiTo — tables, axes and drafting tools for Civil 3D

A toolset for as-built survey documentation: legend tables and blocks from a DWG template, axis
grids with markers and dimension chains, callouts, dimensions and marks, sheets from ready-made
layouts, a calculator over drawing objects and a standards check for schemes.

**Version 2.1.3** · released 2026-10-10 · requires Civil 3D 2027 or later

## Download

**[HiTo Setup v2.1.3.exe](HiTo%20Setup%20v2.1.3.exe)**

The installer and the plugin work in English or Russian. The installer follows the Windows
language; the plugin language is set in its settings.

## What's new in version 2.1.3

- Standards check: a new rule, “Dimensions with typed-in values”. It lists dimensions whose value was typed in by hand and differs from the measured one. A note, not an error; can be switched off.
- User guide: the rule is added to the table of standards check rules.
- General improvements and bug fixes.

## Where to find the guide and contacts

Everything is in one plugin window — **About**: **HiTo** ribbon → “Help” panel, or the
`HiTo_About` command.

- **User guide (PDF)** — the “User guide” tile. Detailed, step by step and with examples for
  every command; it opens in the plugin language, English or Russian.
- **Author's email** — the “Contact” line in the “Details” section; a double-click copies the address.
- **Diagnostics package** — the tile next to it: one file to attach to an email about a problem.
- **Updates** and the list of changes of a version — in the same window.

You can write without opening Civil 3D too — see “[Contact](#contact)” below.

## What it does

All tools are on the **HiTo** ribbon tab. Hover over a button and the tooltip says what the command
does; keep hovering and a “how to use it” explanation unfolds — animated for most commands.

| Panel | Tools |
| --- | --- |
| Legend & blocks | **Create tables** — legend tables and blocks from the data template: tick the rows you need, and the table is assembled and placed at the picked point. A frequent selection is kept as a saved set. Repeat of the last insertion, template markup check, tag assignment. |
| Axes | **Grid axes** with markers, numbering and dimension chains, with a preview throughout the input. Intermediate axis, axes from columns, renumbering, rebuilding to the current settings. |
| Standards check | **Standards check** *(experimental)* — checks a sheet against itself: the title and notes against the scheme, the schedule against the scheme, consistent notation of elevations. Unneeded rules can be turned off; optionally an AI review from the sheet data. Written for sheets lettered in Russian. |
| Calculator | Sum, average, minimum and maximum over texts, dimensions, lines and COGO points. The result goes to the clipboard, to a new MTEXT or into an existing text. |
| Misc | **Opening mark** with wedges, **arc-line dimension** for ties on a plan, **Pie callout** — a callout for a layered structure, **Break line** — zigzag or wavy, single or paired for a long element, **Unsweep** — brings hidden COGO points back by point group. |
| Help | **About** — updates, the user guide (PDF), the author's email, the diagnostics package. |

Sheets from layouts and the repeat of the last insertion are also in the context menu:
right-click → **HiTo**.

## Installation

**Civil 3D 2027 or later** is required. In Civil 3D 2026 and earlier the plugin does not load and
the HiTo tab does not appear: it is built for a platform that only the 2027 series runs on.

1. Close Civil 3D — a running program holds the plugin files.
2. Run the installer and choose the mode: **for all users** of the computer (administrator rights
   needed) or **just for me** (no administrator rights).
3. Windows shows an **“Unknown publisher”** warning — this is expected. The installer is not signed
   with a publisher certificate (those are paid), and SmartScreen warns about any unsigned file
   regardless of its contents. Press “More info” → “Run anyway”. You can make sure the file was not
   replaced on its way to you by its checksum — see below.
4. Start Civil 3D. The **HiTo** tab appears on the ribbon.

An update installs over the previous version; there is no need to remove it by hand. Settings, the
table template and the sheet layouts stay in place: they live in the user profile and the installer
does not overwrite them.

## Checksum

SHA-256 of the installer:

```
b23e62c54e3e4eec11362052110e82092f0ab782ba4cb0a82ea69455019eb05e
```

Check the downloaded file in PowerShell:

```powershell
Get-FileHash "HiTo Setup v2.1.3.exe" -Algorithm SHA256
```

A match means the file is exactly the one released. No match — do not run it and download again.

## Updating

When Civil 3D starts, the plugin compares its version with `version.json` from this repository. If
a new one is out, a notice appears in the lower-right corner — at most once a day. A checkbox in it
postpones reminders until the next version; notices can be turned off altogether in the **About**
window → “Tell me about new versions”.

You can update right from the notice or from the **About** window (**HiTo** ribbon → “Help”
panel). The plugin downloads the installer and compares its SHA-256 with the manifest — on a
mismatch the file is not run. Then one of two ways:

- **“Restart and update”** — Civil 3D closes, asking about saving the drawings, the update is
  installed, and Civil 3D opens again. Offered only when the restart is guaranteed to work: a
  single Civil 3D is open, and administrator rights are confirmed by the same account.
- **“Install on close”** — the installer waits until you close Civil 3D yourself and installs the
  update right after that.

The plugin cannot be updated without restarting Civil 3D: it does not release a loaded library
until it exits. The list of changes of a version is behind the “What's new” button in the
**About** window.

## Network and data

The plugin goes online only to check for an update and to download the installer; there is no
telemetry. The AI review in the standards check is off until you connect a service and an API key
yourself — then the texts and coordinates of the checked sheet go to the service you chose.

If something does not work: **About** → “Diagnostics package” collects logs, settings and details
of the workstation into one `.hitodiag` file — attach it to your problem report. The API key of the
AI service is encrypted in the settings by Windows and is useless on another computer.

## Contact

Email: **hitoplugin@gmail.com** — questions, bug reports, suggestions. Attach the diagnostics package to a bug
report: only the author sees the email. If you have a GitHub account you can also write in the
[Issues](https://github.com/Hishwaia/HiTo-update/issues) tab of this repository — but it is public, so the diagnostics package is better
not posted there.

## What else is in the repository

| File | What for |
| --- | --- |
| `HiTo Setup v2.1.3.exe` | the plugin installer |
| `HiTo Setup v2.1.3.exe.sha256` | the installer checksum as a separate file — in `sha256sum` format, for checking with a utility |
| `version.json` | the manifest for update checks |
| `README.md`, `README.en.md` | this page in Russian and in English |
| `LICENSE` | the full license text — in Russian and in English |

## License

Using the plugin in your work — including in a commercial organisation on its own projects — is
free and needs no consent from the author. You may pass the plugin on to others free of charge and
unmodified, together with the license. Trading in the plugin itself (sale, rental, paid support,
inclusion in a paid product) requires the author's prior written consent. The plugin is licensed,
not sold: decompiling, making derivative builds, repackaging and claiming authorship are
prohibited. The full text is shown during installation in the installer language; both texts,
Russian and English, are in the plugin folder — `License_ru.txt` and `License_en.txt` —
and in this repository, in the [LICENSE](LICENSE) file.

© 2026 Hishwaia. AutoCAD® and Civil 3D® are trademarks of Autodesk, Inc.
