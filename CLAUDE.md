# Duskfade Autosplitters: working agreement

Public repo on GitHub (`Zyrumi/duskfade-autosplitters`) that other people may contribute to.

- **`main` is live.** Runners (and LiveSplit's auto-download, once listed) use `main`. Never push or merge to `main` unless the user says the script is known to work.
- **Work on `dev`.** Commit and push to `dev` automatically as work completes; that's pre-authorized. Pull requests from others target `dev`; read them fully before merging.
- **Fetch first.** Run `git fetch` before any work and pull if `origin` is ahead.
- **Compile-check every `.asl` change** with LiveSplit's own ASL compiler before committing (Windows PowerShell 5.1, load LiveSplit's DLLs, call `LiveSplit.ASL.ASLParser.Parse(code)`).
- **Never create a GitHub Release or tag** unless the user asks.
- **No Claude attribution anywhere**: no Co-Authored-By or Claude-Session trailers, no "Generated with Claude Code".
- **ASL comments:** short one-line labels per element, no long paragraphs.
- **No em dashes** in READMEs or any user-facing text.
