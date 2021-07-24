all games
- findings based on hare tokidoki otenkiame trial 1

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
  the directory structure can be flat in this file, no need to put the files in
  their original directories. the game will also check patch2.xp3, pathch3.xp3
  etc if they exist, taking a file from the archive with the highest number

known issues:
- engine doesn't support word wrap for english words out of the box
- insani-xp3-tools has a description on how to fix word wrap

issues:
- voice disappeared when i changed a voiced line and the character name. voice
  is intact if i leave character name and name associated with voice file alone
