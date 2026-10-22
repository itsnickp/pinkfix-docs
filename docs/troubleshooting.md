# Troubleshooting

## A file I can see on disk still shows as missing

- Add the folder that contains it (or a parent, with **Recursive** on) and click **Match**.
- Check **Max Depth** on that search folder (0 = no limit).
- Check **Extensions** in the preferences: files with other extensions aren't searched.
  Leave it empty to search every file.
- A renamed file with a low name similarity is filtered out: lower **Fuzzy Minimum**
  under **Relink > Advanced**.

## A match was found but Apply didn't change it

Apply only relinks **ticked** rows. Suggestions (yellow) and ambiguous rows (question mark)
are never ticked for you: check the proposed file and tick it if it's right.

## "Collect failed, nothing written"

The target folder couldn't be written (read-only folder or no permission).
Pick another folder or fix its permissions. Nothing was copied.

## "Collect incomplete: … is not portable yet"

Collect fixes the paths inside the copied `.blend` files with a second, background Blender.
If that fails or times out, the copied files are in the named folder but its `.blend`
copies may still point at the original locations. Your open file and the originals are
unchanged. Delete that folder and run Collect again into an empty one; use
**Copy Diagnostics** if it keeps failing.

## "Save the .blend first"

Collect saves a copy of your `.blend` into the folder, so the file needs a location on
disk first.

## Undo

One ++ctrl+z++ after **Apply** restores every path. **Collect & Pack** doesn't change any path in
your open file, so there's nothing to undo; delete the folder if you don't want it.

## Asking for help: Copy Diagnostics

1. Click **Copy Diagnostics** in the **Scan** panel.
2. Leave **Include Paths** off unless support asks for it. By default it copies the Pink Fix,
   Blender, OS and Python versions, your Pink Fix settings and the file counts per kind,
   with no file or folder names.
3. Click **OK** and paste the text into your support message on Superhive.
