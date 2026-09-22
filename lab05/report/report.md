---
## Front matter
title: "Отчёт по лабораторной работе 5"
author: "Елизавета Александровна Гайдамака"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью данной работы является освоение создания и форматирования таблиц средствами LaTeX.

# Задание

- Создать простую таблицу и проверить выравнивание столбцов.
- Исследовать поведение строк с неверным количеством элементов.
- Освоить объединение столбцов с помощью multicolumn.

# Теоретическое введение

Таблицы в LaTeX создаются с помощью окружения tabular, где для каждого столбца задаётся тип выравнивания. Ячейки разделяются символом &, строки завершаются двойным обратным слешем, а команда multicolumn позволяет объединять несколько столбцов.

# Выполнение лабораторной работы

1. Взять простую таблицу из примера книги.

![Рис.1](image\picture1.png)  

2. Начать экспериментировать с её оформлением.
3. Попробовать разные типы выравнивания столбцов: `l`, `c`, `r`.
4. Сделать строку, в которой **слишком мало элементов**, и посмотреть результат.
5. Сделать строку, в которой **слишком много элементов**, и посмотреть результат.
6. Использовать `\multicolumn`.
7. Объединить несколько столбцов.

# Выводы

Благодаря данной работе я научилась создавать и форматировать таблицы средствами LaTeX.
