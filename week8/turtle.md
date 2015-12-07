# Turtle

## Как да започнем

```python
# Стъпка 1: Зареждаме модул `turtle`
import turtle

# Стъпка 2: Създаваме "костенурка"
t = turtle.Turtle()

# Стъпка 3: Започваме да рисуваме с нея
t.forward(50)

# Стъпка 4: Край
turtle.done()
```

## Да нарисуваме квадрат

```python
import turtle

t = turtle.Turtle()

t.forward(50) # чертаем линия дълга 50 пиксела
t.right(90) # завъртаме се на 90 градуса

# ...

turtle.done()
```

## Полезни методи

Име | Параметри | Описание
-|-|-
forward | amount | Премества костенурката напред указаният брой пиксели
backward | amount | Премества костенурката назад указаният брой пиксели
right | angle | Завърта костенурката по часовниковата стрелка
left | angle | Завърта костенурката обратно часовниковата стрелка
color | color name | Задава цвета на писалката
position | None | Връща позицията на костенурката
goto | x,y | Премества костенурката на позиция x,y
dot | None | Рисува точка
stamp | None | Рисува косенурка
shape | shapename | Задава формата на курсора ‘arrow’, ‘classic’, ‘turtle’ или ‘circle’

## Задачи

1. Нарисувайте квадрат
2. Нарисувайте триъгълник
3. Нарисувайте петоъгълник
4. Нарисувайте шестоъгълник
5. Дефинирайте функция, която да може да рисува всяка от изредените досега форми