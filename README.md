# Repo for RK3326 OPKs

To build an OPK
==================

Prerequisites:
mksquashfs
  - Available in Ubuntu from the squashfs-tools apt package (apt install squashfs-tools)
  - Available in Fedora from the squashfs-tools yum package (yum install squashfs-tools)

Process to create an OPK:

1. Create a manifest file (ex. you can name it default.rk3326.desktop) \
Example manifest file content for PPSSPPSDL:

[Desktop Entry] \
Name=PPSSPP \
Comment=PPSSPP Standalone \
Exec=PPSSPPSDL \
Terminal=false \
Type=Application \
#MimeType=application/zip;application/x-nes-rom; \
StartupNotify=true \
Icon=ppsspp \
Categories=emulators;

2. mksquashfs default.rk.3326.desktop source2 source3 .... name.opk -all-root -noappend -no-exports

Test and verify that your name.opk works if possible.

### Note
- Sources can be either specific file, a directory, or a compbination of both. \
- If there are any special libs required for your OPK, include them in the OPK.  Possibly provide a .sh file that will point to those special libs to be loaded during execution. \
Example: LD_LIBRARY_PATH. ./execuable
