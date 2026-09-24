---
## Front matter
title: "Отчёт по лабораторной работе 8"
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

Целью данной работы является освоение создания диаграмм и графиков программным способом с использованием TikZ.

# Задание

- Построить граф с вершинами и рёбрами средствами TikZ.

![Рис.1](../image/1.png)

- Построить графики функций по образцу из книги.

![Рис.2](../image/2.png)

- Модифицировать рекурсивный пример для построения ковра Серпинского.

![Рис.3](../image/3.png)

# Теоретическое введение

TikZ позволяет описывать графические объекты непосредственно командами LaTeX с использованием координат, узлов, линий и кривых. Этот подход позволяет воспроизводимо строить графы, функции и рекурсивные геометрические изображения.

# Выполнение лабораторной работы

В этой лабораторной есть три конкретных упражнения.

### Задание 1

1. Открыть TeX-редактор.

2. Создать документ `standalone`.
3. Подключить `\usepackage{tikz}`.
4. Воспроизвести граф, изображённый в книге.
5. Граф не обязан выглядеть абсолютно идентично.
6. Главное — получить граф с похожими свойствами.
7. Попробовать расположить вершины по окружности с помощью полярных координат.
8. На образце имеются вершины `A`, `B`, `C`, `D`, `E`, `F`, различные типы и цвета линий и подписи весов.

### Задание 2

1. Создать TikZ-график по изображению из книги.
2. Можно использовать готовую структуру документа и сосредоточиться только на TikZ.
3. На образце нужно воспроизвести:
   - ось `x`;
   - ось `y`;
   - начало координат `O`;
   - график `y=e^x`;
   - график `y=ln(x)`;
   - отметки `x=1` и `y=1`.

### Задание 3

1. Взять приведённый в книге код для треугольников Серпинского.
2. Изменить его.
3. Вместо треугольника Серпинского построить **ковёр Серпинского**.
4. Показать несколько итераций ковра Серпинского.

# Выводы

Благодаря данной работе я научилась создавать диаграммы и графики программным способом с использованием TikZ.
