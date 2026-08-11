# DerpMap

An interactive map maker: drop a high-resolution image in, pin the places that matter, describe
them, attach photos — and push the whole thing to a GitHub repository so other people can edit it
with you.

C# / .NET 10 / Avalonia 11.

---

## Build and run

```bash
dotnet run --project src/DerpMap/DerpMap.csproj
```

### Publishing

The app publishes as **Native AOT**: one native `DerpMap.exe` (~18 MB) next to the Skia, HarfBuzz
and ANGLE native libraries — no .NET runtime on the target machine, no JIT, and a cold start with
nothing to warm up.

```bash
dotnet publish src/DerpMap/DerpMap.csproj -c Release -r win-x64
```

or run `src/publish.bat`, which drops the result in `src/publish/win64`.

Publishing (not building) needs the **MSVC linker** on the machine doing the publish — Visual Studio
with *Desktop development with C++*, or the standalone Build Tools. Ordinary `dotnet build` and
`dotnet run` do not.

`win-arm64` is also configured; pass `-r win-arm64` and install the C++ ARM64 build tools.

#### Staying AOT-clean

AOT removes the reflection that a lot of convenient .NET APIs quietly depend on, and the failures
land at runtime in the shipped binary rather than at compile time. Two guards keep that from
happening:

* The trim, AOT and single-file **analyzers run on every ordinary build**, not just at publish, so a
  reflection-dependent API is a warning the moment it is written.
* `JsonSerializerIsReflectionEnabledByDefault` is **off**. Everything persisted goes through the
  source-generated context in [`Services/AppJson.cs`](src/DerpMap/Services/AppJson.cs); a type that
  is not declared there throws in Debug too, instead of only in the published app. Adding a new
  persisted root type means adding one `[JsonSerializable(typeof(T))]` line to it.

---

## What it does

### 1. High-resolution maps you can scroll

Any PNG / JPEG / BMP / GIF / WEBP becomes a map. The image is copied into the map's own folder, so
the original can be moved or deleted afterwards.

| Action | Input |
| --- | --- |
| Pan | Drag with the left button on empty map, or drag with the middle button anywhere |
| Zoom | Mouse wheel (zooms around the pointer) |
| Zoom in / out | `+` / `-` |
| Fit to window | `F`, or the **Fit** button |
| Nudge the view | Arrow keys |

The view is clamped so the map can never be panned off into the void.

### 2. Markers

Right-click the map → **Add marker here**, or press **＋ Add marker** and click where you want it.
Drag a marker to move it (switch **Lock** on to prevent accidental drags).

Each marker carries a name, a description, any number of photos, a category, a size multiplier, and
optional per-marker icon and colour overrides. Icons are either one of 24 built-in vector glyphs
(chest, skull, cave, camp, mountain, key, …) tinted with the category colour, or your own image file.

Markers keep a **constant on-screen size at any zoom level** — the icon counter-scales by `1 / zoom`
— so a map zoomed all the way out doesn't turn into a wall of giant pins.

* **Hover** a marker → a floating card with its name, category, description and a preview of the
  first attached photo.
* **Double-click** a marker → the full marker card: complete description, photo gallery with a
  thumbnail strip and captions, timestamps, and buttons to edit, show on map, or delete.

### 3. Legend

Down the left-hand side:

* **Categories** — each with a colour/icon swatch and a marker count. Untick one and every marker in
  it disappears from the map. **All** / **None** toggle everything at once.
* **Search** (`Ctrl+F`) — matches marker names, descriptions and category names as you type.
  Matching markers stay bright, everything else fades to 22% so you keep the spatial context.
  Click a result to centre the map on it; double-click to open its card.
  With an empty box the list doubles as a browsable index of every marker on the map.

**Manage categories…** opens the editor for adding, renaming, recolouring, reordering and deleting
categories. Deleting one that still holds markers asks whether to move them or delete them too.

### 4. Several maps at once

Every open map gets a tab. Switching tabs preserves each map's own pan/zoom position, search text and
... (осталось: 60 строк)
