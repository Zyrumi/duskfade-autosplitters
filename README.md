# Duskfade Autosplitters

LiveSplit autosplitters for [Duskfade](https://store.steampowered.com/app/2542020). Two scripts, pick the one for your category. Both only read the game's memory and save files and never write to the game.

**Use only one at a time.** Running both would fire every start and split twice.

| | Any% (`Duskfade.asl`) | Any category (`Duskfade-LoadSplitter.asl`) |
|---|---|---|
| For | The any% route | 100%, all achievements, anything else |
| Starts | Leaving the main menu (New Game) | Leaving the main menu (New Game), same moment as any% |
| Splits | Each zone on the fixed any% route | Every arrival in a different level, revisits included |
| Ends | Credits | Credits |
| Resets | Optional on returning to the main menu (off by default) | Off by default, so quitting to the menu doesn't end a long run |

Both pause LiveSplit's **Game Time** during loading screens. To see load-removed time, right-click LiveSplit → Compare Against → **Game Time**. This reads a fixed memory address, so a game patch may break it until the script is updated.

## Setup

1. Download [`Duskfade.asl`](Duskfade.asl) or [`Duskfade-LoadSplitter.asl`](Duskfade-LoadSplitter.asl).
2. In LiveSplit: right-click → Edit Layout → **+** → Control → **Scriptable Auto Splitter**.
3. In that component's settings, browse to the downloaded `.asl` file.

## Any% (`Duskfade.asl`)

Every split is its own checkbox in the component's settings, grouped by chapter and all on by default. Uncheck anything not in your route and it's skipped. Zones reached without a checkpoint save, like the wrong warp out of Guayota, still split when the level loads.

Auto-reset on returning to the main menu is available but off by default. If you turn it on, note that restarting the game after a crash also counts as returning to the menu and will reset your run.

If you have more than one save slot on disk, set `SlotFileName` at the top of the script to your exact slot (e.g. `DFSlot_1.sav`), so an unrelated slot (e.g. a Steam Cloud sync) can't trigger a wrong split.

## Any category (`Duskfade-LoadSplitter.asl`)

No route to set up. It splits **every time** you arrive in a different level, including revisits. Coming back to TickTown for the third time in a run splits just like the first.

- Dying or retrying in the same level doesn't split.
- Quitting to the main menu and continuing doesn't split or reset. The timer keeps running.
- Each level has one checkbox under **Split every time you enter:**, all on by default. Checked means that level splits on every visit, and unchecked means it never splits. It's all visits or none, not per visit.
- Pressing Continue outside a run can start the timer. That isn't a real run, so just reset.
- Auto-reset is off, so after abandoning an attempt, reset LiveSplit before your next New Game.

Your splits file needs one segment per arrival at a checked level (count every revisit), plus the credits.

## Branches

- `main` holds only scripts that are known to work. This is what runners should use.
- `dev` is where changes are made and tested first. Pull requests should target `dev`.

## Credits

Load removal by [c3pown](https://github.com/c3pown). Save tools (practice save library and editor) live in [duskfade-save-tools](https://github.com/Zyrumi/duskfade-save-tools).

## License

GPL-3.0, see [LICENSE](LICENSE).
