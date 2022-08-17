all games
- findings based on looking at aikagi 2 trial, aibeya trial, aikagi 3,
  imouto spiral trial

link to tools:
https://github.com/morkt/GARbro

tools:
- use garbro to extract script files from .pfs files (in script/ or scenario/
  directory) 

known info:
- script files don't need to be re-packed into archive files, the game can read
  loose files as long as they are put in the correct directory
- script files are in plaintext .ast files, easily editable (akiagi 2/aibeya)
- script files are in plaintext .txt files (imouto spiral)
-------------------------------------------------------------------------------
aikagi 2/aikagi 3/aibeya
- stuff looks so edit-friendly in general that i wouldn't be
  surprised if it is feasible to create a visual novel from scratch
- the script format puts every line of the script into double quotes. to use
  double quotes in the actual text, use backslash as escape code
  (like "\"This text is quoted.\"")
- word wrapping seems to be done automatically. though the script file has
  a mechanism for breaking single lines manually (and aikagi 2 does that a lot).
  it's also possible to use \n
- image files are in .png, also easily editable, which means we can edit stuff
  like the title screen, options screen etc
- seems we can add/change splash screens (and voice lines played during them)
  by editing script/brandlogo.ast
- can't add comments with semicolon (i tried in aikagi 3, the game crashed)
-------------------------------------------------------------------------------
imouto spiral trial

TODO only took a super-quick look, was able to change text
-------------------------------------------------------------------------------
ixshe tell

known issues:
- images are encrypted/obfuscated or something
