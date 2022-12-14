---
title: "Лабораторная работа №1"
author: |
  Кувшинова Ксения Олеговна\inst{1}
date: "09.09.2022, Moscow"
output:
  beamer_presentation: default
  slidy_presentation: default
  ioslides_presentation: default
  powerpoint_presentation: default
subtitle: "Установка и конфигурация операционной системы на виртуальную машину"
lang: ru-RU
institute: |
  \inst{1}RUDN University, Moscow, Russian Federation
toc: no
slide_level: 2
theme: metropolis
header-includes:
- \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
- \makeatletter
- \beamer@ignorenonframefalse
- \makeatother
aspectratio: 43
section-titles: yes
---



## Цель работы

Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

## Выполнение лабораторной работы

Установили на виртуальную машину операционную систему Linux (дистрибутив Rocky) со всеми неоходимыми параметрами.

![ОС Linux на виртуальной машине](5.png){#fig:003 width=100%}

## Выполнение лабораторной работы

Запустили ВМ и установили следующие настройки:

![Окно обзор установки](allthnigs.png){#fig:010 width=100%}

## Выполнение лабораторной работы

В меню Устройства виртуальной машины подключаем образ диска дополнений гостевой ОС, введим пароль пользователя root виртуальной ОС. 

![Загрузка образа диска дополнений гостевой ОС](dopobr2.png){#fig:014 width=100%}

## Выполнение задания 

1. Версия ядра Linux (Linux version).
Использовали команду dmesg | grep -i Linux. В результате получили, что версия ядра 5.14.0-70.1.1.el9_0.x86_6. (@fig:016)

![Версия ядра Linux](ex1.png){#fig:016 width=100%}

## Выполнение задания 

2. Частота процессора (Detected Mhz processor).
Использовали команду dmesg | grep -i Detected. В результате получили, что частота процессора 2399.996 MHz. (@fig:017)

![Частота процессора](ex2.png){#fig:017 width=100%}

## Выполнение задания 

3. Модель процессора (CPU0).
Использовали команду dmesg | grep -i CPU0. В результате получили, что модель процессора Intel(R) Core(TM) i5-9300H. (@fig:018)

![Модель процессора](ex3.png){#fig:018 width=100%}

## Выполнение задания 

4. Объем доступной оперативной памяти (Memory available).
Использовали команду dmesg | grep -i Memory. В результате получили, что объем доступной оперативной памяти равен 260860К/2096696К (@fig:019)

![Объем доступной оперативной памяти](ex4.png){#fig:019 width=100%}

## Выполнение задания 

5. Тип обнаруженного гипервизора (Hypervisor detected).
Использовали команду dmesg | grep -i Hypervisor. В результате получили, что тип обнаруженного гипервизора - KVM. (@fig:020)

![Тип обнаруженного гипервизора](ex5.png){#fig:020 width=100%}

## Выполнение задания 

6. Тип файловой системы корневого раздела.
Использовали команду dmesg | grep -i filesystem. В результате получили, что тип файловой системы корневого раздела - XFS.(@fig:021)

![Тип файловой системы корневого раздела](ex6.png){#fig:021 width=100%}

## Выполнение задания 

7. Последовательность монтирования файловых систем.
Использовали команду dmesg | grep -i mount. В результате получили следующий вывод: (@fig:022)

![Последовательность монтирования файловых систем (dmesg)](ex7.png){#fig:022 width=100%}


## Результат выполнения работы

В ходе выполнения работы мы приобрели практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.


## Библиография

1. Кулябов Д. С., Королькова А. В., Геворкян М. Н. Установка и конфигурация операционной системы на виртуальную машину.
2. Справочник 70 основных команд Linux: полное описание с примерами (https://eternalhost.net/blog/sozdanie-saytov/osnovnye-komandy-linux)
