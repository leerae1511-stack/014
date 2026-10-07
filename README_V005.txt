Tool Pocket Generator — V005

Provenance: built directly from supplied Tool_Pocket_Generator_V004(1).zip.

Authorised change: JSON and STL export filename version suffixes now use one runtime GENERATOR_VERSION variable derived from the generator version-bearing app metadata. The old V83/V99 filename literals are removed. Existing export generation and download behaviour is unchanged.

Protection: detectPhoto() and detectWorkspaceRectangle() are byte-for-byte unchanged from V004.

Checks: ZIP integrity PASS; export expressions use GENERATOR_VERSION; V83/V99 export filename literals removed; protected New Tool functions unchanged. Browser/iPad runtime test remains for user validation.

User validation: confirm V005 display, export JSON and STL and confirm both filenames contain V005, then repeat New Tool exact outline detection.
