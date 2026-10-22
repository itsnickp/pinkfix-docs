# FAQ

## Does it handle UDIM tiles?

Yes. A `<UDIM>` (or `<UVTILE>`) image is matched by its first tile and relinked with the
token kept, so every tile follows. An image sequence is matched by the frame file it
stores (`frame_0001.png`) and relinked to it; the other frames are read from the same folder.

## What about linked libraries?

Missing library `.blend` files are found, relinked like any other file and reloaded. If a
library links another library that also moved, the inner one only appears once the outer
one loads: run **Scan → Match → Apply** a second time to fix it.

Textures stored *inside* a linked library belong to that library file: Pink Fix won't
rewrite them from your file. **Collect & Pack** copies them next to the library's copy
and fixes the paths inside that copy (never the original library).

## Does it modify my original files?

No. Relinking only changes the paths stored in your open `.blend` (undo with ++ctrl+z++).
**Collect & Pack** writes *copies* into the target folder (files, a copy of your `.blend`,
copies of linked libraries) and changes paths only inside those copies; your open file
and the originals are never moved, renamed, overwritten or deleted.

## Why wasn't a match ticked automatically?

Only proposals at or above **Auto-Accept** (0.85) are ticked by **Accept All**. Exact
names score 1.00, different-case names 0.95 and the same name with another image
extension (`wood.png` → `wood.jpg`, `.tga`, `.psd`…) 0.85, so those are ticked. Another extension outside
the image family scores 0.82 and similar names 0.50–0.80, so those show as
**suggestions** for you to check and tick. Ambiguous files (the same name in two folders)
are never ticked for you.

## Does it work with paths saved on another OS?

Yes. Blend-relative paths saved on Windows (`//textures\wood.png`) resolve on Linux and macOS, and
absolute paths from another machine (`D:\Projects\...` or `/mnt/projects/...`) show as
missing and are matched by filename.

## Does it connect to the internet?

No. Pink Fix has no network access and no updater of its own. Updates come from Superhive
through Blender; see [Updates from Superhive](updates.md).
