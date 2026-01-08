# Steps for building
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
    git clone --recursive --depth=1 https://github.com/0aids/aithinker-lora-buildscript.git
    ```

2. Setup the python venv environment, and install required packages
    ```bash
    python -m venv venv
    source venv/bin/activate
    python -m pip install configparser pyserial
    ```

3. Build the binary
    ```bash
    make
    ```

4. Flash the lora module
    ```bash
    python tremo_loader.py -p /dev/ttyUSB0 -b 921600 flash 0x08000000 build/main.bin
    ```
