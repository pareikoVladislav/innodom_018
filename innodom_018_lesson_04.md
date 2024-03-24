# **Basic constructions**

# **Comparison operators**

**Операторы сравнения** - это операторы, которые сравнивают между собой\
два значения и возвращающие результат типа `bool` ( **True** \ **False** ).


Сравнивать можно:
* **логический тип**
* **строки**
* **числа**
* **переменную на пустоту**

Со строками при этом есть интересная особенность при сравнениях:

```python
"qwe" < "qwer"
```

В Python при сравнении строк сравнение происходит **лексикографически**,\
то есть сравниваются символы на соответствующих позициях в строках\
поочередно, начиная с первого символа. Если символы на одной позиции\
равны, то сравниваются следующие символы, и так далее, пока не будет\
найдено различие или одна из строк не закончится.

**В нашем примере:**

"`q`" сравнивается с "`q`" - **они равны**.\
Затем "`w`" сравнивается с "`w`" - **они тоже равны**.

На этом этапе одна из строк, "`qwe`", заканчивается, но другая строка,\
"`qwer`", еще не закончилась.

Так как до этого момента все символы совпали, **Python** продолжит сравнение,\
и так как "`qwer`" еще имеет символы, она считается большей, чем "`qwe`".\
Поэтому выражение "`qwe`" < "`qwer`" вернет значение `True`.

То есть, при сравнении строк в **Python**, длина строк имеет значение только в\
случае, если все символы на соответствующих позициях равны.

```python
"abcd" < "abce"
```

```python
True == False
"qwe" == "QWE"
25 >= 24.4
```

---

Какие операторы сравнения бывают:

* `>` - Проверяет, больше ли левое выражение. Если да - `True`, если нет - `False`
* `<` - Проверяет, меньше ли левое выражение. Если да - `True`, если нет - `False`
* `>=` - Проверяет, больше или равно левое выражение относительно правого.\
Если да - `True`, если нет - `False`
* `<=` - Проверяет, меньше или равно левое выражение относительно правого.\
Если да - `True`, если нет - `False`
* `==` - Проверяет равны ли выражения. Если да - `True`, если нет - `False`
* `!=` - Проверяет равны ли выражения. Если нет - `True`, если да - `False`


Разберём примеры со всеми этими операторами:

```python
print(5 > 3)
print(True == False)
print((10 * .9) > (100 // 99.))
print(-10 != -1)
print(["A", "b", "c"] > ["a", "B", "c"])
```

---

# **Logical operators**

Логические операторы используются для выполнения логических операций, таких\
как **сравнение значений** и **комбинирование условий**.

Какие операторы у нас имеются:

* `not` - Логический оператор "не"
* **`and` - логическое "И". Используется, когда нам нужно проверить несколько**\
условий сразу. Логическое "И" запинается на лжи ( если хоть одно из условий\
`False`, вернёт `False`. Если оба значения `False`, просто вернёт\
последнее значение `False` )
* `or` - Логическое "Или". Так же используется, когда нам нужно проверить несколько\
условий сразу. Логическое "Или" запинается на правде ( если хоть одно из значений\
`True` - вернёт `True`. Если оба значения `True`, или `False` - вернёт\
последнее значение )


Где мы можем применять эти операторы:

* **Условные операторы**: часто используются в условных операторах, таких как\
`if`, `elif` и `else`, для проверки условий и принятия решений на основе результата.
* **Циклы**: также наши операторы могут использоваться в циклах, таких как\
`while` и `for`, для проверки условий продолжения выполнения цикла.
* **Функции и выражения**: Логические операторы также могут использоваться в функциях\
и выражениях для создания булевых (логических) значений. Например, операторы\
`and`, `or` и `not` могут быть использованы для комбинирования и инвертирования\
булевых значений и выполнения различных операций на основе этих значений.

```python
print([1, 2, 3] == [1, 2, 3] and 3 in [1, 2, 3])

print("dEfG" == "dEjO" or ["23", 1, -2] not in [97, "nickname", [23, "-2"]])
```

**Операторы принадлежности**

**Операторы принадлежности** в Python используются в различных контекстах\
для проверки условий

