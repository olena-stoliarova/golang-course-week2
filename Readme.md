# Неделя 2

## Задания

Необходимо написать игру, минимум 1 на выбор. Можно реализовать обе.

> Код решения будет проверятся на наличия бездумной копипасты. **Бездумная копипаста вне правил**

Для отрисовки игры в терминале использовать данную библиотеку:
  - https://github.com/gizak/termui/tree/v1 - код
  - https://github.com/gizak/termui/tree/v1/example - примеры использования компонент
  - `go get -u gopkg.in/gizak/termui.v1` - команда в консоле для установки библиотеки в систему
  - https://godoc.org/gopkg.in/gizak/termui.v1 - документация


### 1. Судоку

Требование:
- кнопка или комманда сгеренрировать классическое судоку 9x9 цифр и отображает в консоле
- кнопка или комманда решить отображенное на экране (сгенерированное) судоку.

Описание - https://ru.wikipedia.org/wiki/Судоку

```sh
puzzle:
3 9 4 |     2 | 6 7  
      | 3     | 4    
5     | 6 9   |   2  
------+-------+------
  4 5 |       | 9    
6     |       |     7
    7 |       | 5 8  
------+-------+------
  1   |   6 7 |     8
    9 |     8 |      
  2 6 | 4     | 7 3 5

solved:
3 9 4 | 8 5 2 | 6 7 1
2 6 8 | 3 7 1 | 4 5 9
5 7 1 | 6 9 4 | 8 2 3
------+-------+------
1 4 5 | 7 8 3 | 9 6 2
6 8 2 | 9 4 5 | 3 1 7
9 3 7 | 1 2 6 | 5 8 4
------+-------+------
4 1 3 | 5 6 7 | 2 9 8
7 5 9 | 2 3 8 | 1 4 6
8 2 6 | 4 1 9 | 7 3 5
```

### 2. Жизнь

Описание - https://ru.wikipedia.org/wiki/Игра_«Жизнь»
Еще одно - https://habr.com/post/154015/

Требование:
- при запуске программы начинается развитие жизни

Правила:

Есть «вселенная», представленная в виде квадрата, разбитого на квадратные же поля. Поле может быть пустым, либо на нём может жить клетка. Каждый «день» игры рассчитывается новое поколение клеток по следующим правилам:
на пустом поле, рядом с которым ровно 3 живые клетки, зарождается новая клетка;
если у живой клетки есть 2 или 3 живые соседки, эта клетка продолжает жить;
если соседей меньше 2 или больше 3, клетка умирает (от «одиночества» или от «перенаселённости» соответственно).

Вселенная «тороидальная»: если зайти за её правый край, окажешься на левом, с верхом и низом то же самое.


___

## Обновление репозитория

```sh
git checkout master

git pull base master

git checkout -b week_2
```


## Магия

`\033[` специальные последоватeльность для терминала, `0;0H` и это тоже, вместе они переносять курсор вывода в левый верхний угол терминала, `\x0c` - указывает перезатереть выведенные символы в терминал новыми

```go
// move cursor to left top corner
fmt.Printf("\033[0;0H")
```

``` go
// Clear screen and print field.
fmt.Print("\x0c", ваша_переменная) 
```

## Отладка кода / Debug

### VS Code

1. Установите дебаггер

```go
go get -u github.com/derekparker/delve/cmd/dlv    
```
2. Прочтите это руководство https://medium.com/golang-notes/%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-visual-studio-code-%D0%B4%D0%BB%D1%8F-go-647ea94aa795

### Goland

- Посмотрите это видео [Туториал ](https://www.youtube.com/watch?v=iPBUaDcehJo)

