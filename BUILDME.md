# clone the official repository
git clone https://gitlab.freedesktop.org/xorg/xserver
cd xserver

# align the xserver to my ubuntu
git checkout xorg-server-1.20.13

# get all dependencies for the source
sudo apt build-dep xorg-server

# build only Xephyr
meson build -Dxephyr=true -Dxorg=false -Dxwayland=false -Dxnest=false -Ddmx=false -Dxvfb=false -Dxwin=false
ninja -C build

# the Xephyr binary path: 
ls -l build/hw/kdrive/ephyr/Xephyr

# clean all and rebuild
meson setup --wipe build -Dxephyr=true -Dxorg=false -Dxwayland=false -Dxnest=false -Ddmx=false -Dxvfb=false -Dxwin=false
ninja -C build

