# embedded-template
A simple template to interface with the RPI Pico C++ SDK

# Project Structure
- This project expects to be placed alongside the pico-sdk directory.
- An example project structure could look like:
```
pico-sdk/ <- pico-sdk from git
test/ <- project directory
```

# Setup Instructions
- Change CMakeLists.txt accordingly
- Build the project and link `compile_commands` for use by the LSP
```
mkdir build
cd build
cmake ..
make
ln -s build/compile_commands.json .
```
