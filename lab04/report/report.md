---
## Front matter
title: "Отчёт по лабораторной работе 4"
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

Целью данной работы является освоение вставки, размещения и перекрёстных ссылок на графические объекты в LaTeX.

# Задание

- Вставить собственное изображение и изменить параметры его отображения.
- Проверить различные способы размещения плавающих объектов.
- Освоить перекрёстные ссылки с помощью label и ref.

# Теоретическое введение

Для включения изображений в LaTeX применяется пакет graphicx и команда includegraphics, позволяющая управлять размером и ориентацией графики. Окружение figure используется для плавающих рисунков, а команды label и ref позволяют создавать автоматические перекрёстные ссылки.

# Выполнение лабораторной работы

1. Вставить **собственное изображение** вместо стандартной картинки из примеров.

![Рис.1](image/1.png)

2. Поэкспериментировать с параметрами `height`, `width`, `angle`, `scale`.

![Рис.2](image/2.png)

3. Для одной картинки задать ширину относительно `\textwidth`.

![Рис.3](image/3.png)

4. Для другой — относительно `\linewidth`.

![Рис.4](image/4.png)

5. Посмотреть разницу с `twocolumn` и без него.

![Рис.5](image/5.png)

6. Использовать `lipsum`, чтобы создать достаточно длинный текст.

![Рис.6](image/6.png)

7. Добавить плавающие изображения `figure`.

![Рис.7](image/7.png)

8. Проверить разные спецификаторы размещения: `h`, `t`, `b`, `p`.

![Рис.8](image/8.png)

9. Посмотреть, как они взаимодействуют.

![Рис.9](image/9.png)

10. Добавить новые нумерованные элементы: `section`, `subsection`, нумерованные списки.

![Рис.10](image/10.png)

11. Проверить, сколько запусков LaTeX требуется, чтобы корректно заработали `\label` и `\ref`.

![Рис.11](image/11.png)

12. Добавить float-объекты.

![Рис.12](image/12.png)

13. Поставить `\label` **перед** `\caption` и посмотреть результат.

![Рис.13](image/13.png)

14. Затем поставить его правильно — после/внутри `\caption`.

![Рис.14](image/14.png)

15. У уравнения поставить `\label` после `\end{equation}`.

![Рис.15](image/15.png)

16. Посмотреть, что произойдёт.

![Рис.16](image/16.png)

# Выводы

Благодаря данной работе я научилась вставлять и размещать графические объекты в LaTeX, а также создавать перекрёстные ссылки на них.
