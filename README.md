# 3 - нахождение корней нелинейного уравнения, многофайловые проекты

> Лабораторная работа 3 для студентов курса "Основы программирования" 1 курса кафедры ИУ5 МГТУ им Н.Э. Баумана.

## Содержание

 - [Цель работы](#цель-работы)
 - [Начало работы](#начало-работы)
 - [Указания по выполнению лабораторной работы](#указания-по-выполнению-лабораторной-работы)
	 - [Метод итераций](#метод-итераций)
	 - [Метод Ньютона](#метод-ньютона)
	 - [Метод половинного деления](#метод-половинного-деления)
 - [Задание](#задание)

## Цель работы

Продолжить развивать навыки работы с циклами и функциями. Научиться работать с многофайловыми проектами. Освоить численные методы решения нелинейных уравнений.

## Начало работы

Зайдите в свою локальную директорию с репозиторием для выполнения лабораторных работ. Заберите ветку с соответствующей лабораторной работой из общего репозитория (в лабораторной работе 0 был отмечен меткой upstream):

```
git pull upstream
```

**или**

```
git pull upstream lab_3
```

Переключитесь на ветку с текущей лабораторной работой:

```
git checkout lab_3
```

Свяжите ветку локального репозитория с вашим удаленным репозиторием:

```
git push --set-upstream origin lab_3
```

## Указания по выполнению лабораторной работы

**Для всех лабораторных работ, начиная с этой!**

Обеспечить работу всего **приложения** в цикле, в котором запрашивается, следует ли продолжить выполнение. Также реализовать интерактивное меню с выбором нужного задания. Сами меню и цикл должны быть реализованы в виде двух отдельных функций.

Все возможные варианты выбора для интерактивного меню (например, задания), должны быть указаны в **scoped enum** (**enum class**). Для считывания следует использовать переменную того же низлежащего типа, что и в заданном **enum**. Затем можно использовать **switch-case** по этой переменной, которая **кастуется** (через **static_cast**) к **enum**.

Функция **main** должна служить исключительно в качестве точки входа в приложение. Никакой бизнес-логики в этой функции быть не должно.

Все переменные, изменение которых в дальнейшем не подразумевается, должны быть помечены как **const**.

Проект должен состоять как минимум из трех файлов. Отдельный файл **main.cpp** с функцией **main**, в которой осуществляется передача управления. Далее пара файлов: заголовочный (расширения *.h*/*.hpp*) и парный ему файл с исходным кодом (*.cpp*). Названия файлов должны быть одинаковыми и корректно отражать суть содержимого. В заголовочном файле должны лежать описания типов и объявления **интерфейсных** функций. То есть таких функций, которые напрямую предоставляют возможность пользоваться приложением. Например, функции, отвечающие за цикл приложения, вывод интерактивного меню и вызов функций, выполняющих соответственное задание, непосредственно те функции, которые отвечают за выполнение конкретного задания, и т.д. **Вспомогательные** функции должны быть вынесены в **анонимный неймспейс**. Например, это могут быть функции, связанные непосредственно с вычислениями.

> **Обратите внимание!** На вход компилятору заголовочные файлы не подаются.

Вычисления и ввод/вывод **по возможности*** должны быть отделены друг от друга разным функциями. Например, функция для выполнения определенного задания может внутри себя запрашивать пользовательский ввод и выводить данные, а затем вызывать функцию/функции для вычисления корня уравнения. Но в самой функции, отвечающей за вычисления, никакого вывода быть не должно. Если вывод данных нетривиален (например, используется таблица с форматированием), то его тоже следует вынести в отдельную вспомогательную функцию.

> ***По возможности** - значит по умолчанию отделяются, но если совсем-совсем-совсем непонятно как, то можно совместить.

Все типы и функции, указанные в заголовочном файле, должны находиться в **именованном неймспейсе**. Также допускается использование вложенных неймспейсов в случае необходимости. Имя неймспейса должно отражать суть содержимого.

Все функции должны быть помечены атрибутами (прежде всего **[[nodiscard]]**) в тех случаях, когда это необходимо (для **[[nodiscard]]** всегда, когда функция возвращает результаты каких-то вычислений/проверок/инициализаций и т.п.).

### Метод итераций

Заданное уравнение **f(x) = 0** приводят к виду: **x = φ(x)**. Выбирая некоторое приближенное значение **x[0]**, вычисляют последовательные приближения **x[i + 1] = φ(x[i])**, где **i ∊ [0, ∞)**.

Сходимость таких приближений к искомому решению **x** требует отдельного исследования. Сходимость зависит прежде всего от вида функции, а также от начального приближения (в данной лабораторной работе такие исследования не делаются, но для уравнения **x - 10cos(x) = 0** решения методом Ньютона и методом простой итерации расходятся). Для того, чтобы программа нахождения корней этими методами не зацикливалась, следует ограничивать максимальное число итераций **N[max]**, например, **N[max] < 1e5**.

### Метод Ньютона

Основан на методе итераций. Также известен как метод касательных.

Метод заключается в том, что сначала задается начальное приближение вблизи предположительного корня, после чего строится касательная к графику исследуемой функции в этой точке, для которой находится пересечение с осью абсцисс. Эта точка берется в качестве следующего приближения.

Уравнение для нахождения следующий точки **x[i + 1]**:

![enter image description here](https://sun9-21.userapi.com/s/v1/ig2/uhrzQFeHQvaSGAT0zjDvsgU5LDhjExrtoRZ1ElRlyapu6W_xoefxl1dmixxR70oQY54mIK2wtwuMAcWlaR2vw0gD.jpg?quality=95&as=32x12,48x19,72x28,108x42,160x62,240x93,256x99&from=bu&u=4gGoLkKcZkK2BifOSeHfuCgTVTAQ3w889TDTlcn4-2c&cs=256x99)

### Метод половинного деления

Изначально берется отрезок **[x[L], x[R]]**, значений **x**, на концах которого функция принимает значения противоположных знаков. То есть **f(x[L]) ∙ f(x[R]) < 0** (в лабораторной работе следует просто найти знаки функции в данных точках и сравнить их, т.к. это будет более эффективно, чем умножение двух функций). Для непрерывных функций это будет означать, что искомый **x** находится на данном отрезке.

Затем находится значение функции на середине этого отрезка **x[M]**. Если значение не является искомым, то отрезок делится на два равных: **[x[L], x[M]]** и **[x[M], x[R]]**.

Выбирается тот отрезок, у которого значения функций на концах отрезка имеют противоположные знаки. Для этого отрезка повторяется предыдущее действие.

И так продолжается, пока не будет найден корень уравнения.


## Задание

Найти корень уравнения: **x - cos(x) = 0**:

 - Итерационным методом;
 - Методом половинного деления;
 - Методом Ньютона.

Для каждого из трех методов определить количество итераций цикла N.

Обеспечить возможность посчитать результат с разной погрешностью (например, **1e-6**, **1e-8**), а также возможность задать коэффицент при **cos(x)** (например, чтобы посчитать **x - 10cos(x) = 0**). Для метода половинного деления начальный диапазон для поиска корней также должен указываться пользователем.

Объяснить результаты.
