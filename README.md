# Alefir's build of st - the simple (suckless) terminal

Forked from[https://github.com/Lukesmithxyz/st](http://github.com/Lukesmithxyz/st) which was forked from [https://github.com/shiva/st](https://github.com/shiva/st) for simplicity's sake, which is the [suckless terminal (st)](https://st.suckless.org/) with some patches added:

+ copy to clipboard
+ solarized colors (light and dark toggleable)
+ vertcenter
+ scrollback with keyboard
+ scrollback with mouse

## My own additions

+ Set default font to Iosevka Term Slab at 13pt
+ Set default opacity
+ Add `-b` option to decrease opacity
+ Set default colours to my personal scheme
+ Change default modifier from Alt to Ctrl
+ Set cursor to go invisible when typing

## Lukesmithxyz's own additions

+ Fixed transparency patch (see below for installation)
+ Ctrl-k and Ctrl-j scroll back/foward in history one line at a time
+ Ctrl-u and Ctrl-d scroll back/foward in history a page at a time

## Terminal-specific mappings

(Additions before me.)

+ Scroll through history -- Shift+PageUp/PageDown or Shift+Mouse wheel
+ Increase/decrease font size -- Shift+Alt+PageUp/PageDown
+ Return to default font size -- Shift+Alt+Home
+ Paste -- Shift+Insert

## Installation for newbs

```
make
sudo make install
```

### Transparency

If you want transparency, run the following. (You will also need to have a composite manager, such as compton or xcompmgr running for the transparency to appear.)

```
make clean
patch < patches/transparency.diff
make
sudo make install
```

And to remove transparency, just unapply the diff patch and reinstall.

```
make clean
patch -R < patches/transparency.diff
make
sudo make install
```

You can change the transparency value by changing the `alpha` variable in the `config.h` file.
