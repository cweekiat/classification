# AI-Deck Image Classification

## Dataset
1. Download dataset from [Roboflow](https://universe.roboflow.com/workspace-b5lim/safmc)
2. Extract file into `data` folder.
3. Folder structure:
   - `data/train/class1/`
   - `data/train/class2/`
   - `data/train/class3/`
   - `data/valid/class1/`
   - `data/valid/class2/`
   - `data/valid/class3/`

## Quickstart
1. Clone repository into `aideck-gap8-examples/examples/ai/` folder
2. From a terminal with the docker container, or gap_sdk dev environment, in the `aideck-gap8-examples/` folder, execute:
   - ```docker run --rm -v ${PWD}:/module aideck-with-autotiler tools/build/make-example examples/ai/classification clean model build image```
3. From another terminal (outside of the container), use the cfloader to flash the example if you have the gap8 bootloader flashed AIdeck. Change the [CRAZYFLIE URI] with your crazyflie URI like `radio://0/90/2M/E7E7E7E726`.
   - ```cfloader flash examples/ai/classification/BUILD/GAP8_V2/GCC_RISCV_FREERTOS/target.board.devices.flash.img deck-bcAI:gap8-fw -w radio://0/90/2M/E7E7E7E726```
   - Flashing may appear to be stuck at 99%. However, if the crazyflie automatically reboots at 99%, the flashing is usually completed and you can `Ctrl+C` in the terminal.  
   - Reboot the Crazyflie.

When the example is flashing, you should see the GAP8 LED blink fast, which is the bootloader. The example itself can be noticed by a slow blinking LED. You should also receive the detection output in the cfclient console.

## Custom Model 
1. Download dataset from [Roboflow](https://universe.roboflow.com/workspace-b5lim/safmc).
2. Extract them in `aideck-gap8-examples/examples/ai/classification/`.
3. Run `python3 train_classifier.py`.

                  
