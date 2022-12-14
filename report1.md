---
title: "Лабораторная работа №1"
author: "Кувшинова К.О. группа НФИ-02-19"
subtitle: "Установка и конфигурация операционной системы на виртуальную машину"
output:
  word_document: default
  pdf_document: default
toc-title: Содержание
toc: yes
toc_depth: 2
lof: yes
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: yes
pdf-engine: lualatex
header-includes:
- \linepenalty=10
- \interlinepenalty=0
- \hyphenpenalty=50
- \exhyphenpenalty=50
- \binoppenalty=700
- \relpenalty=500
- \clubpenalty=150
- \widowpenalty=150
- \displaywidowpenalty=50
- \brokenpenalty=100
- \predisplaypenalty=10000
- \postdisplaypenalty=0
- \floatingpenalty = 20000
- \raggedbottom
- \usepackage{float}
- \floatplacement{figure}{H}
---


# Цель работы

Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Выполнение лабораторной работы

## Установка виртуальной машины

Создаем новую виртуальную машину. Для этого в VirtualBox выбераем Машина -> Создать.
Указываем имя виртуальной машины, тип
операционной системы — Linux, RedHat. (@fig:001)

![Окно «Имя машины и тип ОС»](1.png){#fig:001 width=100%}

Указываем размер основной памяти виртуальной машины  — 2048 МБ. (@fig:002)

![Окно «Размер основной памяти»](2.png){#fig:002 width=100%}
Задаем конфигурацию жёсткого диска — загрузочный,VDI (BirtualBox Disk Image)(@fig:003), динамический виртуальный диск (@fig:004)

![Окно определения типа подключения виртуального жёсткого диска](3.png){#fig:003 width=100%}

![Окно определения формата виртуального жёсткого диска](4.png){#fig:004 width=100%}

Задайте размер диска — 20 ГБ, его расположение — в данном случае /var/tmp/user/uxer.vdi.
В результате получаем следующие характиристики:
(@fig:005)

![Характеристики виртуальной машины](5.png){#fig:005 width=100%}

Выбераем в VirtualBox для нашей виртуальной машины Настройки -> Носители. Добавляем новый привод оптических дисков и выбераем образ
операционной системы. (@fig:006)

![Окно "Носители"](6.png){#fig:006 width=100%}

Запускаем виртуальную машину, выбераем Russian в качестве языка интерфейса и переходим к настройкам установки операционной системы.
В разделе выбора программ указываем в качестве базового окружения Server with GUI , а в качестве дополнения — Development Tools. (@fig:007)

![Окно настройки установки: выбор программ](gui.png){#fig:007 width=100%}

Отключаем KDUMP. Включаем сетевое соединение и в качестве имени узла указываем kokuvshinova.localdomain. (@fig:008)

![Окно настройки установки: сеть и имя узла](network.png){#fig:008 width=100%}

Устанавливаем пароль для root и пользователя с правами администратора. (@fig:009)

![Установка пароля для root](password.png){#fig:009 width=100%}

В результате получаем следующие настройки: (@fig:010)

![Окно обзор установки](allthnigs.png){#fig:010 width=100%}

После завершения установки операционной системы корректно перезапускаем виртуальную машину.
Входим в ОС под заданной нами при установке учётной записью. При запуске машина запрашивает установления имени и пароля, их установили в соответсвии с предыдущей установкой (@fig:011) (@fig:012)

![Окно "о вас"](name.png){#fig:011 width=100%}

![Окно "пароль"](password2.png){#fig:012 width=100%}

В меню Устройства виртуальной машины подключаем образ диска дополнений гостевой ОС, введим пароль пользователя root виртуальной ОС. (@fig:013) (@fig:014)

![Запуск образа диска дополнений гостевой ОС](dopobr.png){#fig:013 width=100%}

![Загрузка образа диска дополнений гостевой ОС](dopobr2.png){#fig:014 width=100%}

После загрузки дополнений нажимаем Enter и корректно перезагружаем виртуальную машину.

## Домашнее задание

Дожидаемся загрузки графического окружения и открываем терминал. В окне терминала проанализируем последовательность загрузки системы, выполнив команду dmesg | less (@fig:015)

![Результат работы команды dmesg | less](dmesg1.png){#fig:015 width=100%}

### Задание

Получите следующую информацию.
1. Версия ядра Linux (Linux version).
2. Частота процессора (Detected Mhz processor).
3. Модель процессора (CPU0).
4. Объем доступной оперативной памяти (Memory available).
5. Тип обнаруженного гипервизора (Hypervisor detected).
6. Тип файловой системы корневого раздела.
7. Последовательность монтирования файловых систем.

### Выполнение

1. Версия ядра Linux (Linux version).
Использовали команду dmesg | grep -i Linux. В результате получили, что версия ядра 5.14.0-70.1.1.el9_0.x86_6. (@fig:016)

![Версия ядра Linux](ex1.png){#fig:016 width=100%}

2. Частота процессора (Detected Mhz processor).
Использовали команду dmesg | grep -i Detected. В результате получили, что частота процессора 2399.996 MHz. (@fig:017)

![Частота процессора](ex2.png){#fig:017 width=100%}

3. Модель процессора (CPU0).
Использовали команду dmesg | grep -i CPU0. В результате получили, что модель процессора Intel(R) Core(TM) i5-9300H. (@fig:018)

![Модель процессора](ex3.png){#fig:018 width=100%}

4. Объем доступной оперативной памяти (Memory available).
Использовали команду dmesg | grep -i Memory. В результате получили, что объем доступной оперативной памяти равен 260860К/2096696К (@fig:019)

![Объем доступной оперативной памяти](ex4.png){#fig:019 width=100%}

5. Тип обнаруженного гипервизора (Hypervisor detected).
Использовали команду dmesg | grep -i Hypervisor. В результате получили, что тип обнаруженного гипервизора - KVM. (@fig:020)

![Тип обнаруженного гипервизора](ex5.png){#fig:020 width=100%}

6. Тип файловой системы корневого раздела.
Использовали команду dmesg | grep -i filesystem. В результате получили, что тип файловой системы корневого раздела - XFS.(@fig:021)

![Тип файловой системы корневого раздела](ex6.png){#fig:021 width=100%}

7. Последовательность монтирования файловых систем.
Использовали команду dmesg | grep -i mount. В результате получили следующий вывод: (@fig:022)

![Последовательность монтирования файловых систем (dmesg)](ex7.png){#fig:022 width=100%}

Так же мы можем найти эту информацию, выполнив команду findmnt: (@fig:023)

![Последовательность монтирования файловых систем (findmnt)](ex7.2.PNG){#fig:023 width=100%}

## Контрольные вопросы

1. Какую информацию содержит учётная запись пользователя?
Учетная запись пользователя содержит в себе следующую информацию: имя пользователя, пароль, числовой идентификатор пользователя, числовой идентификатор группы, полный путь к домашнему каталогу пользователя.
2. Укажите команды терминала и приведите примеры:
– для получения справки по команде;
можно использовать команды:
man <command name>
<command name> --help
Например:
man ls
ls --help
– для перемещения по файловой системе;
используется команда cd для перехода между директориями
cd <dir name>
cd .. -исопльзуется для перехода в папку, которая выше текущей на одну позицию в файловой системе.
– для просмотра содержимого каталога;
используется команда ls;
ls - для просмотра текущей директории 
ls <dir name> - для просмотра заданной директории
– для определения объёма каталога;
команда du с флагами 
-а для вывода размера самой папки и вложенной в нее
-h для вывода информации в привычном виде (Кб, Мб и тд)
du -ah <dir name>
– для создания / удаления каталогов / файлов;
для создания каталога используется команда mkdir <dir name>
для удаления каталога используется команда rmdir <dir name>
для создания файла используется команда touch <file name> (cat < <file name>)
для удаления файла используется команда rm <file name>
– для задания определённых прав на файл / каталог;
используется команда chmod опции права путь к файлу
Права:
r - чтение;
w - запись;
x - выполнение;
s - выполнение  от имени суперпользователя (дополнительный);
Категории пользователей:
u - владелец файла;
g - группа файла;
o - все остальные пользователи;
например,
chmod ug+w <file name> - разрешить запись для владельца и группы;
chmod ugo+rwx <file name>-  разрешить все для всех;
– для просмотра истории команд.
используется команда history.

3. Что такое файловая система? Приведите примеры с краткой характеристикой.
Файловая система определяет и контролирует, как будут храниться и именоваться данные на носителе/накопителе информации: флешке, жестком или ssd диске и других. От нее зависит способ хранения данных на накопителе, сам формат данных и то, как они будут записываться/читаться в дальнейшем. 
FAT (таблица размещения файлов) — это простая ФС с классической архитектурой. Используется исключительно для небольших флеш накопителей, дисков и простых структур папок.
FAT32 — это разновидность файловой системы FAT. На данный момент является предпоследней версией этой ОС, прямом перед exFAT. Имеет расширенный размер тома, т.е. использует 32-разрядную адресацию кластеров. Представляет собой пространство, разделенное на три части: одна область для служебных структур, форма указателей в виде таблиц и зона для хранения самих файлов.
NTFS — это файловая система, являющаяся стандартом для Windows и других ОС. Поддерживается практическими всеми устройствами и не имеет лимита на размер файлов в 4 Гб.
exFAT — это улучшенная система FAT32, избавленная от ее недостатков. Была создана специально для SSD дисков, здесь используется куда меньшее количество перезаписей секторов, что увеличивает срок службы таких дисков. Ограничения на размер данных нет и увеличен размер кластера.

4. Как посмотреть, какие файловые системы подмонтированы в ОС?
С помощью команды findmnt --all можно посмотреть все файловые системы.

5. Как удалить зависший процесс?
Сначала узнаем идентификатор процесса с помощью команды ps:  ps aux | grep ping. Затем используем команду kill <индентификатор процесса>

# Вывод

В ходе выполнения работы мы приобрели практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.


# Библиография

1. Кулябов Д. С., Королькова А. В., Геворкян М. Н. Установка и конфигурация операционной системы на виртуальную машину [Текст] / Кулябов Д. С., Королькова А. В., Геворкян М. Н. - Москва: - 14 с. [^1]:  Установка и конфигурация операционной системы на виртуальную машину.
2. Справочник 70 основных команд Linux: полное описание с примерами (https://eternalhost.net/blog/sozdanie-saytov/osnovnye-komandy-linux)