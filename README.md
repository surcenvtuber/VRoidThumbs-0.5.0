# VRoidThumbs-0.5.0
Windows Explorer thumbnails for .vroid / .vroidcustomitem / .vrm / .xwear / .xavatar

What it does
Shows previews directly in Windows Explorer for:
.vroid / .vroidcustomitem - the thumbnail baked into the file
.vrm - the VRM meta thumbnail (VRM 0.x and 1.0)
.xwear / .xavatar - these formats carry no thumbnail, so the
largest texture in the file is used instead.
Works well for garment atlases (you can tell
colourways apart at a glance); less useful
for plain or unusual UV layouts.

Files with no usable image silently fall back to the default icon.

How to use
1. Run VRoidThumbsSetup.exe
2. Click "Install" (keep the "Restart Explorer and clear the thumbnail
cache" box ticked)
3. Open a folder with VRoid files and switch to medium or large icons

Removing it
Run VRoidThumbsSetup.exe again and click "Uninstall". All registry
entries are removed. Command line: VRoidThumbsSetup.exe /uninstall

Will it slow my folders down?
No. Both file types are ZIP containers with a small preview image
already baked in (thumbnails/thumbnail.png / .jpg). This tool seeks to
the ZIP directory, pulls out that one small image, and stops - it never
parses model data. On a 150 MB test container, extraction averaged
under 1 millisecond. Windows also caches thumbnails, so only the first
visit to a folder does any work.
(PSD thumbnail patches are slow because they must composite a
multi-hundred-megabyte layered image. This is a different situation.)

About the security warning
The installer is not code-signed, so SmartScreen may show an "unknown
publisher" prompt. Click "More info" -> "Run anyway". Full source is in
src/ if you would rather build it yourself.

Known limitations
- 64-bit Windows only
- Installs for the current user (HKCU); no administrator rights needed
- Files with no embedded thumbnail, or damaged files, silently fall
back to the default icon
- If the DLL is locked by Explorer during install/uninstall, the stale
copy is cleaned up on the next reboot

Disclaimer
Not affiliated with pixiv / VRoid. Read-only: it never modifies your
.vroid or .vroidcustomitem files.
