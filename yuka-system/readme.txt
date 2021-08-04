all games
- tried akaneiro trial, lover able trial1

link to tools:
https://drive.google.com/file/d/0B4E8zrOX6ZdWaHdJRm9ETWNtZ3c/view?resourcekey=0-SwaKa2y-ZDSU4e5pTw-jLA (ykstool)
https://github.com/AtomCrafty/yukatool

tools:
- use yukatool to unpack/pack archives
- use ykstool to decode/encode script files

known info:
- use yuka pack with -r to keep files in .png format instead of converting
  them to .ykg (converting causes akaneiro trial to crash)
- it's possible to make .ykc (archive) files with only the changed files.
  but it needs to be read before the original files by the game. in other
  words, data01.ykc, data02.ykc etc needs to be renamed to data02.ykc, 03 etc
  and the patch file needs to be named data01.ykc (data00 doesn't work)
- eventually, if there are multiple .ykc files and one of the contains just the
  script, we can replace just that one
- commands that can be used in script:
  - @r(2,か　ほ): furigana, this instance put one hiragana above the last 2
    chars (kanji)

known issues:
- game doesn't wordwrap english sentences automatically. 50 chars per line
  with english text worked for lover able trial1 (the game uses monofont, so
  50 chars will probably always work, but i only tried once to wordwrap).
  \n doesn't work. TODO try 0d or 0a

TODO read the lover able fan translation blog, it has technical info
