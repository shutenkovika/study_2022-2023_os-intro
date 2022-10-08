---
## Front matter
lang: ru-RU
title: Лабораторная работа №5
subtitle: Дискреционное разграничение прав в Linux. Исследование влияния дополнительных атрибутов
author: Victoria M. Shutenko
institute: RUDN University, Moscow, Russian Federation
date: 8 October, 2022, Moscow, Russian Federation

## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

# Цель выполнения лабораторной работы

Изучение механизмов изменения идентификаторов, применения
SetUID- и Sticky-битов. Получение практических навыков работы в консоли с дополнительными атрибутами. Рассмотрение работы механизма
смены идентификатора процессов пользователей, а также влияние бита
Sticky на запись и удаление файлов.1

# Результаты выполнения лабораторной работ


## Создание программы

![Код simpleid.c.](images/2.png){ #fig:002 width=70% }

## Создание программы

![Компилирование и запуск файла simpleid.c. Выполнение команды id](images/3.png){ #fig:003 width=70% }

## Создание программы

![Код simpleid2.c](images/4.png){ #fig:004 width=70% }

## Создание программы

![Компилирование и запуск simpleid2.c.](images/5.png){ #fig:005 width=50% }


![Выполнение  команд.](images/6.png){ #fig:006 width=50% }

## Создание программы

![ Проверка правильности.](images/7.png){ #fig:007 width=50% }


![Запуск simpleid2 и id.](images/8.png){ #fig:008 width=50% }

## Создание программы

![Код readfile.c.](images/9.png){ #fig:009 width=70% }

## Создание программы

![Компиляция и запуск readfile.c.](images/10.png){ #fig:010 width=50% }

## Создание программы

![Запуск readfile.c.](images/11.png){ #fig:011 width=50% }

## Создание программы

![Запуск readfile.c.](images/12.png){ #fig:012 width=50% }

## Исследование Sticky-бита

![Просмотр атрибутов file01.txt](images/13.png){ #fig:013 width=70% }

## Исследование Sticky-бита

![Запись файла и проверка.](images/14.png){ #fig:014 width=70% }

## Исследование Sticky-бита

![Удаление файла, вход и выход из режима суперпользователя.](images/15.png){ #fig:015 width=70% }

# Итоги выполнения лабораторной работы

- Получили практические навыки работы в консоли с дополнительными атрибутами.
- Создали 3 файла, скомпилировали их и запустили
