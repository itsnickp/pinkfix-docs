# Panels

Everything lives in the 3D Viewport sidebar (++n++), tab **Pink Fix**. The main actions
are also under **File > External Data**.

## Scan

**Scan** lists every external path the file uses. The panel shows totals per status and,
per kind (Image, UDIM, Sequence, Movie, Sound, Font, Library), a count under each status
icon:

| Status | Meaning |
|---|---|
| OK | The file is on disk (for a UDIM set or sequence: at least one tile or frame). |
| Missing | Not found at the stored path. |
| Ambiguous | After **Match**: two or more candidates within 0.02 confidence. One is proposed, unticked; tick it only if it's right. |
| Packed | Stored inside the `.blend`; nothing to fix. |

**Export Report** saves the last Apply or Collect result (or, before either, the open
proposals) as `.csv` or `.txt`. **Copy Diagnostics** is described in
[Troubleshooting](troubleshooting.md).

## Relink

- **Search Folders**: where to look. **+** adds a folder, **−** removes the selected one.
  Select a folder to set **Recursive** and **Max Depth** (0 = no limit).
  A folder on the same drive as the saved `.blend` is stored relative to it (`//textures`).
- **Auto-Accept** (default 0.85): **Accept All** ticks proposals at or above this
  confidence.
- **Match** searches the folders once and proposes a file for each missing path, trying in
  order: exact name, the name in different case, the same name with another extension,
  then similar names.
- **Accept All** ticks every unambiguous proposal at or above Auto-Accept.
- **Dry Run**: Apply only reports what it would change.
- **Apply** relinks every ticked row. A path that was relative to the `.blend` stays
  relative (on the same drive). ++ctrl+z++ restores all the old paths.
- The list shows the files that need fixing (tick **Show All** in its filter to see every
  file); when nothing is missing it says **All files found**. Each row has a tick box, the
  file name with a cue icon, and the confidence on the right:
    - file icon: not matched yet
    - green: at or above Auto-Accept
    - yellow: a **suggestion** below Auto-Accept. It's never ticked for you; tick it if
      it's right.
    - red: Match found nothing
    - question mark: ambiguous
- Hover a file name for what its row means, the proposed file and which materials,
  objects or worlds use it. The **Details** panel under the list (closed by default) shows the selected row.
- A file stored inside a linked library can't be relinked from your file (the change
  wouldn't be saved); its row says so. Open that library and fix it there.

### Advanced

- **Fuzzy Minimum** (default 0.60): how similar a different filename must be to be
  offered as a suggestion at all. Lower it to see more distant names; raise it to cut noise.

## Collect & Pack

**Collect & Pack** makes a self-contained copy of your project in one folder (**Target**,
default `//pinkfix_collected/` next to the `.blend`):

- every file that was found, sorted into `textures`, `media`, `sounds`, `fonts` and
  `libraries`;
- a copy of your `.blend` (same name; numbered if one is already there) whose paths point
  into that folder, relative to the copy (`//textures/wood.png`);
- copies of linked libraries, with their own files next to them and their paths also made
  relative to themselves, including a library that linked another one by an absolute
  path.

The copies hold no Pink Fix settings (no search folders, proposals or reports) and no
File Browser folder (Blender saves your home folder there by default), so the folder you
hand off doesn't reveal the original folders or your user name.

Move or zip the folder and open the `.blend` inside it on another machine (tested on Windows, macOS and Linux). The paths in your open
file and your original files are not changed, and existing files in the target are never
overwritten. Save the `.blend` first. With **Dry Run** on, it only reports what it would
copy.

If the target folder can't be written, nothing is written at all.

## Preferences

**Edit > Preferences > Add-ons > Pink Fix**: default search folders, default Auto-Accept
and Fuzzy Minimum, which file extensions to search (empty = all), and the default Collect
folder name. A scene picks these up the first time you Scan or Match in it.
