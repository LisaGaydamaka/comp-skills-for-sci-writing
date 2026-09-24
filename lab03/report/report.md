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
- Проверить греческие буквы и математические шрифты.
- Исследовать параметры выравнивания формул и расположения их номеров.

# Теоретическое введение

В LaTeX используются строчный и выключной математические режимы, в которых автоматически формируются интервалы между математическими символами. Пакет amsmath расширяет возможности набора формул, выравниваний и многострочных математических выражений.

# Выполнение лабораторной работы

1. Взять примеры математических выражений из главы.

![Рис.1](image/1.png)

2. Переключать их между inline math и display math.

![Рис.2](image/2.png)

3. Посмотреть, как меняется результат.

![Рис.3](image/3.png)

4. Добавить другие греческие буквы — строчные и прописные.

![Рис.4](image/4.png)

5. Поэкспериментировать с командами изменения математических шрифтов.

![Рис.5](image/5.png)

6. Попробовать вкладывать команды изменения шрифтов друг в друга.

![Рис.6](image/6.png)

7. Добавить параметр класса `[fleqn]`.

![Рис.7](image/7.png)

8. Проверить, как display-формулы выравниваются влево.

![Рис.8](image/8.png)

9. Добавить параметр `[leqno]`.

![Рис.9](image/9.png)

10. Проверить, как номера формул перемещаются на левую сторону.

![Рис.10](image/10.png)

# Выводы

Благодаря данной работе я научилась набирать математические выражения и использовать основные возможности математического режима LaTeX.
