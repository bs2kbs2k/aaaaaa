# 학습 활동: 프로그램 설치하기

**마이크로비트 학습 활동:** Microsoft 메이크코드(MakeCode)에서 만든 프로그램을 마이크로비트에 업로드하기

**Objective:** Learn how to download programs from the MakeCode tool.

**Overview:** Students will create a simple program in Microsoft MakeCode and download it to their micro:bit using a USB cable.

For this activity, students will each need a micro:bit, a micro-USB cable, a computer, and a battery pack.

![micro:bit kit](/static/courses/csintro/making/microbit-kit.jpg)

Open a browser window to [makecode.com](http://makecode.com), and select the micro:bit code editor

![마이크로비트 카드 아이콘](/static/courses/csintro/making/microbit-card-icon.png)

From the top left corner of the screen, select the **Projects** Menu, and click on **Import File**. Select the file that you saved on your computer in the previous step.

![Projects folder](/static/courses/csintro/making/projects-folder.png)

![Import file](/static/courses/csintro/making/import-file.png)

The program should look like the following in MakeCode. It shows a repeating series of faces:

```blocks
basic.forever(() => {
   basic.showIcon(IconNames.Happy)
   basic.pause(5000)
   basic.showIcon(IconNames.Sad)
   basic.pause(5000)
})
```

## Microsoft 메이크코드(MakeCode) 둘러보기

* **Simulator** - on the left side of the screen, you will see a virtual micro:bit that will show what your program will look like running on a micro:bit. 프로그램 오류를 찾아내고 수정하는 디버깅, 프로그램 실행 결과를 바로 확인해 즉각적인 피드백을 줄 수 있는 것에 매우 큰 도움이 됩니다.
* **Toolbox** - in the middle of the screen, there are a number of different categories, each containing a number of blocks that can be dragged into the programming workspace on the right.
* **Workspace** - on the right side of the screen is the Programming Workspace where you will create your program. Programs are constructed by snapping blocks together in this area.

![IDE tour](/static/courses/csintro/making/ide-tour.png)

The color of the blocks identifies their category. All of the blocks that make up the program above come from the **Basic** Toolbox category, which is light blue.

## Downloading a MakeCode program to the micro:bit

To download the file to your micro:bit, you must connect it to your computer’s USB port using a micro-USB cable. 마이크로비트와 컴퓨터 사이에 연결한 USB 연결을 끊으면, 전원도 함께 끊어지게 됩니다. 컴퓨터와 연결되지 않았을 때, 전원을 공급해 실행시키려면, 배터리 팩과 같은 것을 연결시켜야 합니다. Once plugged in, the micro:bit shows up on your computer like a USB flash drive.

![USB 연결](/static/courses/csintro/making/microbit-usb.jpg)

Click the purple Download button in the lower left of the MakeCode screen. This will download the file to your computer, to the location where your browser is set to save downloads.

![다운로드 버튼](/static/courses/csintro/making/download-button.png)

To move the program to your micro:bit, drag the downloaded "microbit-xxxx.hex" file to the MICROBIT drive, as if you were copying a file to a flash drive. The program will copy over, and it will begin running on the micro:bit immediately.

![micro:bit drive](/static/courses/csintro/making/microbit-drive.jpg)

The micro:bit will hold one program at a time. It is not necessary to delete files off the micro:bit before you copy another onto the micro:bit; a new file will just replace the old one.

For the next project, your students should attach the battery pack (it takes 2 AAA batteries) to the micro:bit using the white connector. That way they can build it into their design without having to connect it to the computer.

![Battery pack](/static/courses/csintro/making/battery-pack.jpg)