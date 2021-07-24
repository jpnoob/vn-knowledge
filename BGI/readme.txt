all games
- findings based on hajirabu making lovers promo, kanojo step trial, azasumi

link to tools:
https://github.com/morkt/GARbro
https://github.com/jpnoob/vn-packunpack/tree/main/BGI

tools:
- use garbro to extract script files from .arc files:
- use bgidecode/encode to convert script files to/from .txt

known info:
- script files don't need to be re-packed into archive files, it's sufficient
  to put the files in the game's root directory (not in Archive/)
- i've encountered no issues so far when replacing text. word wrapping of
  english text is handled automatically, i've never seen a word being split in 2
- all text must be in japanese shift-jis (codepage 932)
- the binary script files are in some kind of "assembly language" format:
  - 0x3: pointer to null-terminated string
- text in big font is typically post-fixed by "<". this character is not
  displayed, even when the line is in english. this character is actually not
  even displayed on normal lines

unknown info:
- the binary script files are in some kind of "assembly language" format.
  learn more about it. this seems to be a list of some commands
  https://github.com/mnakamura1337/engine_bgi/blob/master/bytecode/bgi_bytecode_cmds.rb
-------------------------------------------------------------------------------
hajirabu making lovers promo

weird stuff observed that has an explanation:
- hajirabu making lovers promo has "←NEW" in the script, this is part of the
  script and not a command or something
