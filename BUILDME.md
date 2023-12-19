## clone the official repository

```sh
git clone https://gitlab.freedesktop.org/xorg/xserver
cd xserver
```

## align the xserver to my ubuntu

```sh
sudo Xorg -version

git checkout xorg-server-1.20.13
```

## get all dependencies for the source

```sh
sudo apt build-dep xorg-server
```

## build only Xephyr

```sh
meson build -Dxephyr=true -Dxorg=false -Dxwayland=false -Dxwayland_eglstream=false -Dglamor=false -Dxnest=false -Ddmx=false -Dxvfb=false -Dxwin=false
ninja -C build
```

## pack exec

```sh
upx build/hw/kdrive/ephyr/Xephyr
```

## the Xephyr binary path: 

```sh
ls -l build/hw/kdrive/ephyr/Xephyr
```

## clean all and rebuild

```sh
meson setup --wipe build -Dxephyr=true -Dxorg=false -Dxwayland=false -Dxwayland_eglstream=false -Dglamor=false -Dxnest=false -Ddmx=false -Dxvfb=false -Dxwin=false
ninja -C build
```

