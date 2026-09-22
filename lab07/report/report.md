---
## Front matter
title: "Отчёт по лабораторной работе 7"
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

Целью данной работы является освоение создания презентаций и научных постеров средствами LaTeX.

# Задание

- Создать презентацию Beamer и оформить основные слайды.
- Освоить последовательное появление элементов и многоколоночную компоновку.
- Изучить основные способы создания научных постеров в LaTeX.

# Теоретическое введение

Класс beamer позволяет создавать презентации в LaTeX, используя кадры, темы оформления, блоки и средства пошагового показа содержимого. Для научных постеров могут применяться классы и пакеты a0poster, beamerposter и tikzposter.

# Выполнение лабораторной работы

В этой главе **нет отдельного раздела `Exercises`**, поэтому книга не задаёт конкретное итоговое упражнение.

1. Создать презентацию класса `\documentclass{beamer}`.

![Рис.1](image\picture1.png)  

2. Выбрать тему, например `\usetheme{Copenhagen}`.
3. Указать автора и название презентации.
4. Создать титульный слайд.
5. Создавать слайды через окружение `frame`.
6. Добавлять текст, блоки, списки и колонки.
7. Использовать `\pause` для последовательного появления элементов.
8. Использовать `\uncover` для более точного управления появлением элементов.
9. Попробовать другие темы оформления, например:

```latex
\usetheme{Warsaw}
\usecolortheme{beaver}
```

10. Изучить создание научных постеров тремя способами:
    - `a0poster`;
    - `beamerposter`;
    - `tikzposter`.
11. Для постера освоить:
    - заголовок;
    - автора;
    - организацию;
    - колонки;
    - блоки;
    - изображения;
    - таблицы;
    - библиографию.

> В книге не указано требование вроде «сделать презентацию на N слайдов» или «обязательно сдать постер».

# Выводы

Благодаря данной работе я освоила создание презентаций и научных постеров средствами LaTeX.
