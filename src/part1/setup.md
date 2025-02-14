# Setup

First, we should set up our dev environment.
We will need:

1. A POSIX environment
2. [RGBDS](https://rgbds.gbdev.io/install) v0.5.1 (though v0.5.0 should be compatible)
3. GNU Make (preferably a recent version)
4. A code editor
5. A debugging emulator

::: tip:❓😕

The following install instructions are provided on a "best-effort" basis, but may be outdated, or not work for you for some reason.
Don't worry, we're here to help: [ask away in GBDev](../index.md#feedback), and we'll help you with installing everything!

:::

## Tools

### Linux & macOS

Good news: you're already fulfilling step 1!
You just need to [install RGBDS](https://rgbds.gbdev.io/install), and maybe update GNU Make.

#### macOS

At the time of writing this, macOS (up to 11.0, the current latest release) ships a very outdated GNU Make.
You can check it by opening a terminal, and running `make --version`, which should indicate "GNU Make" and a date, among other things.

If your Make is too old, you can update it using [Homebrew](https://brew.sh)'s formula [`make`](https://formulae.brew.sh/formula/make#default).
At the time of writing, this should print a warning that the updated Make has been installed as `gmake`; you can either follow the suggestion in order to use it as your "default" `make`, or use `gmake` instead of `make` in this tutorial.

#### Linux

Once RGBDS is installed, open a terminal and run `make --version` to check your Make version (which is likely GNU Make).

If `make` cannot be found, you may need to install your distribution's `build-essentials`.

### Windows

The sad truth is that Windows is a terrible OS for development; however, you can install environments that solve most issues.

On Windows 10, your best bet is [WSL](https://docs.microsoft.com/en-us/windows/wsl).
Install WSL 1 or WSL 2, install a Linux distribution, and then follow these steps again, but for the Linux distribution you installed.

If WSL is not an option, you can use [MSYS2](https://www.msys2.org) or [Cygwin](https://www.cygwin.com) instead; then check out the bottom of [RGBDS' Windows install instructions](https://rgbds.gbdev.io/install/windows).
As far as I'm aware, both of these provide a sufficiently up-to-date version of GNU Make.

## Code editor

Any code editor is fine; I personally use [Sublime Text](https://www.sublimetext.com) with its [RGBDS syntax package](https://packagecontrol.io/packages/RGBDS); however, you can use any text editor, including Notepad, if you're crazy enough.
Awesome GBDev has [a section on syntax highlighting packages](https://gbdev.io/list.html#syntax-highlighting-packages), see there if your favorite editor supports RGBDS.

## Emulator

Using an emulator to play games is one thing; using it to program games is another.
The two aspects an emulator must fulfill to allow an enjoyable programming experience are:
- **Debugging tools**:
  When your code goes haywire on an actual console, it's very difficult to figure out why or how.
  There is no console output, no way to `gdb` the program, nothing.
  However, an emulator can provide debugging tools, allowing you to control execution, inspect memory, etc.
  These are vital if you want GB dev to be *fun*, trust me!
- **Good accuracy**:
  Accuracy means "how faithful to the original console something is".
  Using a bad emulator for playing games can work (to some extent, and even then...), but using it for *developing* a game makes it likely to accidentally render your game incompatible with the actual console.
  For more info, read [this article on Ars Technica](https://arstechnica.com/?post_type=post&p=44524) (especially the "An emulator for every game" section at the top of page 2).
  You can compare GB emulator accuracy on [Daid's GB-emulator-shootout](https://daid.github.io/GBEmulatorShootout/).

The emulator I will be using for this tutorial is [BGB](https://bgb.bircd.org) (1.5.9 when I'm writing this).
It's Windows-only, but macOS and Linux users can install Wine to be able to run it, and macOS users will additionally have to use the 64-bit version.
Other debugging emulators are possible (such as [Emulicious](https://emulicious.net/) on any OS, or [SameBoy](https://sameboy.github.io/) on macOS), but I will be giving directives for and including screenshots of BGB.
