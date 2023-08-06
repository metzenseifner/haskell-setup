# Haskell

There are overarching two ways of doing it, whereby one actually works on Arch Linux.

1. Installation using ghcup
2. Installation using Arch packages (pacman / pikaur)

# GHCup

https://www.haskell.org/ghcup/

Acquire the Ghcup Binary precompiled for your CPU architecture.

https://downloads.haskell.org/~ghcup/

```
wget https://downloads.haskell.org/~ghcup/0.1.19.5/aarch64-apple-darwin-ghcup-0.1.19.5
```

and put it somewhere and make sure to add a symbolic link appropriately named
`ghcup` to your ~/.local/bin. Assumption is that you have added ~/.local/bin to 
your PATH: `export PATH=~/.local/bin:$PATH`.

```
ln -s ~/haskell/aarch64-apple-darwin-ghcup-0.1.19.5 ~/.local/bin/ghcup
```

Or if you live according to the YOLO philosophy, feel free to trust this:

```
curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh
```


Note that The GHCup website does not use the XDG standard when it suggests
~/.cabal and ~/.ghcup. I would suggest not creating those directories or else backwards 
capatibility will kick in. Use the 
XDG Standard ~/.local/share/ghcup for ghcup and ~/.local/bin for Cabal's `cabal install`
destination and do not create the older directories. 


Install the Haskell compiler, Cabal build/package system, and whatever using
the ghcup terminal UI or manually e.g.

```
ghcup tui
```
