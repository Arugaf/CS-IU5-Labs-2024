# 2 - программирование циклических алгоритмов

> Лабораторная работа 2 для студентов курса "Основы программирования" 1 курса кафедры ИУ5 МГТУ им Н.Э. Баумана.

## Содержание

 - [Цель работы](#цель-работы)
 - [Начало работы](#начало-работы)
 - [Указания по выполнению лабораторной работы](#указания-по-выполнению-лабораторной-работы)
 - [Задания](#задания)
	 - [Вариант 1](#вариант-1)
	 - [Вариант 2](#вариант-2)
	 - [Вариант 3](#вариант-3)
	 - [Вариант 4](#вариант-4)
	 - [Вариант 5](#вариант-5)
	 - [Вариант 6](#вариант-6)
	 - [Вариант 7](#вариант-7)
	 - [Вариант 8](#вариант-8)
	 - [Вариант 9](#вариант-9)
	 - [Вариант 10](#вариант-10)
	 - [Вариант 11](#вариант-11)
	 - [Вариант 12](#вариант-12)
	 - [Вариант 13](#вариант-13)

## Цель работы

Получить навыки работы с циклами, функциями, вложенными циклами, вещественными числами. Научиться использовать манипуляторы **std::setw** и **std::setprecision** для форматирования потокового вывода.

## Начало работы

Зайдите в свою локальную директорию с репозиторием для выполнения лабораторных работ. Заберите ветку с соответствующей лабораторной работой из общего репозитория (в лабораторной работе 0 был отмечен меткой upstream):

```
git pull upstream
```

**или**

```
git pull upstream lab_2
```

Переключитесь на ветку с текущей лабораторной работой:

```
git checkout lab_2
```

Свяжите ветку локального репозитория с вашим удаленным репозиторием:

```
git push --set-upstream origin lab_2
```

## Указания по выполнению лабораторной работы

Приложение должно обеспечить возможность повторного ввода данных без повторного запуска приложения. Например, через цикл, который включает в себя вопрос вида "*Продолжить работу? (y/n)*" и проверку соответствующего символа для продолжения. В цикле также должно быть предложение запустить выбранную часть задания.

Все задания подразумевают работу с вещественными числами. Также каждое отдельное задание должно быть реализовано в отдельной функции. Для вычисления математических функций следует использовать заголовочный файл **cmath**.

При вычислении значения очередного члена ряда используйте значение предыдущего члена, предварительно сохранив его в отдельную переменную.

Обеспечьте вывод данных заданной точности с использованием манипуляторов **std::setw** и **std::setprecision** из заголовочного файла **iomanip**.

### Для задачи 3

Расчет степенных функций и, особенно, факториалов, может привести к быстрому росту значений и, вследствие, к потери точности вычислений и даже переполнению. Чтобы этого избежать, следует использовать свойство сходимости ряда Тейлора. Это позволяет вычислять каждый следующий член ряда Тейлора по следующей формуле:

![enter image description here](https://sun9-70.userapi.com/s/v1/ig2/DPeCfY4D_s8EnJ1DmS8j5KupeoaqDREYLVKZPNo0S82r0HgfoscVbiimwWU7D3Dx9XtfSS1gtHy9mTad0G13R87Y.jpg?quality=95&as=32x9,48x13,72x19,108x29,155x42&from=bu&u=4SOPWzul-qhkXCr72-EyRzLw-xz5MKkyEiQZtvIpjdw&cs=155x42)

Где **Ai** - i-ый член ряда Тейлора;
**k** - коэффициент, соотношение вида:

![enter image description here](https://sun9-29.userapi.com/s/v1/ig2/MvmIAAXHl3UOLZ-YyL_k_wqD4Y6TjdKb5XVFgu7JoOvmc6RIMtgs6-uN45aDXEHHsY8RjllzEU59xMwdfoY_GF7R.jpg?quality=95&as=32x12,48x19,72x28,108x42,160x62,234x91&from=bu&u=--C--oFwsgo1M2XDSi2TOsw97otc0EAhvukO4hR-cPc&cs=234x91)

Расчет ряда Тейлора следует заканчивать тогда, когда очередной рассчитываемый член ряда меньше погрешности, заданной в задании.

## Задания

Вариант задания определяется вариантом делением по модулю варианта студента на 13.

### Вариант 1

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-23.userapi.com/impg/qfMFJhrE1nALDaCn9HEsE68UoGFDPcYp32kxxw/ZJl4rlJMTTo.jpg?size=168x105&quality=95&sign=d3d386c21def22c22b254ddf7ecdad07&type=album)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы ряда:
![enter image description here](https://sun9-62.userapi.com/impg/M4g8x-F19AYAJfht1z_37euYYlFsMuBDeoZyIA/Pw1fDRTZaSw.jpg?size=232x42&quality=95&sign=07afa4111d52f2d660d1d171fec8d05b&type=album)
и функции **Y(x) = sin(х)**, где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-54.userapi.com/impg/3LGqZ9C9WAEueWYZCrbBlNEQcr6wxw7tfBkwWA/5uBh7lLbzD8.jpg?size=259x43&quality=95&sign=23996e1fb7d7d5723e39f51584603c38&type=album)
Натуральное значение **n** и значение **х** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 2

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-23.userapi.com/impg/qfMFJhrE1nALDaCn9HEsE68UoGFDPcYp32kxxw/7Fa9QKwq1vM.jpg?size=168x105&quality=95&sign=6ffdd4c1544f0b963fe4f917d54d902e&type=album)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-9.userapi.com/impg/9_kiEHrwVRZhagIztmwKvnP1lht33MbaEFti4w/U0eG5B5z524.jpg?size=171x42&quality=95&sign=c8e1048afe9a1baacbd57c33c6ef0c63&type=album)
и функции:
![enter image description here](https://sun9-53.userapi.com/impg/qTy-mmvv0E8LwjuPe1H_SAf7WtETnhXaIfmW5A/B7ZNtINt3yk.jpg?size=107x41&quality=95&sign=03243f89aa87e49c5e9f659f5fc19d16&type=album), где **0 ≤ х ≤ 1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-31.userapi.com/impg/AHje2IJZmJowuUruvNBztANFjdQgQRKyf_nS6A/TyuxZZMhr2U.jpg?size=247x42&quality=95&sign=3bd697b69e458c1706276ab17cf9e5d5&type=album)
Натуральное значение **n** введите с клавиатуры. Значения **x** и **а** также введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 3

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-23.userapi.com/impg/qfMFJhrE1nALDaCn9HEsE68UoGFDPcYp32kxxw/ElaAhKoV1aE.jpg?size=168x105&quality=95&sign=dca59b459e8d5740b6208ec9bcb2fc0b&type=album)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-31.userapi.com/impg/rJv3ITcgM44f7TiCvI6m5DjDc2_Oi9NgMtMqzg/nlKoUMLUcEs.jpg?size=230x59&quality=95&sign=d82dabdb93294689b6d0392bbcd55912&type=album)
и функции:
![enter image description here](https://sun1-98.userapi.com/impg/_nT71eOgXSu-C2Dv11Y-5MZ63udA73nCJDLFtQ/sbGEuvGhjCY.jpg?size=168x39&quality=95&sign=64565f7bb2345735f81fe0f268a66ec6&type=album), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-54.userapi.com/impg/4IhR4IeQR6qctUbxVED6fZVkEbuOk0pO06z2zQ/pi9tPVvdyK8.jpg?size=245x41&quality=95&sign=9b95611c44153e200ba32646ed899323&type=album) для **|x| < 1**.
Натуральное значение **n** и значение **х** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 4

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-29.userapi.com/s/v1/ig2/U76jXIUQLiruQzcyUc0FKIWW0MUQ_G6wXm4u3PSNSS9H_KQ9BcJam29YLKYW6pRHiYHLxgGRdvDc7xxLECIv7ffJ.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=NurM6_ABDqkmR_56woVfljlrdSvSQIKDLroXWaFzHTM&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-65.userapi.com/s/v1/ig2/osumTqABr4PBeTEv6VZbGlhWN_yIm655M5kiTlC4xsCwkFchcSi4cSnn93hPNTGFgSSxFe5irxDOloqsKif5RN2b.jpg?quality=95&as=32x6,48x10,72x15,108x22,160x32,213x43&from=bu&u=SvEQZOpgApG63GNYptFIkyuIFKYn5mNJC-a8MX-guF8&cs=213x43)
и функции:
![enter image description here](https://sun9-77.userapi.com/s/v1/ig2/_Le99ELHk2WWL3kJtQG4qxy1soqvXgnUD_K0wGi1ip9sRNmWEWkXd7qDoEBtro9iNBxce6WMMQ_t1X3B32oaFeU3.jpg?quality=95&as=32x6,48x9,72x14,102x20&from=bu&u=JdqPp7BjsCW6fshSx9RX-s2J4odPl0sZPG-hCGYLhuE&cs=102x20), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-15.userapi.com/s/v1/ig2/uL6jG-TgV-JXCIpqEt5VE-IfWY7wiHYH3gkMRMO1P6WkeLM295-actEU_S17s84TUSKvSxujFUA98IwybxiP-Y_u.jpg?quality=95&as=32x21,48x32,72x48,108x72,149x99&from=bu&u=6ilIilaheJnLoky9Tp-Xm99IW1FxQjE92gyj1NVvzeM&cs=149x99)
Натуральное значение **n** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 5

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-23.userapi.com/s/v1/ig2/H2_rfH_9jNA1BIZ_6h05dSee1Dz1P3XbUcx0Vt0oL_Htnrrg2wl1L_pK1N5B1XRLo2Yp0eXmgvUAq2JN9T1R8lrx.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=sBODMJkEBiovvKUrZnJB0AxsexfToI6xzYVJTHMzjes&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-55.userapi.com/s/v1/ig2/7ptAsp91p8K1uoKkvovZPojeLmbDIYBDgcSdYJOZROhP-ALbMraI-GUkBtwEqzNrsE97BFqg-DjHwcDN7WkXBXrQ.jpg?quality=95&as=32x6,48x9,72x14,108x21,160x32,198x39&from=bu&u=cA5iqUgv8gSF6E2Hk2HK7Gwp1Gy2ONiWuEJIkaYOiNU&cs=198x39)
и функции:
![enter image description here](https://sun9-18.userapi.com/s/v1/ig2/C876G_Ra9bNxAtelfCBSu-71aG3TjTWwFYxP7HJlfFpNnpwhsUcjPkCcQLMFlrQI3eAGQdq_BhggBkeacrOJkg7O.jpg?quality=95&as=32x6,48x9,72x14,108x20,133x25&from=bu&u=okdFy4a5zmHAOmTGGxlPBff4Twp6om8iOvjXLz2opiU&cs=133x25), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-77.userapi.com/s/v1/ig2/RnGnv7fGeip5Z81ExxNbOvBOy5fvAGkUrANcke94zA0nug4bdz0RBsu19ab0aCNu1yqVqMu2P-96ntOEZO_ECDYy.jpg?quality=95&as=32x18,48x27,72x40,108x60,160x89,180x100&from=bu&u=84CBsnwZ7KT2DjfneC2_Mntce_a6J7V98HNwBGZNlvc&cs=180x100)
Натуральное значение **n** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 6

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-23.userapi.com/s/v1/ig2/IF-pq8LnNFQxgJRjl0hOqOEgZftZQRbd5T4FagRsQoobEXQCWQq-_BFphIaTZL4bhQ_vAJN4zVTFbOkguzn-eDv3.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=gPte4udpxEa_KlLAVzTxAqYyFOQY4bmeM8jV10kQPws&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-11.userapi.com/s/v1/ig2/csc_bDIFkWVEcZuTEEdVkWjbDkOkt7aoWj0DYljrlkpyV91Uq7fYcHUlWjX4bVsgYiuYs1qH_nEUxl7Ktuz5kVVs.jpg?quality=95&as=32x6,48x9,72x13,108x20,160x30,224x42&from=bu&u=Qn6uhY3vtPCvuUWSK1gdBgHZj-f53ahzuArxHUdL4U8&cs=224x42)
и функции:
![enter image description here](https://sun9-45.userapi.com/s/v1/ig2/_W0iifK-yMWBSQgf1Dy2jSSr9KrSZALgpeHhEUF4xVcOjgafffWOefdq4QMdhPgOSLIKghf5qliKY2rZdTPHr_G3.jpg?quality=95&as=32x10,48x14,72x21,84x25&from=bu&u=KwgMgFk8na8CIXbv6fBz1uIduGlvJsJLtsS1OSBwlWw&cs=84x25), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-63.userapi.com/s/v1/ig2/SKVT9uDPHdgEttjSETN_Twy4CRxPI4CaTtzbvvZ_Lgu_62r0C1kmp3xzPaN94TvEGon0n7MdNpsIdpDlGxj8J5Cu.jpg?quality=95&as=32x5,48x7,72x11,108x16,160x24,240x36,286x43&from=bu&u=xTCNXyWfSGXrimJaKVYgUNX_QcTglhcNIPkY3h7Gt-c&cs=286x43)
Натуральное значение **n** и значение **х** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 7

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-16.userapi.com/s/v1/ig2/ja7XfLwnWtd70gJyW-YtDfmK_gqOVnS7mZVRMFxM72wFsvqHrTt2paM5EDGwMxZ-srOWJqPiWINUvYxKejQrErpF.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=EEuRQSxv5cQD6t1Bm9hKyLfUj5InQRVZ9nEHdh70yvU&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-4.userapi.com/s/v1/ig2/nI_jU4CbFrtr8DP8kOWbEC5MGfa0llr3J-1PAg30F0BlD76P4ZrHr8SyMmDRdHAgTqbIBpBOJDDZYFz8KIqGT4il.jpg?quality=95&as=32x6,48x9,72x14,108x20,160x30,218x41&from=bu&u=kK8Xj3wpltZzwfyqwZvhJ7WVbPQPIPd4ojBJLuR4Gxg&cs=218x41)
и функции:
![enter image description here](https://sun9-18.userapi.com/s/v1/ig2/IJV9XKI6IXOqRZpLurzsdSMGqt9O0Y-csQp7vM_dVT0GW-tGLkLxXrLcFlvCKH-ePM_5OqwrK5wHjzXf9dfaoZ0C.jpg?quality=95&as=32x5,48x8,72x12,108x18,130x22&from=bu&u=kateGKZ4fpe0U4ak3JBw3oZhlhRKdo9m_5xlRkymRbc&cs=130x22), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-39.userapi.com/s/v1/ig2/09nIp40oIfpYM0q3NzYhxW_lihy9r3I-khjjjpyMoqDBeLz9rqzQX6UP0aZ-6Ig4tiBrWQ-KbchEqYwIcqCBoF_y.jpg?quality=95&as=32x4,48x6,72x9,108x14,160x21,206x27&from=bu&u=6V2z1XMOQzA8WwtGrlKmYIgjYIiPLFn8GoOmtUcdIxc&cs=206x27)
Натуральное значение **n** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 8

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-16.userapi.com/s/v1/ig2/elfNLdN63Y_XKMLoizRD-1xJ_pMirJq7g3YpyG4vSfp-c34zQkk26iMQUKc0ADoEVv5zUeTRZzRjk74Ag_wsOUU_.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=D5Hk7SDVQAm4x2vY29nsj7jSbWiSki7BFUJ8mtAuG84&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-27.userapi.com/s/v1/ig2/twtDnQrguQV6j94IVLELEFCC81UGi1GufQ8Rm-f17tywbSo65hnPcOe5FsWFXG2IGffsPAFyK981xIEDt4JIS7v6.jpg?quality=95&as=32x8,48x12,72x17,108x26,160x39,173x42&from=bu&u=Jug020AeVKwMVBdT4slFFZraCa8bcXFDRqC0fKWnhO4&cs=173x42)
и функции:
![enter image description here](https://sun9-60.userapi.com/s/v1/ig2/qp_x82BWlSQ_7v6CKPbDA7zGEWQ3QhhtU70qDE33TVnwNT3U54h7f_rI0x7IqaSD8aX4eX_ZZ-ohBI50_ra9c0F8.jpg?quality=95&as=32x9,48x14,72x20,78x22&from=bu&u=9WzNXDnhcBiuU8t7WlPtAcSmBx8cEGliwofHdoHmqs4&cs=78x22), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-50.userapi.com/s/v1/ig2/iCVJEdzw-hqVeFhk9smPBAxJLD0N9cSFhupTvdeSbOdntQdNwv9pVaCqkMet6VeWdQoDWTsWu5ZlHHvJ5DQMFtr8.jpg?quality=95&as=32x3,48x5,72x7,108x11,160x16,240x24,360x36,422x42&from=bu&u=A0Q8isZaJ4PMaE1eXCqKep4KdPZqXh8ObuYSE9ZBHQ0&cs=422x42)
Натуральное значение **n** и значение **х** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 9

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-16.userapi.com/s/v1/ig2/QiTLBD7p3fnJyUwajKEZIIqDInIr3Lhpapi92vHON_Z4elPosyuGrJspje_Kci_O2QbrIpfHgwzR02CWPhZEe4h8.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=n6NT6OyeviPPgL9Uv3vO6FVf0ecuiueOPnEoz4nha8g&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-32.userapi.com/s/v1/ig2/f_Wj-xYhlhA3dnw1k4QTdxFZNHr-oeSj8C4gjbzJZKHXi28rqoVT7fQ-25jGEBn5dPxSqih3WYqNLF08fvI1rbqY.jpg?quality=95&as=32x7,48x10,72x15,108x23,160x34,200x43&from=bu&u=xPkCycYjBfJ9NgXXNmPoi-rC57GtGWkRdBf9zMyo1k0&cs=200x43)
и функции:
![enter image description here](https://sun9-17.userapi.com/s/v1/ig2/dmOedJ_KIc_YaU8YoRvOn-a_fs2zM5DKjrtKGsIfGDap6rOzcyP1GJDI5ZkfFj8U5_yw1D0LHSzjz9NHa0srOHIN.jpg?quality=95&as=32x10,48x15,72x23,108x35,146x47&from=bu&u=DtfX5fiV0wthBukDGCje8wY69ZVXvY-dE8YSORUP4lc&cs=146x47), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-66.userapi.com/s/v1/ig2/w4YP9xriinKqKelMVb44Z0aWBvB6jHOQlVE59jt7T_Dth6JpAq6Si92Bb09NAtjiVj5zH4b-Zfe_KAdhTTjGAkSc.jpg?quality=95&as=32x5,48x7,72x10,108x15,160x23,175x25&from=bu&u=m3Ayy5D9ovUThGFa-sz9orS2fktlAwHdXBTgq38M0AE&cs=175x25)
Натуральное значение **n** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 10

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-16.userapi.com/s/v1/ig2/xTXuOhy2DSzeMPDh8mtjNkjLT9a7Zr6fdowKHYzg7ZbWVod2t5NBsK8GviXti5vxi3w0VDuVA28lAul0oBYgN4An.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=WQWPKwwP5tQR_DkKjGuYiex4OdGOOKbw-0M3PlgZGss&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-72.userapi.com/s/v1/ig2/ZyQ6X-5AZGGdQROnjbcH7LZ9T7DMLlWCLumK9_aM1GPa2Ag80GBs4h-RTozAssFpreCg-eSWhY2QJ4-H193Gqjmw.jpg?quality=95&as=32x6,48x9,72x14,108x21,160x31,212x41&from=bu&u=dfTD6EN6W94gO7_Oho5eYMMdc4QLbag5YZNAn1a-OPU&cs=212x41)
и функции:
![enter image description here](https://sun9-77.userapi.com/s/v1/ig2/82PffPezhnmMo3Hvux39eDenpfuRY00GhviT8XVEeRVQP8D7DmSilRcdtVkSSSKhWajCt8zUWsn04BF9ubSPY_bm.jpg?quality=95&as=32x6,48x8,72x13,108x19,115x20&from=bu&u=ornxR45c8gQEZd-2gKYbUl6qZxLaoumbfKwI6xnCCOE&cs=115x20), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-22.userapi.com/s/v1/ig2/tOOC0xGbjhnBxFALHmv3UfardH-D-LZoGhoT0ltGtjnK6XA31SYHYA4UBPu1HlPPS9u3bp6f14jZ5pIOMr7XLp7B.jpg?quality=95&as=32x3,48x5,72x7,108x11,160x16,240x24,360x36,422x42&from=bu&u=DKS-uitJAxNlYxcS_Unk1WrOLQFzZWCnTCfulyu8fqw&cs=422x42)
Натуральное значение **n** и значение **х** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 11

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-16.userapi.com/s/v1/ig2/Bb1YkybjifzW3s4zEr5pNrUzbnUnfviBoTlOWzOEAByl1SYTICMpKZDZonaEqTW1LBgOWmSSFXUua4RpT8ObSoGp.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=lhZF9ceGx2Q2_jNVjvbkYhhYPVIJts-pOUTqXREkXnM&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-67.userapi.com/s/v1/ig2/SLTQdlMjwNIRh0INzjMzo5nKXV0q7k2n2CJA6igIqyxuwetF9oyk4IWvTBW9RTHt6SpINxhbHhkHAmThjEwkPDDA.jpg?quality=95&as=32x5,48x8,72x12,108x18,160x27,240x41,253x43&from=bu&u=UWU542QvAR8yk2FVeEkzqPNH9SNob7tFsvusxnSDU44&cs=253x43)
и функции:
![enter image description here](https://sun9-50.userapi.com/s/v1/ig2/jlucxRKDvTjo1g1FMEpzOa1s4pEh_tYckanMciaL_-u4yrLZrrFJnfNXO-E4m-mG56Q9ppLAfAbJK0gTq5nB_5y1.jpg?quality=95&as=32x6,48x10,72x15,108x22,160x32,223x45&from=bu&u=qvnFrX5k3mIro9rDc5fH2oZ41Uzz1BU7tGQz66M1oDQ&cs=223x45), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-17.userapi.com/s/v1/ig2/AHKBMxKWwWf02o5RYi6PRR-ziqTu7Ynu2cGfo5E11U1so_0pLp-it8MstfYc0je2fgLomiz2oxPl2Q4fxaQmRIwL.jpg?quality=95&as=32x4,48x6,72x9,108x13,160x20,219x27&from=bu&u=_6jFpOnO3LLAwmXitZn3K0yK6POW5HlSvLInjFNKd4c&cs=219x27)
Натуральное значение **n** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 12

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-16.userapi.com/s/v1/ig2/4kt0uCxjXAkP4fBGJ58JNy8q42w_HYLncGLLNN3nCTlPNHUamPrPu5Oj17fd5wPZDr2V8a9tvVca8uw3FxW4XDRX.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=Yi2MqrAcSeGQrzCKT1bRAz-sHONyFid0khu2RwVw3Tk&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-72.userapi.com/s/v1/ig2/vPHWeV_hqUzWPLEMROGVKodAG58gfN9xCcN-w6Nmojj2ngksAcO6YHrlxTXYCA5XlbyiBZu5mxTABL5eEgBW3YOP.jpg?quality=95&as=32x5,48x7,72x11,108x16,160x24,240x37,288x44&from=bu&u=5_h8sBt8h-FVwehVmIeMzhuH-sD8IJf1ef-eSpbcTCg&cs=288x44)
и функции **Y(x) = cos(2x)**, где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-54.userapi.com/s/v1/ig2/4aBJQxvDVPhek3RRVwZihh_OQARK3tQZ30wZhjfSTY00-XFgmKLdkBpLneCRevlJe18CbkS4vZJn4hX8mtRL3qVA.jpg?quality=95&as=32x6,48x10,72x14,108x22,160x32,214x43&from=bu&u=d6vHrkUrt3GWDMXk3t7WeTZIBOKm4_6Og7fGmPWf6mQ&cs=214x43)
Натуральное значение **n** и значение **х** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.

### Вариант 13

 1. Найдите сумму натуральных чисел на отрезке от **1 до n,** которые делятся на **5** и не делятся на **m** (**m** < **n**). Значения **n** и **m** вводятся с клавиатуры;
 2. Вычислите:
![enter image description here](https://sun9-16.userapi.com/s/v1/ig2/vPRBTIDkhtoUsrk0NH93J4l12uWGveQi6mVLr6Assck-Mg9gTsObJnubTKgxWV8i4oH1zMibTxEru7VAdy12U6yh.jpg?quality=95&as=32x20,48x30,72x45,108x67,160x100,168x105&from=bu&u=AXYTqvjcG95Nx3jUwyFib5y8pRN_TUi44pGsJHMZlNc&cs=168x105)
Значение **a** вводится с клавиатуры;
 3. Вычислите значения суммы:
![enter image description here](https://sun9-53.userapi.com/s/v1/ig2/N_3nah7Tbar0uubwrBIkxEIq_u3nqlMzjlMH1qWVzgQ1Kh12P6HIjHmXPqQqJVnUAKg9l8iarGHbWMYaf7EA9832.jpg?quality=95&as=32x7,48x10,72x15,108x23,160x34,193x41&from=bu&u=C1FSp3lmM2NOl6zo5u_ZJwG9Bgdxao5PEb33h2d9NFk&cs=193x41)
и функции:
![enter image description here](https://sun9-48.userapi.com/s/v1/ig2/jyH3Ap_PSlA8H21XaHeaO9R-ScAupCMhVKZWzhEXY-SlvQ12WicraFotgGP0FdtSSBd2iw4-vzjtPiEGjBbuZwXP.jpg?quality=95&as=32x12,48x18,72x26,106x39&from=bu&u=4xTVAyrvAbGTAme8Olx38iX4WZ-uAZYaUy47S5RXRHQ&cs=106x39), где **0 ≤ х ≤1**, с шагом **h = 0.2**. Вычисление суммы ряда Тейлора производите с погрешностью, не превышающей **1e-6**.
Результат представить в виде таблицы (без рамок), которая содержит четыре столбца со значениями x, Y(x), S(x) и N, где N - номер последнего слагаемого ряда;
 4. Вычислите **y** по формуле:
![enter image description here](https://sun9-67.userapi.com/s/v1/ig2/KhHbz-IgzKub3O0wdE8EXSK-f2WXhstXS_C8i7YqTDYZD6Qn3V-Ukzi1_BFLzeI9S7rqg1lqMirhyPZNRVf6xxCu.jpg?quality=95&as=32x6,48x9,72x13,108x19,160x29,240x43,244x44&from=bu&u=P8qVrCxboTI_f-F1O3E1RYAqGDYxfzuCO9Y31-_xazc&cs=244x44)
Натуральное значение **n** и значение **х** введите с клавиатуры. Обеспечьте возможность вычислить **y** для нескольких значений **n** и выведите на экран значения промежуточных (частичных) сумм при количестве слагаемых **3**, **5** и **10**.
