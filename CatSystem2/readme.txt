all games
- tested on aibeya 2 trial

link to tools:
https://github.com/morkt/GARbro
https://github.com/regomne/chinesize/tree/master/CatSystem2/cstTextProc
https://github.com/jpnoob/vn-packunpack/tree/main/CatSystem2/cat2pack
https://drive.google.com/file/d/1XLRy0pgK3mGc6qRwVl5Vv07autCvkSes/view (tutorial)

tools:
- use garbro to unpack .int files. archive files are encrypted, so
  "check exe" and select the executable to find encryption key
- scripts are in scene.int
- use cstTextProc to convert script files to/from .txt
- use cat2pack (my own util) to make new archive file with scripts
  - can also use garbro to make new archive

known info:
- wordwrap is not handled automatically. lines in aibeya 2 trial are 65 chars
  long, can pad with spaces. \n is also supported

unknown info:
- \@ occurs in the script, dunno what it means

there exists a super-detailed tutorial, it also tells how to translate
gui stuff
