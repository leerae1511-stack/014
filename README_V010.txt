Tool Pocket Generator — V010
Release status: User validation build

SOURCE / PROVENANCE
- Built directly from Tool_Pocket_Generator_V009_FINAL.zip.
- V009 was the immediately preceding build and the only application source used.
- No V007, V008, V147, or older build was used as the application source.

REQUESTED SCOPE — ONE FUNCTION ONLY
- Adjust Detect exact tool outline.
- All other successful functions and processes were left unchanged.

V010 DETECT EXACT TOOL OUTLINE CHANGE
- The photographed physical grid remains the scale authority.
- The detector no longer uses the workspace rectangle or entered tool dimensions to determine the detected outline size.
- Detection now identifies substantial dark tool material by local contrast/thickness rather than selecting a small coloured component as the primary tool.
- A nearby coloured component can be joined to the dark tool body. This specifically handles tools such as the brass-bristled brush where the handle is black but the working end is coloured.
- Thin printed grid lines are rejected by the local-area test because they do not occupy enough dark area around a pixel.
- The detected photo outline is returned in photo coordinates and then placed in the workspace without proportional enlargement when the workspace dimensions are changed.
- The existing physical-grid measurement path remains the dimensional authority.

NOT CHANGED
- New Tool workflow.
- Import JSON workflow.
- Point editing, point numbering, add/delete/range-delete behaviour.
- Straight/Curve controls and curve geometry.
- Physical-grid confirmation and ruler measurement functions.
- Workspace rectangle process.
- Set dimensions from physical grid.
- Close Profile.
- Geometry Check.
- JSON export/import structure apart from the required V010 version labels.
- STL geometry/export process apart from required V010 version labels.
- Finger Relief functionality remains removed as established in V009.

VERSION ALIGNMENT
- Application title: V010.
- Page heading: V010.
- Saved project/export version labels: V010.
- Manifest name: V010.
- Service-worker cache name: v010.
- Historical README_V004.txt, README_V005.txt and README_V009.txt are retained as provenance records and were not rewritten.

TESTING / VERIFICATION PERFORMED
1. V009 ZIP unpacked and used as the source build.
2. JavaScript syntax check: PASS.
3. Application/manifest/service-worker version alignment: PASS — no V009/v009 version strings remain in the active application files.
4. Detector regression analysis using the two locked physical-grid photographs:
   - IMG_6448.jpeg — wrench: detector candidate bbox approximately 250 × 69 pixels at the detector's 320 px working width; this corresponds to the established successful wrench result and preserves the complete silhouette.
   - IMG_6445.jpeg — brush: detector candidate bbox approximately 278 × 49 pixels at the detector's 320 px working width; the coloured bristle component is joined to the black handle. The full long brush is therefore detected instead of the short bristle section selected by V009.
5. Physical-grid scale path remains separate from workspace dimensions. The detector itself does not read L/W or the workspace rectangle.
6. ZIP integrity and contents checked after packaging.

USER VALIDATION REQUIRED
- Test New Tool with the wrench photo and confirm the existing successful outline remains unchanged.
- Test New Tool with the brush photo and confirm the complete brush outline is detected from the physical photograph/grid.
- Change the workspace rectangle dimensions after detection and confirm the detected outline does NOT proportionally increase or decrease.
- User/iPad Safari validation remains the final acceptance test.
