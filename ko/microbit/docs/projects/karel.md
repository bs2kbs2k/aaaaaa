# Karel the LED

## ~avatar avatar

카렐(Karel) 을 도와 LED 아트를 만들어보세요!

## ~

**Karel the LED** 에서는 오른쪽으로 회전할 수 없습니다. 하지만, 멋진 LED 아트를 만들 수 있습니다!

![](/static/mb/projects/karel/hi.png "Hi")

이 활동의 목표는 @boardname에 아래에 주어진 자바스크립트 코드를 업로드하는 것입니다. Then use the program to introduce new students to the @boardname@. 이번 활동에서는 프로그램 코딩을 하지 않습니다. 학생들은 보드에 더 익숙한 사용자가 될 것입니다.

## 게임 방법

* `A 버튼` **왼쪽으로 회전**  
    아무 것도 그리지 않고, 카렐(Karel, 반짝이는 LED) 이 움직이는 방향만 바꿉니다.
* `B 버튼` **앞으로 이동**  
    카렐을 이동 방향으로 한 칸 이동시키면서, 지나가는 길에 있는 LED 를 켭니다.
* `흔들기` **점프**  
    카렐을 이동 방향으로 한 칸 이동시키는데, 지나가는 길에 있는 LED 를 끕니다.
* `A+B 버튼` **카렐 숨기기**  
    카렐(반짝이는 LED) 을 보이거나 숨깁니다. LED 아트 작품이 완성되었을 때, 한 번 사용합니다.
* `리셋 버튼` **스크린 화면을 지우고 재시작**  
    프로그램을 재시작시키면서 화면을 지웁니다.

**참고:** 화면을 지울 수 있는 방법은 없습니다. 리셋을 누르면 재시작됩니다.

## 그리고 싶은 패턴들을 그려보세요.

**A**, **B** 버튼과 **흔들기** 를 이용해서 아래 패턴을 그려낼 수 있는지 생각해보세요. 무늬를 다 만들고나면, **A** + **B** 버튼을 동시에 눌러, 카렐을 숨기면 됩니다. 여러 가지 패턴들을 만들기 위해서는, 어떤 LED 를 켜야할 지 생각해야합니다. 그리고, 카렐을 이용해서 그 디자인을 만들어야 합니다.

### 나선 모양

![](/static/mb/projects/karel/spiral.png "Spiral")

### 오른쪽 회전

![](/static/mb/projects/karel/right-turn.png "Right turn")

### 눈

![](/static/mb/projects/karel/eyes.png "Eyes")

### 웃는 얼굴

![](/static/mb/projects/karel/smile.png "Smile")

### 확인 표시

![](/static/mb/projects/karel/check.png "Check")

### 영문 이름 이니셜의 첫 번째 문자

영문 이름 이니셜의 첫 번째 문자를 LED 들로 어떻게 만들 수 있을 지 생각해보세요.

```sim
basic.forever(() => {
    basic.showAnimation(`
    # # # . . # # # . . # # # . . # # # . .
    . . . . . # . . . . # . . . . # . . # .
    . . . . . # . . . . # . . . . # . . # .
    . . . . . # . . . . # . . . . # . . # .
    . . . . . # . . . . # # # . . # # # . .
    `)
    basic.pause(1000)
    basic.clearScreen()
    basic.pause(1000)
})
```

### 만들고 싶은 디자인!

재미있는 모양들을 만들어보세요!

```sim
basic.forever(() => {
    basic.showAnimation(`
    # . . . . # . . . . # . . . . # . . . . # . . . . # . . . .
    . . . . . # . . . . # . . . . # . . . . # . . . # # . # # #
    . . . . . # . . . . # . . . . # . . . . # . . . # # . # . #
    . . . . . # . . . . # . . . . # . . . . # . . . # # . . . #
    . . . . . # . . . . # # # # # # # # # # # # # # # # # # # #
    `)
    basic.pause(1000)
    basic.clearScreen()
    basic.pause(1000)
})
```

Karel the LED 게임을 해주셔서 감사합니다!

## 카렐 LED 코딩하기

아래의 코드를 자바스크립트 편집기에 붙여넣은 후, 보드에 업로드하세요.

**Note:** For this project you need to manually copy the code and insert it into the JavaScript view of the editor.

```typescript
/**
 * Karel the LED
 */
basic.forever(() => {
    if (board.isKarelActive) {
        led.toggle(board.karelX, board.karelY)
        basic.pause(500)
    }
})
input.onButtonPressed(Button.A, () => {
    board.pressedA();
    updateLeds();
})
input.onButtonPressed(Button.B, () => {
    board.pressedB();
    updateLeds();
})
input.onGesture(Gesture.Shake, () => {
    board.shake();
    updateLeds();
})
input.onButtonPressed(Button.AB, () => {
    board.pressedAB();
    updateLeds();
})
function updateLeds() {
    for (let j = 0; j < 5; j++) {
        for (let k = 0; k < 5; k++) {
            if (board.ledState[j][k]) {
                led.plot(k, j);
            } else {
                led.unplot(k, j);
            }
        }
    }
}
const board = new Board();
enum Direction {
    UP = 0,
    LEFT,
    DOWN,
    RIGHT
}
class Board {
    public isKarelActive: boolean;
    public karelX: number;
    public karelY: number;

    public ledState: Array < Array < boolean >>;
    private karelDirection: Direction;

    constructor() {
        this.isKarelActive = true;
        this.karelX = 2;
        this.karelY = 2;
        this.karelDirection = Direction.UP;
        this.ledState =[];
        for (let i = 0; i < 5; i++) {
            this.ledState.push([false, false, false, false, false]);
        }
    }

    pressedA() {
        if (!this.isKarelActive) {
            return;
        }
        this.karelDirection = (this.karelDirection + 1) % 4;
    }

    pressedB() {
        if (!this.isKarelActive) {
            return;
        }
        this.ledState[this.karelY][this.karelX] = true;
        this.moveKarel()
    }

    shake() {
        if (!this.isKarelActive) {
            return;
        }
        this.moveKarel()
    }

    private moveKarel() {
        if (!this.isKarelActive) {
            return;
        }
        switch (this.karelDirection) {
            case Direction.UP:
                if (this.karelY > 0) {
                    this.karelY -= 1;
                }
                break;
            case Direction.LEFT:
                if (this.karelX > 0) {
                    this.karelX -= 1;
                }
                break;
            case Direction.DOWN:
                if (this.karelY < 4) {
                    this.karelY += 1;
                }
                break;
            case Direction.RIGHT:
                if (this.karelX < 4) {
                    this.karelX += 1;
                }
                break;
        }
    }

    pressedAB() {
        this.isKarelActive = !this.isKarelActive;
    }
}
```

## 원작자

This project was contributed by Dr. David Fisher a professor at [Rose-Hulman Institute of Technology](https://www.rose-hulman.edu/academics/faculty/fisher-david-fisherds.html). Dr. Fisher loves educational robotics and runs various outreach programming activities, including a summer camp, called [Connecting with Code](https://connectingwithcode.org), which gives a @boardname@ to each participant.