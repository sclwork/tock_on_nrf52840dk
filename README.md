# Tock rust OS on nrf52840dk

## Kernel

### Rust (nightly)
```bash
curl https://sh.rustup.rs -sSf | sh
rustup install nightly-2022-03-22
```

### JLinkExe
JLink is available from the [Segger](https://www.segger.com/downloads/jlink) website. You want to install the "J-Link Software and Documentation Pack". 
There are various packages available depending on operating system. We require a version greater than or equal to 5.0.

### Openocd
```bash
sudo apt-get install openocd
```

### Tockloader
```bash
pip3 install --upgrade tockloader --user
```

### Tock OS
```bash
git clone git@github.com:tock/tock.git
cd tock/boards/nordic/nrf52840dk
make
make install
```

## Application

### toolchain
```bash
sudo apt install gcc-arm-none-eabi
```

### libtock-c
```bash
git clone https://github.com/tock/libtock-c
cd libtock-c/examples
./build_all.sh
```

### install
```bash
tockloader install --board nrf52dk --jlink blink/build/blink.tab
```

### uninstall
```bash
tockloader uninstall --board nrf52dk --jlink blink
```

### remove all installed applications
```bash
tockloader uninstall --board nrf52dk --jlink
```

