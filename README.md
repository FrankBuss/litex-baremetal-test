# litex-baremetal-test

Ported to MAX1000 by Frank Buss

How to run it: compile it and start the upload process:
```    
lxterm --serial-boot --kernel test.bin /dev/ttyUSB0
```

In a second shell, go to the litex-boards/litex_boards/partner/targets directory and start the FPGA configuration:
    
```
quartus_pgm -m jtag -o "p;soc_basesoc_max1000/gateware/top.sof"
```
or configure it from the GUI programmer. The upload in the first shell will automatically start and you will see something like this:
```
 BIOS CRC passed (692f01bc)

 Migen git sha1: 94db729
 LiteX git sha1: 9c3c43c9

--=============== SoC ==================--
CPU:       VexRiscv @ 50MHz
ROM:       32KB
SRAM:      4KB
L2:        8KB
MAIN-RAM:  8192KB

--========== Initialization ============--
Initializing SDRAM...
SDRAM now under hardware control
Memtest OK

--============== Boot ==================--
Booting from serial...
Press Q or ESC to abort boot completely.
sL5DdSMmkekro
[LXTERM] Received firmware download request from the device.
[LXTERM] Uploading test.bin to 0x40000000 (360 bytes)...
[LXTERM] Upload complete (7.9KB/s).
[LXTERM] Booting the device.
[LXTERM] Done.
Executing booted program at 0x40000000

--============= Liftoff! ===============--
Hello World!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
hello World again!
The end.
```
