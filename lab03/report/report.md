---
## Front matter
title: "Отчёт по лабораторной работе 3"
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

Целью данной работы является освоение набора математических выражений и основных возможностей математического режима LaTeX.

# Задание

- Сравнить строчный и выключной математические режимы.

![Рис.1](../image/1.png)

- Проверить греческие буквы и математические шрифты.

![Рис.2](../image/2.png)

- Исследовать параметры выравнивания формул и расположения их номеров.

![Рис.3](../image/3.png)

# Теоретическое введение

В LaTeX используются строчный и выключной математические режимы, в которых автоматически формируются интервалы между математическими символами. Пакет amsmath расширяет возможности набора формул, выравниваний и многострочных математических выражений.

# Выполнение лабораторной работы

1. Взять примеры математических выражений из главы.

2. Переключать их между inline math и display math.
3. Посмотреть, как меняется результат.
4. Добавить другие греческие буквы — строчные и прописные.
5. Поэкспериментировать с командами изменения математических шрифтов.
6. Попробовать вкладывать команды изменения шрифтов друг в друга.
7. Добавить параметр класса `[fleqn]`.
8. Проверить, как display-формулы выравниваются влево.
9. Добавить параметр `[leqno]`.
10. Проверить, как номера формул перемещаются на левую сторону.

# Выводы

Благодаря данной работе я научилась набирать математические выражения и использовать основные возможности математического режима LaTeX.
