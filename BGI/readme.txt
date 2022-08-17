all games
- findings based on hajirabu making lovers promo, kanojo step trial, azasumi,
  daitoshokan trial, pure x connect

link to tools:
https://github.com/morkt/GARbro
https://github.com/jpnoob/vn-packunpack/tree/main/BGI
https://github.com/arcusmaximus/EthornellTools
https://web.archive.org/web/20160314220049/http://tlwiki.org/index.php?title=File:Bgi_script_tools.zip

tools:
- use garbro to extract script files from .arc files
- use garbro to extract images from .arc files (save as .png)
- use bgidecode/encode to convert script files to/from .txt
- use Bgi_script_tools to convert script files to/from .txt (v1.69, doesn't work on v1.72)
- use BgiImageEncoder (ethornelltools) to convert .png back to the game's 
  normal image format

known info:
- the changed files don't need to be re-packed into archive files, it's
  sufficient to put the files in the game's root directory (not in Archive/)
- i've encountered no issues so far when replacing text. word wrapping of
  english text is handled automatically, i've never seen a word being split in 2
- all text must be in japanese shift-jis (codepage 932)
- text in big font is typically post-fixed by "<". this character is not
  displayed, even when the line is in english. this character is actually not
  even displayed on normal lines

unsolved stuff:
- i don't know how to change 《選択肢》 that appears in the backlog after a choice
- i can't convert the images (?) in sysgrp.arc (tried in hajirabu making
  lovers promo), i tried bgi-kit/sysgrpconverter, but all resulting .bmp
  images turned out blank. it seems all non-game graphics showing japanese
  text are in this archive

unknown info:
- i used ethornelltools/bgidisassembler to disassemble the ._bp files in
  sysprg.arc. haven't really looked at these files. it also seems bgidecode
  doesn't like these files (and bgidisassembler doesn't like the normal script
  files)
- the binary script files are in some kind of "assembly language" format:
  - 0x3: pointer to null-terminated string
- learn more about the assembly language. this seems to be a list of some commands
  https://github.com/mnakamura1337/engine_bgi/blob/master/bytecode/bgi_bytecode_cmds.rb

QoL improvements that would be nice to have:
- better script decoding/encoding, only extract the actual script+character
  names and don't extract the other commands
  - for v1.69 games, bgi_script_tools dumps less garbage than bgidecode
-------------------------------------------------------------------------------
hajirabu making lovers promo

weird stuff observed that has an explanation:
- hajirabu making lovers promo has "←NEW" in the script, this is part of the
  script and not a command or something
