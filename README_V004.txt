Tool Pocket Generator — V004
Release status: Validation build; not approved until Lee validates it.

Provenance
- Built directly from /mnt/data/Tool_Pocket_Generator_V001.zip.
- V002 and V003 were not used as source builds.
- Source archive entries were retained; README_V004.txt is added to this release ZIP.

Authorised change — Import JSON only
- When Detect Rectangle in Workspace is used in imported-project mode, existing point positions are converted to physical millimetres.
- The imported outline's physical bounding dimensions are measured from those points.
- The outline is then centred within the newly sized workspace, distributing any extra space around it.
- The original point-to-point geometry and UIDs are retained; no fit-to-rectangle scaling is applied.
- If the workspace is smaller than the outline, centring may place parts of the outline outside the workspace boundary; the outline is not reduced.

New Tool protection
- The non-imported/New Tool branch of detectWorkspaceRectangle() is retained verbatim from V001.
- No photo loading, physical-grid confirmation, photo outline detection, or photo-scale calculation code was changed.
- This is a code-isolation check, not a claim of a full browser/iPad regression test.

Not changed
- Point editing, numbering, straight/curve controls, geometry check, JSON/STL geometry generation, and export naming logic.

Checks performed
- Opened V001 ZIP and verified index.html exists.
- Located the V001 detectWorkspaceRectangle() function exactly once before replacement.
- Retained the original non-imported branch verbatim.
- Added imported-mode centring based on the imported outline's measured point bounds.
- Packaged and verified ZIP integrity and release branding.
- Full browser execution and iPad/Safari runtime testing were not performed in this build session.

Lee's validation checklist — Import JSON only
1. Import the same JSON project used for the V003 test.
2. Note the imported outline's physical dimensions.
3. Increase workspace dimensions and press Detect Rectangle in Workspace.
   Expected: the outline's physical dimensions and shape stay unchanged; extra space appears around it, not just on two sides.
4. Reduce workspace dimensions below the outline dimensions and press Detect Rectangle in Workspace.
   Expected: outline remains the same size and may extend beyond the workspace boundary; it is not scaled down.
5. Confirm point numbering/shape remain intact; edit one point, then run Geometry Check and export/reimport JSON.

New Tool regression assurance
- The New Tool branch is unchanged in the source code. No New Tool photo workflow is requested for this validation round.

Version check
- Release ZIP name: Tool_Pocket_Generator_V004.zip
- README title: V004
- App visible branding: V004
