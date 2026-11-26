# CoH3 Trainer

A small, free trainer for **Company of Heroes 3** (Steam, PC) for **offline campaign and skirmish**.
Set or freeze your manpower, munitions and fuel, and raise your population cap.

> [!WARNING]
> **Offline only. Do not use it in multiplayer or in any online/ranked game.** Changing game memory online is
> cheating, is unfair to other players, and can get your account banned. Use it in single-player campaign
> and skirmish against the AI only.

## Features

| Value | What you can do |
| --- | --- |
| Manpower, Munitions, Fuel | Set to any amount, or freeze so it never runs out |
| Population Cap | Raise the cap to field a bigger army (also lifts the lower limits some campaign missions use) |

- One small exe, no installer. Nothing is written to the game files; changes only last while the game is running.
- Finds your player by itself, also after you load another mission.
- Start it before or after the game.

## Requirements

- Windows 10 or 11, 64-bit
- **[.NET 10 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/10.0)** (x64). On that page, pick
  **".NET Desktop Runtime"** for Windows x64. If it's missing, Windows tells you when you start the trainer and
  offers the download.
- Windows 11 only: **Smart App Control** must be off (it blocks unsigned programs; see
  [below](#antivirus-smartscreen-and-smart-app-control)). On most PCs it already is.
- Company of Heroes 3 from Steam. Tested game versions: **5.1.52176** and **5.1.52564**.

## How to use

1. Download `CoH3Trainer-vX.Y.Z.zip` from the [Releases page](https://github.com/Frogstep/CoH3-Trainer/releases)
   and unzip it anywhere.
2. Start the game and load a campaign mission or a skirmish against the AI.
3. Run `CoH3Trainer.exe`. When it says it's attached and shows your current values, you're ready.
4. **Set** a value: type a number in *New value* and press **Enter** or click **Set**.
5. **Freeze** a resource: tick **Freeze**. It stays at the number in the box, or at the current value if the box
   is empty. Frozen values are shown in blue. Untick to unfreeze. (Population Cap has no Freeze: once set, it stays.)

**Player dropdown:** some campaign missions switch you to a different player partway through (for example when you
take over another group). If the values in the trainer don't match the game, pick another player (1000–1003).

## After a game update

The trainer shows a green line when your game version is one it knows, and a red line when it isn't. A game patch
often doesn't break it, so check whether the values still match the game. If they don't, check the
[Releases page](https://github.com/Frogstep/CoH3-Trainer/releases) for a new version, or
[open an issue](https://github.com/Frogstep/CoH3-Trainer/issues) with your game version (shown in the trainer).

## Antivirus, SmartScreen and Smart App Control

The trainer isn't code-signed (a signing certificate costs money every year, and this is a free hobby project).
That has two effects:

- **Smart App Control** (Windows 11): if it's on, Windows blocks the trainer with *"An Application Control policy
  has blocked this file."* There is no per-app exception; the trainer can only run with Smart App Control turned
  off (Windows Security → App & browser control → Smart App Control settings). Smart App Control is only active on
  some fresh Windows 11 installs, and on some Windows versions it can't be turned back on without reinstalling
  Windows, so decide for yourself whether that's worth it.
- **SmartScreen** shows "Windows protected your PC" the first time; click **More info** → **Run anyway**.

Trainers also work by writing into another program's memory, so some antivirus programs flag them. This trainer
contains no network code and doesn't install anything. Only download it from the
[official Releases page](https://github.com/Frogstep/CoH3-Trainer/releases). Each release lists the SHA-256 hash of
its files so you can check that your download is the official one (`Get-FileHash CoH3Trainer.exe` in PowerShell).

## Troubleshooting

| Problem | What to do |
| --- | --- |
| "An Application Control policy has blocked this file" | Smart App Control is on; see *Antivirus, SmartScreen and Smart App Control*. |
| Nothing happens / a .NET message appears when starting | Install the .NET 10 **Desktop** Runtime (x64), see Requirements. |
| "Waiting for RelicCoH3.exe..." | Start the game. The trainer finds it within a second. |
| Attached, but "waiting for a battle" and values show `-` | Load into a mission or skirmish; the values only exist during a battle. |
| Values don't match what the game shows | Try another player in the dropdown. If none match, the game was probably updated; see *After a game update*. |
| "OpenProcess failed" | Run the trainer as administrator (only needed if the game runs as administrator). |
| A resource goes back after you set it | Tick **Freeze**. |
| Something else | [Open an issue](https://github.com/Frogstep/CoH3-Trainer/issues) with the game version, the trainer version (window title) and what the trainer shows. |

## Disclaimer

This is an unofficial fan-made tool. It is not affiliated with, endorsed by or supported by Relic Entertainment,
SEGA or Valve. "Company of Heroes" is a trademark of its respective owner. Use it at your own risk; the software
is provided "as is", without warranty of any kind (see [LICENSE](LICENSE)).

## License

Freeware: free for personal use; please don't re-host it, link to the Releases page instead. See [LICENSE](LICENSE).
Third-party components are listed in [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt).
