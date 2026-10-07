# Tool Pocket Generator V009

Release status: Validation build — user validation required.

## Provenance
- Starting/source build: `Tool_Pocket_Generator_V007.zip`.
- V008 was **not** used as the source.
- V007 is the locked baseline for all functionality outside Profile Editing.
- V147 was used only as the reference for the requested Profile Editing behaviour.

## Authorised V009 change — Profile Editing only
1. Remove all Finger Relief functionality.
2. Replace Finger Relief access with the V147-style Curve/Straight profile editing system.
3. Every profile point starts as Straight for New Tool/detected outlines.
4. Every point has a Straight/Curve option in the Point List; no typed Curve/Straight commands are required.
5. Changing Straight ↔ Curve does not move the point.
6. A Curve point is part of the actual profile geometry. The curve is formed through the Curve point and its surrounding profile points.
7. Dragging a point moves the actual profile geometry with the point.
8. Moving a Curve point moves the curve with it and keeps the curve joined to the surrounding profile.
9. Added points remain Straight by default.

## Explicitly locked / not changed
- New Tool workflow and all non-profile reset behaviour.
- Import JSON workflow and its existing coordinate restoration, except the profile mode restoration required for the new Point List.
- Photo loading and physical-grid confirmation.
- Exact tool-outline detection.
- Workspace rectangle and existing Length × Width behaviour.
- Save Tool workflow.
- Close Profile workflow outside the profile geometry required for curves.
- Geometry Check logic outside removal of FR checks.
- JSON/STL export mechanisms outside removal of FR data/geometry and use of the sampled profile.
- No FR object, FR1/FR2, FR depth, FR placement, or FR STL processing remains.

## Verification performed
- V007 source ZIP unpacked and used directly.
- JavaScript syntax check: PASS.
- Release HTML contains no Finger Relief / FR / placingRelief code or UI.
- Generator branding: V009.
- JSON export version: V009.
- STL solid/export version: V009.
- Manifest version: V009.
- Service-worker cache version: V009.
- Curve geometry code was checked to use the actual Curve point as the middle point of the sampled arc.
- Curve movement changes the sampled profile rather than moving an independent marker.
- V147 profile-editing implementation was inspected and used as the reference for the Point List and curve model.
- iPad/Safari runtime validation has **not** been claimed; user validation is required.

## User validation order
1. Import JSON — confirm outline and dots appear exactly as in V007.
2. Change Length × Width — confirm V007 behaviour is unchanged.
3. New Tool/photo workflow — confirm unchanged.
4. Select any existing point and change Straight ↔ Curve using the point option.
5. Confirm the point does not jump off the profile.
6. Drag a Straight point — confirm the profile follows the point.
7. Drag a Curve point — confirm the curve follows the point and remains joined to both surrounding profile sections.
8. Run Geometry Check.
9. Export JSON and STL and confirm they use V009 naming/versioning.

## Regression rule
If any locked V007 functionality is different, stop testing and report it before any further change.