* `is` - используется для проверки, указывает ли один объект на тот же участок\
памяти, что и другой объект. Он сравнивает идентичность объектов, а не их значения.
* `in` - Проверяет, принадлежность элемента x к последовательности \ коллекции\
(Находится ли подстрока в общей строке, находится ли какой-то ключ в словаре и т.д.)
* `not in` - является отрицанием оператора `in`. Он используется для проверки\
отсутствия элемента в коллекции или последовательности. Он возвращает `True`,\
если элемент отсутствует, и `False` в противном случае.

Операторы `is`, `in` и `not in` позволяют выполнять проверки на идентичность\
объектов и принадлежность элементов к коллекциям или последовательностям в `Python`:


```python
a = 15
b = a

print(a, b)
print(id(a), id(b))

print(b is a)
```

```python
list_1 = ["1", [1, 2, 3], 45]

print(2 not in list_1)
tuple_1 = (1, 2, "4", "abc", (1, 2, 3))
print("abc" in tuple_1)

# Более сложный уровень

dict_1 = {
    "a": 1,
    "b": 2,
    "c": 3,
}
print("a" in dict_1 and dict_1.get("a") == 1)
```

# **Branching operators**

**Операторы ветвлений** используются для принятия решений в программе на\
основе условий. Они позволяют программе выполнить определенные блоки кода\
только при выполнении определенных условий, что делает программу\
более гибкой и адаптивной.

Они могут встречаться в различных областях разработки, вот несколько примеров:


* **Управление потоком программы**: Операторы ветвления позволяют контролировать\
поток выполнения программы, определяя, какие части кода будут выполнены в\
зависимости от условий. Например, в зависимости от значения переменной можно\
выполнить определенные действия или перейти к другому блоку кода.

* **Обработка ошибок**: Так же можно использовать наши операторы для обработки\
исключений и ошибок в программе. Они позволяют определить, какая часть кода будет\
выполнена при возникновении определенной ошибки, и принять соответствующие\
меры для ее обработки.

* **Валидация пользовательского ввода**: проверка и валидация введенных пользователем\
данных. Например, мы можем проверить, является ли введенное значение числом\
или строкой, и выполнить различные действия в зависимости от результата.


По ветвлениям мы можем выделить две основные группы наших операторов:

* **Условные операторы**
* **Обработчики ошибок**

Давайте по порядку

---

# **Conditional statements**

* `if` - позволяет выполнить определенный набор инструкций в зависимости от\
некоторого условия. Если условие верно, выполняется блок кода, который\
определён внутри этого условия. Иначе этот блок кода пропустится.

* Как это работает:

```
if условие:
    инструкция_1
    инструкция_2
    ...
    инструкция_n
```

После оператора `if` записывается выражение. Если это выражение истинно, то\
выполняются инструкции, определяемые данным оператором. Выражение является\
истинным, если его результатом является число не равное нулю, непустой объект,\
либо логическое True. После выражения нужно поставить двоеточие “:”

```python
user_input = int(input("Enter your age: "))

if user_input and user_input > 18:
  print("Вы совершеннолетний!")
```

* `if – else` - Используется для выполнения одного блока кода, если условие\
истинно, и другого блока кода, если условие ложно.

Бывают случаи, когда необходимо предусмотреть альтернативный вариант выполнения\
программы. Т.е. при истинном условии нужно выполнить один набор инструкций,\
при ложном – другой. Для этого используется конструкция `if – else`

```
if выражение:
    инструкция_1
    инструкция_2
    ...
    инструкция_n
else:
    инструкция_a
    инструкция_b
    ...
    инструкция_x
```

