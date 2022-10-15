---
## Front matter
lang: ru-RU
title: Лабораторная работа №6
subtitle: Мандатное разграничение прав в Linux атрибутов
author: Victoria M. Shutenko
institute: RUDN University, Moscow, Russian Federation
date: 15 October, 2022, Moscow, Russian Federation

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

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux1.
Проверить работу SELinx на практике совместно с веб-сервером Apache.

# Результаты выполнения лабораторной работ

## Подготовка к выполнению лабораторной работы №6

![Установка httpd.](images/1.png){ #fig:001 width=70% }

## Подготовка к выполнению лабораторной работы №6

![Файл httpd.conf.](images/2.png){ #fig:002 width=70% }

## Подготовка к выполнению лабораторной работы №6

![Задание параметра ServerName](images/3.png){ #fig:003 width=70% }

## Подготовка к выполнению лабораторной работы №6

![Проверка наличия параметра ServerName](images/4.png){ #fig:004 width=70% }

## Подготовка к выполнению лабораторной работы №6

![Отключение пакетного фильтра.](images/5.png){ #fig:005 width=70% }

## Работа SELinux в режиме enforcing.


![Проверка работоспособности SELinux.](images/6.png){ #fig:006 width=70% }

## Проверка работоспособности веб-сервера с помощью браузера


![Обращение к веб-серверу.](images/7.png){ #fig:007 width=70% }

## Контекст безопасности

![Определение контекста безопасности.](images/8.png){ #fig:008 width=70% }

## Текущее состояние переключателей SELinux для Apache 

![Определение текущего состояния переключателей SELinux.](images/9.png){ #fig:009 width=70% }

## Статистика по политике.

![Статистика по политике.](images/10.png){ #fig:010 width=70% }

## Определение типов файлов и поддиректорий, находящихся в директории /var/www и в директории /var/www/html:

![Определение типов файлов и поддиректорий.](images/11.png){ #fig:011 width=70% }

## Круг пользователей, которым разрешено создание файлов в директории /var/www/html.

![Определение круга пользователей.](images/12.png){ #fig:012 width=70% }

## Создание html-файл /var/www/html/test.html 

![Файл test.html.](images/13.png){ #fig:013 width=70% }

## Проверка, изменение и просмотр контекста 

![Проверка, изменение и просмотр контекста.](images/14.png){ #fig:014 width=70% }

## Просмотр log-файлов веб-сервера Apache. 

![Cистемный лог-файл.](images/15.png){ #fig:015 width=70% }

## Изменение Listen 80 на Listen 81 в файле httpd.conf.

![Изменение Listen 80 на Listen 81 в файле httpd.conf.](images/16.png){ #fig:016 width=70% }

## Просмотр лог-файлов:

![Cистемный лог-файл.](images/17.png){ #fig:017 width=70% }

## Просмотр лог-файла audit.log 

![Лог-файл audit.log.](images/18.png){ #fig:018 width=70% }

## Добавление порта 81.

![Добавление порта 81.](images/19.png){ #fig:019 width=70% }

## Удаление порта 81.

![Возвращение контекста, удаление привязки к порту 81 и удаление файла test.html.](images/20.png){ #fig:020 width=70% }

# Итоги выполнения лабораторной работы

- Получили первое практическое знакомство с технологией SELinux1.
- Проверили работу SELinx на практике совместно с веб-сервером Apache.
- Создали файл test.html.

