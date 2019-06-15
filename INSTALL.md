Installation of GBDK on Mac OS 10.14.4
--------------------------------------

Follow instructions at:
https://hackaday.io/project/16188-game-boy-cartridge-plus-programmer/log/49145-programming-game-boy-games-on-a-mac-in-2016

Below we paste a copy of the contents of above's URL in case it is not
accesible at some point. All credit to its author.

## Instructions from hackaday.io

First - get homebrew if you haven't.

http://brew.sh/
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

brew install wget
```

Then follow this for installing gbdk, or do what's in the box.

https://github.com/dunn/homebrew-formulae
```
brew tap mistydemeo/formulae
brew install --HEAD mistydemeo/formulae/gbdk
```

Then start a new.c file with your text editor of choice
```
nano new.c
```
and copy this example I borrowed from the credited site

```
// http://www.loirak.com/gameboy/gbprog.php

#include <gb/gb.h>
#include <stdio.h>

void main()
{
        printf("Welcome to GAMEBOY\nProgramming");
        printf("\nPress Start");
        waitpad(J_START);  // other keys are J_A, J_UP, J_SELECT, etc.
        printf("\nIsn't it easy!");
}
```

Run the compiler
```
lcc -o new.gb new.c
```

Lastly, get mGBA to emulate your "game" - example


# Tutorials
http://gbdev.gg8.se/wiki/articles/GBDK_Joypad_Tutorial

http://gbdev.gg8.se/wiki/articles/GBDK_Sprite_Tutorial

http://www.retroisle.com/others/nintendogameboy/Technical/Firmware/dev.php

http://gbdk.sourceforge.net/guidelines.html

http://swelectronics.co.uk/Gameboy/images/Opcodes.htm

http://fms.komkon.org/GameBoy/Tech/Hardware.html
