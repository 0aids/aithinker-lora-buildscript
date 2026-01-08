# Setup the environment
0. Required packages:
    ```
    gcc-arm-embedded
    python313
    screen
    cmake
    make
    ```
    OR if you have nix
    ```bash
    nix develop
    ```

1. Clone the repo with recursive cloning.
    ```bash
    git clone --depth=1 https://github.com/0aids/aithinker-lora-buildscript.git
    cd aithinker-lora-buildscript
    git submodule update --init
    ```

2. Setup the python venv environment, and install required packages
    ```bash
    python -m venv venv
    source venv/bin/activate
    python -m pip install configparser pyserial
    ```

# Building and flashing

1. Enter the python venv
    ```bash
    source venv/bin/activate
    ```

2. Build the binary
    ```bash
    make
    ```

3. Flash the lora module (change the usb0 to be whatever the lora module is connected to).
    ```bash
    python tremo_loader.py -p /dev/ttyUSB0 -b 921600 flash 0x08000000 build/main.bin
    ```
