# Linting for SystemVerilog for VSCode on WSL

## Installing Verilator
In WSL, open the terminal and run the following commands:
```
sudo apt update
sudo apt upgrade
sudo apt install git perl python3 make autoconf g++ flex bison
git clone https://github.com/verilator/verilator.git
cd verilator
autoconf
./configure
make -j$(nproc)
sudo apt install help2man
sudo make install
```
Then, run `pwd` (This will give your current path to use in the next command)

Then, run `find {insert your current path} -name verilator` (This will give you the path to verilator to use in step 4 below)

## Setting up Linting in Visual Studio Code
1. In Visual Studio Code, install the extension called **Verilog-HDL/SystemVerilog/Bluespec SystemVerilog**

2. Go to Extensions, and right-click the Verilog extension and click “Settings”

3. Click “Open Settings (JSON)” icon in the top right (looks like a paper icon)

4. Paste this in (and be sure to copy your verilator path into the first line):
```
{
    "verilog.linting.verilator.path": "{insert your verilator path}",
    "workbench.settings.applyToAllProfiles": [
        "verilog.linting.path"
    ],
    "verilog.linting.enabled": true,
    "verilog.linting.verilator.runAtFileLocation": true,

   
    "verilog.linting.linter": "verilator",
    "verilog.linting.verilator.arguments": "--lint-only --timing --Werror-WIDTH -Werror-SELRANGE -Werror-COMBDLY -Werror-LATCH -Werror-MULTIDRIVEN",
    "editor.unicodeHighlight.invisibleCharacters": false,
    "editor.unicodeHighlight.ambiguousCharacters": false,
    "verilog.linting.verilator.useWSL": true
}
```
5.	Save `settings.json`
