# DCS Mission Briefing Reader

<img src="DCSMissionReader/Resources/DCS_MBR_Icon.ico" alt="DCS Mission Briefing Reader icon" width="96" align="right">

Free Windows application that reads `.miz` mission files from **Digital Combat
Simulator (DCS World)**, shows their briefings, details and taskings, and plots the
mission on an interactive map.

---

## At a glance

| | |
| --- | --- |
| **Type** | Windows desktop app (WPF) |
| **Built with** | C# · .NET 9 |
| **Status** | Active: latest release v1.1e |
| **License** | MIT |

---

## Features

- **Mission parsing:** extracts briefing text, mission details and taskings from `.miz` files.
- **Map view:** units, routes and shapes on an interactive OpenStreetMap-based map.
- **Theatres:** Caucasus, Syria, Persian Gulf, Nevada, Marianas, South Atlantic,
  Sinai, Kola and Afghanistan.
- **Mission library:** indexes a whole missions folder and groups missions by
  theatre and unit.
- **Advanced search** over a local SQLite index:
  - structured filters with negation;
  - automatic detection of aircraft, map, mission type, time of day and coalition
    from plain-text keywords;
  - free-text search with phrase folding, stop words and quoted literal search;
  - Greek language support.

  The full syntax is in the built-in **Search Guide** (`DCS_Search_Guide.html`).

---

## Download and use

1. Download the latest version from the
   [Releases](https://github.com/JRouss1975/DCS_Mission_Briefing_Reader/releases) page.
2. Run `DCSMissionReader.exe`.
3. Click **DCS MISSIONS FOLDER** and choose a folder containing `.miz` files.
4. The app indexes all missions and lists them by theatre and unit.

---

## Requirements

| | |
| --- | --- |
| Operating system | Windows 10 or 11 |
| Runtime | .NET **9** Desktop Runtime |
| Build | [.NET 9 SDK](https://dotnet.microsoft.com/download), or Visual Studio 2022 17.12+ |
| Internet | For map tiles |

---

## Building and running

```bat
dotnet restore
dotnet build
dotnet test
dotnet run --project DCSMissionReader
```

---

## Project structure

```
DCSMissionReader.sln
├─ DCSMissionReader/            WPF application
│  ├─ MizParser.cs              reads .miz mission files
│  ├─ SearchIndex.cs            SQLite search index
│  ├─ Models/                   mission, search and UI models
│  ├─ MainWindow.xaml(.cs)      main window and map
│  ├─ DCS_Search_Guide.html     search syntax guide
│  └─ Resources/                icon and background
├─ DCSMissionReader.Core/       synonyms and map helpers
└─ DCSMissionReader.Tests/      xUnit tests
```

---

## Dependencies

| Package | Used for |
| --- | --- |
| [GMap.NET](https://github.com/judero01col/GMap.NET) (Core, WinPresentation) | Map control and tile management |
| [Microsoft.Data.Sqlite](https://learn.microsoft.com/dotnet/standard/data/sqlite/) | Local search index |
| xUnit, coverlet | Tests |

---

## Attributions and disclaimer

- **THIS MATERIAL IS NOT MADE OR SUPPORTED BY EAGLE DYNAMICS SA.**
- Map data © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors.

---

## License

Licensed under the **MIT License**. See [LICENSE](LICENSE).

Copyright © 2026 Ioannis Roussos.
