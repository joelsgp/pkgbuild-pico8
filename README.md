# PICO-8 pkgbuild

This is an Arch Linux makepkg build file for the PICO-8 fantasy console.

It's not on the aur because you have to buy the softare. This is just an install helper. Use it like so:

```bash
git clone https://github.com/joelsgp/pkgbuild-pico8
cd pkgbuild-pico8
# Download PICO-8 from where you bought it
mv ~/Downloads/pico-8_0.2.4c_amd64.zip .
makepkg -si
```

Only supports amd64.

Footnote: there's an existing pkgbuild but also it's on the aur and I don't know how he hell it works, looks complicated. See here: <https://gist.github.com/Addisonbean/538b4fa815b3a02dc6653538f026ee78> <https://aur.archlinux.org/packages/pico-8>
