




git clone https://github.com/zmkfirmware/zmk.git
cd zmk

Need to undestand why If I have another official zephyr repo if I need to duplicate this for zmk ?

These are steps that seems to be needed in order to compile a zmk keyboard in case we already have a zephyrproject enviroment

python3 -m venv .venv
source .venv/bin/activate
pip install west
west update

cd zmk/app

west build -d build/swweeep/right --pristine -b "nice_nano_v2" -- -DSHIELD=swweeep_right -DZMK_EXTRA_MODULES="/home/matteo/git/swweeep_36/"

west build -d build/swweeep/left --pristine -b "nice_nano_v2" -- -DSHIELD=swweeep_left -DZMK_EXTRA_MODULES="/home/matteo/git/swweeep_36/"

west build -d build/swweeep/reset --pristine -b "nice_nano_v2" -- -DSHIELD=settings_reset -DZMK_EXTRA_MODULES="/home/matteo/git/swweeep_36/"