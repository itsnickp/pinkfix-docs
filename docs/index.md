# Pink Fix

Pink Fix finds the external files a `.blend` uses (images, UDIM sets, image sequences,
movie clips, sounds, fonts and linked libraries), shows which ones are missing, relinks
them from folders you choose, and can collect everything into one project folder.

Works on Blender 4.2 LTS to 5.2 LTS. It never touches the network.

**[See it in action: Showcase](showcase.md)**

## Quick start

1. **Scan.** In the 3D Viewport press ++n++, open the **Pink Fix** tab and click **Scan**.
   The table shows how many files of each kind are OK, missing, ambiguous or packed.
2. **Match.** In **Relink**, click **+** and pick the folder(s) where the files might be
   now, then click **Match**. Each missing file gets its best candidate, if one is found.
3. **Apply.** Click **Accept All** to tick every confident match, tick any suggestions you
   agree with, then click **Apply**. One ++ctrl+z++ undoes the whole relink.

Every action reports a one-line result in the status bar, for example
*"Relinked 37 of 40 missing files, 3 ambiguous"*.
