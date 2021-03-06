iCESugar
-----------
[中文](./README.md) [English](./README_en.md)
* [iCESugar](#iCESugar) 
* [Hardware](#hardware)
	* [iCE40UP5K](ice40up5k)
	* [iCELink](icelink)
* [virtual-machine-image](#virtual-machine-image)
* [How-to-setup](#how-to-setup-env)
* [How-to-buy](#how-to-buy)
* [Reference](#reference)

# iCESugar
iCESugar is a FPGA board made by MuseLab, it base on Lattice iCE40UP5k, on board peripheral include RGB LED，Switch，TYPE-C-USB, Micro-USB，most IO out with standard PMOD interface  
the on board debugger iCELink (base on ARM Mbed DAPLink) support drag-and-drop program, you can just drag the FPGA bitstream into the virtual disk to program, iCELink also support USB CDC serial port and JTAG   
![icesugar_render](https://github.com/wuxx/icesugar/blob/master/doc/iCESugar_render.jpg)
![icesugar](https://github.com/wuxx/icesugar/blob/master/doc/iCESugar.jpg)

# Hardware
### iCE40UP5K
1. 5280 Logic Cells (4-LUT + Carry + FF)  
2. 128 KBit Dual-Port Block RAM  
3. 1 MBit (128 KB) Single-Port RAM  
4. PLL, Two SPI and two I2C hard IPs  
5. Two internal oscillators (10 kHz and 48 MHz)  
6. 8 DSPs (16x16 multiply + 32 bit accumulate)  
7. 3x 24mA drive and 3x hard PWM IP  
8. SPI Flash use W25Q64 (8MB)
9. on board switch and RGB LED
10. all IO out with standard PMOD Interface

### iCELink
iCESugar has a on board debugger named iCELink (base on STM32F1)，you can only use one USB wire to program the FPGA and debug, here is detail:   
1. drag-and-drop program, just drop the bitstream into the virtual USB DISK iCELink, then wait a few second, the iCELink firmware will do the total program work
2. USB CDC serial port, it can use to communicate with FPGA
3. support JTAG, you can use it to debug the SoC run on FPGA
4. the MCO can provide 12Mhz clock for FPGA as extern clock.

# virtual-machine-image
link：https://pan.baidu.com/s/1qVSdwM7DnFbaS0xdqsPNrA  
verify code：6gn3  
`user: ubuntu`  
`passwd: ubuntu`  
or
https://mega.nz/file/uvJTWKrK#1bBgBkJPZrszwHQSTHHL-RLjxGIru0Qv0qUgmULZZVs

the env include yosys, nextpnr, icestorm, gcc, sbt.

# How-to-setup-env
recommand use the virtual machine, it simple and convenient  
FPGA toolchain reference [icestorm](http://www.clifford.at/icestorm/)  
gcc toolchain reference [riscv-gnu-toolchain](https://pingu98.wordpress.com/2019/04/08/how-to-build-your-own-cpu-from-scratch-inside-an-fpga/)  
`icesprog` is command tool for iCESugar program，it depend libusb and hidapi  
`$sudo apt-get install libhidapi-dev`  
`$sudo apt-get install libusb-1.0-0-dev`  

# How-to-buy
currently we only has the board on taobao, [iCESugar FPGA Board](https://item.taobao.com/item.htm?spm=a1z10.1-c-s.w4004-21349689053.18.305e20f8cSEvqA&id=614093598737), if you can't buy it from taobao, maybe you can buy it on aliexpress, just search "icesugar fpga" (not official, somebody copy the link and acts as distributor)
# reference
### toolchain
http://www.clifford.at/icestorm/
### examples
https://github.com/damdoy/ice40_ultraplus_examples  
https://github.com/icebreaker-fpga/icebreaker-examples
### SpinalHDL
https://spinalhdl.github.io/SpinalDoc-RTD/SpinalHDL/Getting%20Started/index.html
### iCESugar introduce
https://www.muselab-tech.com/wan-quan-shi-yong-kai-yuan-gong-ju-lian-de-fpgadan-ban/
