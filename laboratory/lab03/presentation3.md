---
## Front matter
lang: ru-RU
title: Лабораторная работа №3
subtitle: Дискреционное разграничение прав в Linux. Два пользователя
author: Victoria M. Shutenko
institute: RUDN University, Moscow, Russian Federation
date: 24 September, 2022, Moscow, Russian Federation

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

Приобрести практические навыки работы в консоли с атрибутами файлов для групп пользователей.


# Результаты выполнения лабораторной работы

![Наличие пользователя guest.](images/0.png){ #fig:001 width=70% }

#Результаты выполнения лабораторной работы

![Создания пользователя guest2.](images/1.png){ #fig:001 width=70% }

# Результаты выполнения лабораторной работы

![Добавление пользователя guest2.](images/2.png){ #fig:001 width=70% }

# Результаты выполнения лабораторной работы

 ![Вход в систему от двух пользователей на двух разных консолях: guest справа и guest2 слева.](images/3.png){ #fig:001 width=70% }

# Результаты выполнения лабораторной работы

![Определение директории, в которой нахожусь.](images/4.png){ #fig:001 width=70% }

# Результаты выполнения лабораторной работы

![Уточнения данных о пользователях guest и guest1. Команда groups.](images/5.png){ #fig:001 width=40% }


![Уточнения данных о пользователях guest и guest1. Команды groups, id -Gn, id -G.](images/6.png){ #fig:001 width=40% }

# Результаты выполнения лабораторной работы

![](images/7.png){ #fig:001 width=30% }

![](images/8.png){ #fig:001 width=30% }

![Команда "cat".](images/9.png){ #fig:001 width=30% }

# Результаты выполнения лабораторной работы

![Регистрация пользователя guest2 в группе guest.](images/10.png){ #fig:001 width=70% }

# Результаты выполнения лабораторной работы

![Изменение прав директории /home/guest](images/11.png){ #fig:001 width=70% }

# Итоги выполнения лабораторной работы

- Создан пользователь guest2
- Заполнена таблица «Установленные права и разрешённые действия»
