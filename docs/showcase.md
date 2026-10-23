# Showcase

Pink Fix on a real test project in Blender 5.2: scan, match, apply, and hand off a folder that just opens.

<figure markdown="span">
  ![Split view of a Blender viewport: left half shows pink missing textures with 15 files missing, right half shows the same scene fully textured after Apply with 0 missing](assets/showcase/01_before_after.webp){ loading=lazy }
  <figcaption>Pink textures fixed in a few clicks</figcaption>
</figure>

<figure markdown="span">
  ![Animation of the Pink Fix panel: Scan finds 15 missing files, Match finds candidates for all 15, Accept All ticks 14 and the 0.72 suggestion is ticked by hand, Apply relinks 15 with 0 missing](assets/showcase/scan_match_apply.gif){ loading=lazy }
  <figcaption>Scan, Match, Apply</figcaption>
</figure>

<figure markdown="span">
  ![Pink Fix Relink results with Wood_Diffuse.png matched to wood_diffuse_2k.png at fuzzy confidence 0.72, left unticked for the user to confirm](assets/showcase/02_fuzzy_match.webp){ loading=lazy }
  <figcaption>Finds renamed textures, with confidence scores</figcaption>
</figure>

<figure markdown="span">
  ![Search Folders list with three recursive folders, Asset_Library Floors, Asset_Library Walls and Downloads, giving candidates for 15 of 15 missing files in one Match](assets/showcase/03_multiple_folders.webp){ loading=lazy }
  <figcaption>Search several asset folders at once</figcaption>
</figure>

<figure markdown="span">
  ![Dry Run report listing every old and new file path without changing anything, with the option to export it as CSV](assets/showcase/04_dry_run.webp){ loading=lazy }
  <figcaption>Preview every change before it happens</figcaption>
</figure>

<figure markdown="span">
  ![Collect and Pack saving a portable copy with 21 files, and the collected .blend opened in a new Blender with originals hidden showing 0 missing and 18 OK](assets/showcase/05_collect.webp){ loading=lazy }
  <figcaption>Hand off a folder that just opens</figcaption>
</figure>

<figure markdown="span">
  ![Comparison table of Pink Fix against Blender's built-in Find Missing Files on the same test project: Pink Fix leaves 0 of 29 missing files versus 5, and also fixes other extensions and renamed files](assets/showcase/06_comparison.webp){ loading=lazy }
  <figcaption>Pink Fix vs Blender's built-in Find Missing Files</figcaption>
</figure>
