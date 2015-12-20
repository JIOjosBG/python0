## Структура

```python
import turtle
import math
import time

# настройки на екрана
window = turtle.Screen()
window.bgcolor('black')
window.tracer(0)

# изчертаване на рамка на игралното поле

FRAME_TIME = 0.01
counter = 0
play_game = True

# създаване на играчите

player = # ...
goal = # ...
bulets = []

# дефиниране на помощни функции за местене, проверка за сблъсък, ...

def quit_game():
    global play_game
    play_game = False

window.listen()
window.onkey(quit_game, 'q')

while play_game:
    start_time = time.clock()
    # преместване на играчите
    # проверка за сблъсъци

    window.update()
    time.sleep(start_time + FRAME_TIME - time.clock())
    counter += 1

window.bye()
```

## Създаване на гериите

Всички герои в играта (както и куршумите) са `Turtle` обекти.
При движението с те обаче не трябва да оставят следа - затова трябва да извикаме
`penup`. Овсен това движението им не е анимирано - затова викаме `speed(0)`.

```python
player = turtle.Turtle()
player.penup()
goal.setposition(0, 0)
goal.speed(0)
```

## Местене и скорост
За преместване се използват познатите методи `forward` и `backword`.
Може да задавате скорост на движение местите героите само през част от циклите
на играта. Например ака местите един герой на всеки 5-ти цикъл, а друг на всеки
цикъл, то вторият ще се движи 5 пъти по бързо.
За целта може да използвате променливата `counter`, в коята се записва кой
по ред цикъл се изпълнява.

## Проверка на позицията и движение в границите на игралното поле
Преди всяко преместване трябва да се проверява дали героят не е границата на
игралното поле. Това може да се направи като се използват `xcor()` и `ycor()`,
които връщат координатите на на героя.

```python
    if PLAYGROUND_SIDE < player.xcor():
        # не може да се премести надясно
        # ще излезе извън игралното поле
```

## Управление с клавиатурата
За да може да упавлявате вашите герои с клавиатурата, дефинирайте функция,
която да се извика при натискане на съответния клавиш.
Наприме този код задава да се вика функция `goleft` при натискане на стрелка
наляво, `goright` при стрелка надясно и `shoot` при натискане на `d`.

```python
def goleft():
    # ...

def goright():
    # ...

def shoot():
    # ...

# Set keyboard bindings
window.listen()
window.onkey(goleft, 'Left')
window.onkey(goright, 'Right')
window.onkey(shoot, 'd')
window.onkey(quit_game, 'q')
```
## Куршуми
Както казахме куршумите също са `Turtle` обектъ. Тъй като те може да се повече
от един е най-лесно да се пазят в списък. Изстрелването на куршум представлява
следните действия:
- създаване на "герой"
- насочването му нагоре
- поставянето му в края на списъка

Тъй като всички куршуми се движат с една и съща скорост, то винаги първият
изстрелян ще стигне до края на игралното поле.
Когато това се случи, трябва да го извадим от списъка и да го премахнем от
екрана.  Това може да направим по следния начин:

```python
bullet.hideturtle()
bullets.pop(0)
```

## Проверка за сблъсъци
За да преверим дали два елемента се сблъскват, трябва да намерим разстоянието
между тях. Използвайте формула за разстояние междо две точки в двумерното
пространство. Ако разстоянието в по малко от някакво число (да речем 5 пиксела),
приемаме, че има сблъск.


(Повече информация за `turtle`](https://docs.python.org/3.4/library/turtle.html#module-turtle)