Условие такого вида можно записать в строчку, в таком случае оно будет\
представлять собой [тернарное выражение](https://ru.wikipedia.org/wiki/%D0%A2%D0%B5%D1%80%D0%BD%D0%B0%D1%80%D0%BD%D0%B0%D1%8F_%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%BD%D0%B0%D1%8F_%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D1%8F)

```python
b = True if 15 > 10 else False
print(b)
```

```python
user_input = int(input("Enter your age: "))

if user_input and user_input > 18:
  print("Вы совершеннолетний!")
else:
    print("Вы ещё слишком маленький!")
```

```python
grade = 85
if grade >= 90:
    print("Отлично!")
elif grade >= 70:
    print("Хорошо!")
else:
    print("Плохо.")
```

```python
user_input_1 = int(input("Enter the number: "))

if user_input_1 and user_input_1 <= 10:
  print(user_input_1 ** 2)
else:
  print("Something went wrong")
```

```python
b = "NO" if 15 < 10 else "YES" # тернарный оператор
print(b)
```

* `if – elif – else` - Можно использовать для реализации выбора из\
нескольких альтернатив


```python
a = int(input("введите число:"))
if a < 0:
   print("Neg")
elif a == 0:
   print("Zero")
else:
   print("Pos")
```

```python
us_account = ("Vladislav", -8749113157394717377) # superkiller2003

username = input("Enter your name: ")
us_password = input("Enter your password: ")

if username and us_password:
    if username == us_account[0]:
        if hash(us_password) == us_account[1]:
            print(f"Welcome, {username}!")
        else:
            print("Wrong password")
    else:
        print(f"User '{username}' doesn't exist")
else:
    print("You must provide your name and password")
```


# **raise**

`raise` используется для вызова исключения, что позволяет программе обработать\
ошибку или иное нежелательное событие. Это не всегда связано с `if-elif-else`,\
но может быть использовано внутри этих конструкций для управления ошибками.

```python
age = -5
if age >= 0:
    print("Возраст положительный")
else:
    raise ValueError("Возраст не может быть отрицательным!")
```

**Немного примеров**

```python
is_raining = True

if is_raining:
    print("Возьмите зонтик")
else:
    print("Зонтик не нужен")
```

Как видите, дополнительная конструкция `raise` позволяет нам обрабатывать\
как-то ожидаемые ошибки. Как и что должно произойти, что должно вывестись\
на экран, если ни одно из условий не сможет отработать и в нашей логике\
в теории может быть какая-то ошибка. Если мы можем "предсказать", что за\
ошибка будет в нашем коде - мы можем её прописать и в скобках вывести какое-то
более подробное описание этой ошибки.


Для работы с ошибками в языке Python существует более удобная конструкция, которая\
как раз и предназначена именно для этой работы.

---


# **try - except**

**Обработчики исключений**

Исключениями (**exceptions**) в языках программирования называют проблемы,\
возникающие в ходе выполнения программы. Типичным примером исключения является\
деление на ноль, попытка вычислений между разными типами данных, невозможность\
считать данные из устройства, отсутствие доступной памяти, доступ к\
закрытой области памяти и т.п.

Для обработки таких ситуаций, как правило, предусматривается специальный\
механизм, который как раз и называется обработка исключений.

Такая конструкция определяется как `try - expect`

```python
a = [1, 2, 3]

try:
  print(a / 8)
except TypeError:
  print("Нельзя производить математические операции между категорически разными типами данных")
```

Рассмотрим иерархию встроенных в python исключений, хотя иногда вам могут\
встретиться и другие, так как программисты могут создавать собственные исключения.\
Данный список актуален для python 3.3 и выше, в более ранних версиях\
есть незначительные изменения:

* `BaseException` - базовое исключение, от которого берут начало все остальные
    * `SystemExit` - исключение, порождаемое функцией `sys.exit`при выходе из программы.
    * `KeyboardInterrupt` - порождается при прерывании программы пользователем\
    (обычно сочетанием клавиш `Ctrl+C`).
    * `GeneratorExit` - порождается при вызове метода `close` объекта `generator`.
    * `Exception` - а вот тут уже заканчиваются полностью системные исключения\
    (которые лучше не трогать) и начинаются обыкновенные, с которыми можно работать.

        * `StopIteration` - порождается встроенной функцией next, если в\
        итераторе больше нет элементов.
        * `ArithmeticError` - арифметическая ошибка
            * `FloatingPointError` - порождается при неудачном выполнении операции\
            с плавающей запятой. На практике встречается нечасто.
            * `OverflowError` - возникает, когда результат арифметической операции слишком\
            велик для представления. Не появляется при обычной работе с целыми числами\
            (так как python поддерживает длинные числа), но может возникать в\
            некоторых других случаях.
            * `ZeroDivisionError` - деление на ноль.
        * `AssertionError` - выражение в функции `assert` ложно.
        * `AttributeError` - объект не имеет данного атрибута (значения или метода).
        * `BufferError` - операция, связанная с буфером, не может быть выполнена.
        * `EOFError` - функция наткнулась на конец файла и не смогла прочитать то, что хотела.
        * `ImportError` - не удалось импортирование модуля или его атрибута.
        * `LookupError` - некорректный индекс или ключ.
            * `IndexError` - индекс не входит в диапазон элементов.
            * `KeyError` - несуществующий ключ (в словаре, множестве или другом объекте).
        * `MemoryError` - недостаточно памяти.
        * `NameError` - не найдено переменной с таким именем
            * `UnboundLocalError` - сделана ссылка на локальную переменную в функции,\
            но переменная не определена ранее.
        * `OSError` - ошибка, связанная с системой
        * `ChildProcessError` - неудача при операции с дочерним процессом.
        * `ConnectionError` - базовый класс для исключений, связанных с подключениями
            * `BrokenPipeError`
            * `ConnectionAbortedError`
            * `ConnectionRefusedError`
            * `ConnectionResetError`
        * `FileExistsError` - попытка создания файла или директории, которая уже существует.
        * `FileNotFoundError` - файл или директория не существует.
        * `InterruptedError` - системный вызов прерван входящим сигналом.
        * `IsADirectoryError` - ожидался файл, но это директория.
        * `NotADirectoryError` - ожидалась директория, но это файл.
        * `PermissionError` - не хватает прав доступа.
        * `ProcessLookupError` - указанного процесса не существует.
        * `TimeoutError` - закончилось время ожидания.
    * `ReferenceError` - попытка доступа к атрибуту со слабой ссылкой.
    * `RuntimeError` - возникает, когда исключение не попадает ни под одну из\
    других категорий.
    * `NotImplementedError` - возникает, когда абстрактные методы класса требуют\
    переопределения в дочерних классах.
    * `SyntaxError` - синтаксическая ошибка
        * `IndentationError` - неправильные отступы
            * `TabError` - смешивание в отступах табуляции и пробелов
    * `SystemError` - внутренняя ошибка.
    * `TypeError` - операция применена к объекту несоответствующего типа.
    * `ValueError` - функция получает аргумент правильного типа, но некорректного значения.
    * `UnicodeError` - ошибка, связанная с кодированием / раскодированием unicode в строках
        * `UnicodeEncodeError` - исключение, связанное с кодированием unicode.
        * `UnicodeDecodeError` - исключение, связанное с декодированием unicode.
        * `UnicodeTranslateError` - исключение, связанное с переводом unicode.
    * `Warning` - предупреждение.

---

**Как это всё может выглядить и каков порядок?**

```python
try:
    k = 1 / 0
except ZeroDivisionError:
    print("You can't divide numbers by zero")
```

В блоке `try` мы выполняем инструкцию, которая может породить исключение,\
а в блоке `except` мы перехватываем их. При этом перехватываются как само\
исключение, так и его потомки. Например, перехватывая `ArithmeticError`,\
мы также перехватываем `FloatingPointError`, `OverflowError` и `ZeroDivisionError`

Также возможна инструкция `except` без аргументов, которая перехватывает вообще всё\
(и прерывание с клавиатуры, и системный выход и т. д.). Но в такой форме инструкция\
`except` практически не используется, потому что у вас не будет никакой конкретики\
какой конкретно природы ошибку поймал ваш обработчик. Вместо этого используется\
`except Exception`. Однако чаще всего перехватывают исключения по одному, для\
упрощения отладки (вдруг вы ещё другую ошибку сделаете, а `except` её перехватит)

```python
my_list = [1, 2, 3, 4, 5]

try:
    result = int("not_an_integer")
    value = my_list[result]
except Exception:
    print("Произошла ошибка при доступе к элементу списка")
```

**Как делать более правильно:**

```python
my_list = [1, 2, 3, 4, 5]

try:
    index = int(input("Enter a number: "))

    try:
        result = my_list[index]
        print(result)
    except IndexError:
        print("Произошла ошибка при доступе к несуществующему индексу списка")

except ValueError:
    print("Произошла ошибка при преобразовании строки в число")
```

**Или же так:**

```python
my_list = [1, 2, 3, 4, 5]

try:
    index = int(input("Enter a number: "))
    result = my_list[index]
    print(result)
except IndexError:
    print("Произошла ошибка при доступе к несуществующему индексу списка")

except ValueError:
    print("Произошла ошибка при преобразовании строки в число")
```

Ещё две инструкции, относящиеся к нашей теме, это `finally` и `else`.\
`Finally` выполняет блок инструкций в любом случае, было ли исключение, или нет\
(применима, когда нужно непременно что-то сделать, к примеру, закрыть файл).\
Инструкция `else` выполняется в том случае, если исключения не было.


```python
try:
  user_input = int(input("Enter any number: "))
  a = user_input ** 2
  print(a)
except Exception:
  print("Переменная 'user_input' - не число. Выходим.")
else:
  print(f"Всё хорошо, результат = {a}")
finally:
  print('Я всегда выполнюсь в конце, пока!')
# Именно в таком порядке: try, группа except, затем else, и только потом finally.
```

---

# **Tasks**

* **or:**
Создайте программу, которая проверяет, является ли число кратным 3 или 5.

* **Проверка пароля:**
Напишите программу, которая запрашивает у пользователя\
пароль. Если пароль равен "secret", выведите "Доступ разрешен", в\
противном случае выведите "Доступ запрещен".


* **Проверка числа на четность:**
Попросите пользователя ввести целое число. Если число четное,\
выведите "Число четное", иначе выведите "Число нечетное".


* **Калькулятор для двух чисел:**
Запросите у пользователя два числа и оператор (+, -, *, /). Выполните\
соответствующее математическое действие и выведите результат.\
Обработайте случай деления на ноль.


* **Оценка студента:**
Введите оценку студента от 0 до 100. Если оценка больше или равна 90,\
выведите "Отлично". Если оценка больше или равна 70, выведите\
"Хорошо". В противном случае выведите "Плохо".


* **Проверка года на високосность:**
Запросите у пользователя год. Проверьте, является ли этот год\
високосным, и выведите соответствующее сообщение.

Год високосный, если он делится на 4, но не делится на 100,\
за исключением случаев, когда он делится на 400


* **Расчет стоимости билета:**
Попросите пользователя ввести возраст и тип билета ("детский",\
"взрослый", "пенсионер"). Рассчитайте стоимость билета с учетом\
скидок (50% скидка для детей и пенсионеров)

По умолчанию билет стоит 100(целое число)
Для просто взрослого человека цена 100%
Для детей и пенсионеров скидка 50%

ребёнок (до 10 лет включительно)
взрослый (11-55)
пенсионер (55+)


* **Определение времени суток:**
Попросите пользователя ввести текущее время (HH:MM).\
Выведите сообщение, соответствующее времени суток:\
"Утро", "День", "Вечер", "Ночь".

утро (5:00 - 11:59 включительно)
день (12:00 - 16:59 включительно )
вечер (17:00 - 23:59 включительно)
ночь (00:00 - 04:59 включительно)


* **Расчет налога на доход:**
Введите годовой доход пользователя. Рассчитайте налог на\
доход с учетом ставок: до $10,000 - 10%, от $10,000 до\
$50,000 - 20%, свыше $50,000 - 30%.


* **Калькулятор BMI (Индекс массы тела):**
Запросите у пользователя его вес (кг) и рост (м). Рассчитайте\
его BMI по формуле BMI = вес / (рост^2) и выведите сообщение,\
указывающее на его состояние: "Недостаточный вес",\
"Норма", "Избыточный вес", "Ожирение".


* **Конвертер температуры:**
Попросите пользователя ввести температуру в градусах Цельсия.\
Затем спросите, в какую шкалу он хочет конвертировать\
(Фаренгейт или Кельвин). Выполните конвертацию и\
выведите результат.


* **Расчет кредита:**
Попросите пользователя ввести сумму кредита, процентную ставку и\
срок кредита (в годах). Рассчитайте ежемесячный платеж и\
общую сумму, которую придется заплатить. Обработайте\
возможные ошибки ввода.\
**POV:**
спец формула для расчёта ежемесячного платежа можно найти в интернете