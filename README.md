# MySQL-Workbench-Bug-92141-patch
Patch Bug # 92141

Bug patch https://bugs.mysql.com/bug.php?id=92141

### The essence of the problem:

In some cases, primary / foreign key icons are not displayed in the ER editor

It was found that in the images folder some of the png icon files are very large. In particular, for the bug in question, the db.Column.pkfk.11x11.png file has a size of more than 4000 bytes (and this is for the 11 x 11 icon). If you compress this file, the problem will be solved

In addition to this file, there are other large files in the images folder. Compress them all using advpng from https://sourceforge.net/projects/advancemame/files/advancecomp/1.15/.

### For Windows:

1. Close MySQL Workbench
2. Copy the files advpng.exe, patch.bat, zlib.dll to the images folder, I have it in "C: \ Program Files \ MySQL \ MySQL Workbench 8.0 CE \ images"
3. Run patch.bat
4. Let's open MySQL Workbench

Checked for version 8.0.19 windows

### For Mac:
Does not require files from repo. Download advpng using the link about or using homebrew.
1. Close MySQL Workbench
2. Nagivate to /Applications/MySQLWorkbench.app/Contents/Resources
3. Run advpng -z db.Column.pkfk.11x11.png
4. Open MySQLWorkbench

Checked for macOS 10.14.6
