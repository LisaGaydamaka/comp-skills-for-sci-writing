---
## Front matter
title: "Отчёт по лабораторной работе 6"
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

Целью данной работы является освоение создания библиографической базы и оформления цитирований средствами BibTeX и biblatex.

# Задание

- Проверить работу библиографии с natbib/BibTeX и biblatex/Biber.

![Рис.1](../image/1.png)

- Добавить новые библиографические записи и цитирования.

![Рис.2](../image/2.png)

- Сравнить обычный и числовой стили цитирования.

![Рис.3](../image/3.png)

# Теоретическое введение

Библиографические данные обычно хранятся отдельно от основного документа в файлах .bib и подключаются по ключам цитирования. Для обработки библиографии могут применяться связки natbib с BibTeX или biblatex с Biber.

# Выполнение лабораторной работы

1. Попробовать пример с `natbib` и BibTeX.

2. Для него выполнить последовательность:

```text
LaTeX
BibTeX
LaTeX
LaTeX
```

3. Попробовать пример с `biblatex` и Biber.
4. Для него выполнить:

```text
LaTeX
Biber
LaTeX
```

5. Создать новые записи в `.bib`-базе.
6. Добавить новые цитирования этих записей.
7. Добавить цитирование источника, которого **нет в базе**.
8. Посмотреть, как оно отобразится.
9. Попробовать числовой стиль для `natbib`.
10. Попробовать `style=numeric` для `biblatex`.

# Выводы

Благодаря данной работе я научилась создавать библиографическую базу и оформлять цитирования средствами BibTeX и biblatex.
