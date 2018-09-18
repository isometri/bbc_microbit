# bbc_microbit
BT mesh with bbc_microbit

Initialize toolchains and environment for Mac OS

//Download gnu
https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads
//Extract and put this in your user folder

export GNUARMEMB_TOOLCHAIN_PATH=“~/gcc-arm-none-eabi-7-2018-q2-update/”
export ZEPHYR_TOOLCHAIN_VARIANT=gnuarmemb

sudo pip install --pre -U pyocd

git clone https://github.com/zephyrproject-rtos/zephyr.git
unset ZEPHYR_SDK_INSTALL_DIR
cd zephyr
source zephyr-env.sh
cd samples/hello_world
mkdir build && cd build
cmake -GNinja -DBOARD=bbc_microbit ..
ninja

In Finder find build->zephyr->zephyr.hex
