---
## Front matter
lang: ru-RU
title: Отчёт по лабораторной работе 7
author: 'Радимов Игорь'

## Formatting
toc: false
slide_level: 2
theme: metropolis
mainfont: Ubuntu
romanfont: Ubuntu
sansfont: Ubuntu
monofont: Ubuntu
header-includes:
  - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
  - '\makeatletter'
  - '\beamer@ignorenonframefalse'
  - '\makeatother'
aspectratio: 43
section-titles: true
---

## Цель работы

Освоить на практике применение режима однократного гаммирования.

## Задание

Лабораторная работа подразумевает использование языков программирования для создания программы для щифрования и дещифрования в режиме однократного гаммирования.

# Выполнение лабораторной работы

1. Импортируем библиотеки random,string. Зададим строковую переменную text.

![рис.1. Импорт библиотек.](images/1.jpg){ #fig:001 width=70% }

---

2. Зададим генератор ключа и напечатаем ключ по этой строке.

![рис.2. Генератор ключа.](images/2.jpg){ #fig:002 width=70% }

---

3. Зададим функцию для гаммирования, обнаружения ключа и дешифрования.

![рис.3. Функция gamm.](images/3.jpg){ #fig:003 width=70% }

---

4. Получим закодированную строку и её шестнадцатеричный вид. Попробуем подобрать ключ и увидим, что он неверный. Используем настоящий ключ и декодированную строку.

![рис.4.](images/4.jpg){ #fig:004 width=70% }

---

## {.standout}

Спасибо за внимание
