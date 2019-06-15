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


Installation on Ubuntu 18.04.2 LTS
----------------------------------

## GBDK installation

### Method 1: Official GBDK installation

1. Download the latest release from http://gbdk.sourceforge.net/. In this case, `gbdk-2.96a-i586-pc-linux2.2.tar.gz`.
2. Extract the compressed file (Presuming that the file was downloaded to `$HOME/Downloads` directory):
```
$ tar xzf $HOME/Downloads/gbdk-2.96a-i586-pc-linux2.2.tar.gz -C $HOME/
```
3. Move the `gbdk` folder to a permanent directory like `/opt`:
```
sudo mv gbdk /opt/gbdk
```

### Method 2: Instructions from gheja/gbdk repository

Follow instructions from https://github.com/gheja/gbdk.

Below we paste an adapted copy of the contents of above's URL in case it is not
accesible at some point. All credit to its author.

First, install the required packages:

```
sudo apt-get -y install make gcc g++ bison flex
```

Then, proceed to compile the binaries using the Makefile located
in the root folder of the cloned repo:

```
sudo make install
```

## Export binaries folder

After completing either method 1 or 2, add the `bin` folder to `PATH` environment variable. Edit the `$HOME/.bashrc` file (or equivalent, if that is the case) and include the following:
```
# GameBoy Development Kit

PATH=/opt/gbdk/bin:$PATH
```

To check if this binary is accessible from any directory, run the following command:
```
$ lcc -v
```

If the steps have been successful so far, the result will be similar to this one:

```
lcc $Id: lcc.c,v 1.6 2001/10/28 18:38:13 michaelh Exp $
```

## Testing GBDK installation: Hello World

We are creating a simple example to check everything is working. We will use the **mGBA** emulator, available from Snap package manager:
```
sudo snap install mgba
```

Let's create a blank file using our favorite text editor. This is a simple example adapted from [mrombout/gbdk_playground](https://github.com/mrombout/gbdk_playground) repository:

```
// ## Hello World example ##
// It shows a welcome text, then ask the player
// to press Start button to show a confirmation message.

#include <gb/gb.h>
#include <stdio.h>

void main() {

    printf("Hello World!");

    printf("\n\nPress Start");
    waitpad(J_START);

    printf("\nLet's go!");

}
```

Run the compiler
```
lcc -o new.gb new.c
```

# Tutorials

http://www.fasebonus.net/foro/index.php?topic=36662.0

https://www.elotrolado.net/hilo_desarrollo-software-proyectos-de-darkryoga_1901847

http://wiki.ladecadence.net/doku.php?id=tutorial_de_ensamblador

http://www.retroisle.com/others/nintendogameboy/Technical/Firmware/dev.php

http://gbdev.gg8.se/wiki/articles/GBDK_Joypad_Tutorial

http://gbdev.gg8.se/wiki/articles/GBDK_Sprite_Tutorial

http://www.retroisle.com/others/nintendogameboy/Technical/Firmware/dev.php

http://gbdk.sourceforge.net/guidelines.html

http://swelectronics.co.uk/Gameboy/images/Opcodes.htm

http://fms.komkon.org/GameBoy/Tech/Hardware.html
