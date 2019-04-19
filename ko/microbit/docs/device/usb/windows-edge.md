# 윈도용 엣지에서 업로드

How to compile, transfer, and run a program on your micro:bit on **Microsoft Edge**.

While you're writing and testing your programs, you'll mostly be [running them in the simulator](/device/simulator), but once you've finished your program you can **compile** it and run it on your micro:bit.

기본 단계:

1. Connect your @boardname@ to your computer via USB
2. Click **Download** to download the `.hex` file
3. Click the **Save As** button in the bottom bar and save the `.hex` file into the MICROBIT drive

## Requirements

You need the following things to transfer and run a script on your micro:bit:

* 마이크로비트와 컴퓨터를 마이크로(micro) USB 케이블을 이용해 연결합니다. 이 USB 케이블은 스마트폰과 컴퓨터를 사용하는데 사용하는 케이블과 같은 케이블입니다.
* A PC running Windows 7 or later, or a Mac running OS X 10.6 or later

## Step 1: Connect your micro:bit to your computer

First, connect the micro:bit:

1. Connect the small end of the USB cable to the micro USB port on your micro:bit.

2. Connect the other end of the USB cable to a USB port on your computer.

Your computer should recognise your micro:bit as a new drive. On computers running Windows, `MICROBIT` appears as a drive under Devices and drives. On a Mac it appears as a new drive under Devices.

![](/static/mb/device/usb-windows-device.jpg)

## Step 2: Download your program

1. @homeurl@ 에서 프로젝트를 여세요.
2. **다운로드** 클릭
3. When prompted, choose to **save** the compiled file onto your computer. The prompt will be different depending on which browser you are using, or whether you are using a Windows computer or a Mac

A message will appear at the bottom of the browser asking what you want to do with the file.

1. Click **Save As**
2. Save the `.hex` file into the **MICROBIT** drive

## Step 3: Transfer the file to your micro:bit

* The LED on the back of your micro:bit flashes during the transfer (which should only take a few seconds).
* Once transferred, the code will run automatically on your @boardname@. To rerun your program, press the reset button on the back of your @boardname@. The reset button automatically runs the newest file on the micro:bit.

By copying the script onto the `MICROBIT` drive, you have programmed it into the flash memory on the micro:bit, which means even after you unplug the micro:bit, your program will still run if the micro:bit is powered by battery.

## ~hint

Transfer not working? See some [troubleshooting tips](/device/usb/troubleshoot).

## ~