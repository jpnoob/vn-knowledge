mashiro iro symphony (haven't tried on other games)

link to tools:
http://asmodean.reverse.net/pages/exmaspaz.html
https://github.com/jpnoob/vn-packunpack/tree/main/MUSICA/spaceconv
https://github.com/jpnoob/vn-packunpack/tree/main/MUSICA/mashirowrap

tools:
- use exmaspaz to unpack/pack archive files
  - can also use garbro to unpack (not pack)
- use spaceconv (my own tool) to mass-convert normal space to japanese space
  in script
- use mashirowrap (my own tool) to check if lines (translated to english)
  need linebreak

known info:
- the script is already in plaintext, no conversion needed
- using space in sentences causes the entire line to disappear. use an
  alternative space character like the 2-byte sequence 81 40 (hex) instead
- word wrapping is not handled automatically. mashiro iro symphony uses a
  monofont, and there's room for 46 characters on a line. can use \n to break
  lines. 81 40 space is slightly wider than a char, so lines with lots of
  spaces might need to be shorter than that
- to my knowledge, the game doesn't read loose files, must pack changed files
  back into archive files
- images with japanese text:
  - sys.dat/anim/title01/[11-15].png (main menu text)
  - sys.dat/cg/bg.png (cg gallery)
  - sys.dat/cg/char[0-3]_[off/on].png (voice on/off settings, looks extremely painful to edit) 
  - sys.dat/mem/*.png (gallery stuff)
  - sys.dat/mus/*.png (music title stuff)
  - sys.dat/sc/bg.png (scene gallery)
  - sys.dat/st/*.png (bunch of misc files with jp text, also in subdirectories)
  - sys.dat/*.png (another bunch of misc files with jp text, incl splash warning screen)
  - st.dat/anim/bg/img_date/0?.png (calendar date stuff)
  - st.dat/anim/bg/img03/??.png (intro text from forced autoplay sequence at the beginning)
  - there's a lot more in st.dat i guess

stuff that's slightly cumbersome to change:
- when i try to repack st.dat using exmaspaz with non-japanese locale, i get an
  error saying that ｂｇ.png ("bg" shown in wrong codepage) can't be opened. it
  works when i run cmd.exe (\Windows\SysWOW64\cmd.exe) with locale emulator.
  locale emulator can occasionally bug out and show a generic error message
  instead of showing the actual text, but that should be solved by restarting
  cmd.exe with locale emulator. the packer will also complain if all the files
  aren't already in the current directory.
- it would be nice to change exmaspaz so that it works without locale emulator,
  but i don't have as-util.h and blowfish.h so i can't (easily) do that

unknown info:
- changed images can show up garbled (wrong colours etc), find correct
  subformat for png

TODO try a tool called fuckpaz (in fuckgalengine), which is stated to support
the following games:
Soreyori no Prologue
Tsumi no Hikari Rendezvous
trinoline
trinoline genesis
Tsumi no Hikari Rendezvous - mikan blossom
Soreyori no Prologue h append disk i guess
Sono Hi no Kemono ni wa,

this engine looks harder than usual to work with, especially finding out how
to unpack archive files from games that aren't supported
-------------------------------------------------------------------------------
how to find keys for unsupported games
https://github.com/Inori/FuckGalEngine/issues/37

need to find crud, toc_key, dat_key

how to find crud:
https://github.com/Inori/FuckGalEngine/blob/master/Minori/note.txt#L17

how to find toc_key, dat_key: (ollydbg script i guess)
https://github.com/Inori/FuckGalEngine/blob/master/Minori/get_key.osc
