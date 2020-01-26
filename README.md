# Switch-Fightstick
[![Thumbnail](https://i.imgur.com/cJLZUdhl.jpg)](https://twitter.com/ebith/status/954858876028907521)
- [Xenoblade Chronicles 2](https://twitter.com/ebith/status/954858876028907521)
- [Octopath Traveler](https://twitter.com/ebith/status/1079163336862818305)

## Base repos

- [ebith/Switch-Fightstick](https://github.com/ebith/Switch-Fightstick)
- [progmem/Switch-Fightstick](https://github.com/progmem/Switch-Fightstick)

## Requirement
- ATMega32U4 Board or see [shinyquagsire23/Switch-Fightstick's README](https://github.com/shinyquagsire23/Switch-Fightstick/blob/master/README.md)
- USB to serial adapter
- USB micro-b cable * 2

## Usage
[NintendoSwitchをPCから操作する - おいら屋ファクトリー](https://blog.feelmy.net/control-nintendo-switch-from-computer/)(in Japanese)

### Features added

Macro Function to press `A`.
It works works without connection with PC

`send('LOOP')`

### On MacOS
```sh
brew install avr-dude osx-cross/avr/avr-gcc
git clone --recursive https://github.com/ebith/Switch-Fightstick.git
cd Switch-Fightstick
make
avrdude -pm32u4 -cavr109 -D -P$(ls /dev/tty.usbmodem*) -b57600 -Uflash:w:Joystick.hex # need reset

pip3 install pyserial
./example/rapid-fire-a-button.py /dev/tty.usbserial*
```
