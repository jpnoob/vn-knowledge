all games
- findings based on hare tokidoki otenkiame trial 1 and 2 (no encryption)

link to tools:
https://github.com/morkt/GARbro
http://www.insani.org/tools/ (xp3-tools)

tools:
- use garbro to extract files from .xp3 archives
  - if encryption is not supported we're pretty much out of luck unless we hack
- use xp3-tools to create .xp3 archive
  - can also use garbro

known info:
- files don't need to be re-packaged into their original archive files, it's
  sufficient to pack all changed files into a new file called patch.xp3.
  (depends on the game, doesn't work on kimi to yumemishi for example)
  the directory structure can be flat in this file, no need to put the files in
  their original directories. the game will also check patch2.xp3, pathch3.xp3
  etc if they exist, taking a file from the archive with the highest number

known issues:
- engine doesn't support word wrap for english words out of the box
- insani-xp3-tools has a description on how to fix word wrap

issues:
- voice disappeared when i changed a voiced line and the character name. voice
  is intact if i leave character name and name associated with voice file alone
-------------------------------------------------------------------------------
some decrypt info
https://github.com/morkt/GARbro/issues/70
https://github.com/vn-tools/arc_unpacker/issues/89

relevant routine:
https://github.com/morkt/GARbro/blob/master/ArcFormats/KiriKiri/KiriKiriCx.cs

xp3archive source code in kirikiri engine
https://github.com/krkrz/krkrz/blob/master/base/XP3Archive.cpp
(tTVPXP3ArchiveStream::Read calls xp3filter (decrypter))

.ks scenario files (.psb format), m2 e-mote format info:
https://github.com/morkt/GARbro/issues/153

if there's a .tpm file in plugin/, that one contains the decrypter. if there's
no such file, the .xp3 files can be CxDec encrypted

how to find cxdec key
https://github.com/crskycode/GalgameCoding/blob/main/Kirikiri/HowToFindCxEncryptKey/FindCxdecKey_CN.md

xp3extractionfilterinfo struct defined in
https://github.com/krkrz/krkrz/blob/master/base/XP3Archive.h

offset	length
0x0	4	size of self (always 0x18)
0x4	4	offset of the buffer data in uncompressed stream position
0x8	8	target data buffer
0x10	4	buffer size
0x14	4	filehash
