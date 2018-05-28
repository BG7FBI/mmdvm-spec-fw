# mmdvm-spec-fw

this is the readme for mmdvm special fw.

connect dual_hs to Rpi；

BOOT0=1 BOOT1=0 reset / or power on；
# on board: short BOOT to high (near C35 and middle pin), then short GPIO PIN 40 & 39.

ssh on pi-star：

rpi-rw

sudo -s

curl -OL https://github.com/BG7FBI/mmdvm-spec-fw/releases/download/1.0/mmdvm.hex

pistar-watchdog.service stop

systemctl stop mmdvmhost.timer

systemctl stop mmdvmhost.service

stm32flash /dev/ttyAMA0

stm32flash -w mmdvm.hex -v -g 0 /dev/ttyAMA0

reboot

DONE.
