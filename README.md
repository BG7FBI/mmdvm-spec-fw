# mmdvm-spec-fw
this is the readme for mmdvm special fw.
connect dual_hs to Rpi；

BOOT0=1 BOOT1=0 reset / or power on；

ssh on pi-star：

rpi-rw

sudo -s

curl -OL https://github.com/BG4TGO/STM32_DVM-fw/releases/download/v1.0.1/stm32-dvm_105.hex

pistar-watchdog.service stop

systemctl stop mmdvmhost.timer

systemctl stop mmdvmhost.service

stm32flash /dev/ttyAMA0

stm32flash -w stm32-dvm_105.hex -v -g 0 /dev/ttyAMA0
