---
## Front matter
title: "Отчёт по лабораторной работе 1"
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

Целью данной работы является подготовка рабочего пространства и настройка инструментов для выполнения лабораторных работ по курсу.

# Задание

- Настроить Git, ключи SSH и подпись коммитов.
- Организовать рабочее пространство и структуру каталогов курса.
- Установить необходимое программное обеспечение и TeX Live.

# Теоретическое введение

Для выполнения лабораторных работ используется единое рабочее пространство с системой контроля версий Git и согласованной структурой каталогов. Git Flow, правила оформления коммитов и TeX Live обеспечивают воспроизводимую организацию работы с исходными файлами курса.

# Выполнение лабораторной работы

1. Настроить структуру рабочего пространства лабораторных работ.

![Рис.1](image\picture1.png)  

2. Использовать:
   - Git Flow;
   - семантическое версионирование;
   - Conventional Commits.
3. Настроить Git:
   - `user.name`;
   - `user.email`;
   - UTF-8;
   - начальную ветку;
   - `core.autocrlf`;
   - `core.safecrlf`;
   - подписание коммитов.
4. Создать SSH-ключ `ed25519`.
5. Добавить SSH-ключ в `ssh-agent`.
6. Добавить SSH-ключ на используемые git-хостинги.
7. Создать PGP/GPG-ключ:
   - RSA;
   - 4096 бит;
   - указать имя и email.
8. Добавить GPG-ключ на git-хостинг.
9. Настроить автоматическое подписание Git-коммитов.
10. Установить необходимое ПО:
    - средства разработки;
    - Quarto;
    - Node.js;
    - `pnpm` / `yarn`;
    - `git-flow`;
    - `commitizen`;
    - `cz-customizable`;
    - `standard-version`.
11. Организовать рабочие каталоги курса.
12. Каталоги лабораторных должны называться `lab01`, `lab02` и т. д.
13. Создать репозиторий курса на основе шаблона.
14. Клонировать его локально.
15. Записать название курса в файл `COURSE`.
16. Выполнить:

```bash
make prepare
```

17. Добавить подготовленные файлы в Git и создать коммит.
18. Отправить изменения на сервер согласно рабочему процессу курса.
19. Инициализировать Git Flow.
20. Создать первый релиз `1.0.0`.
21. Создать `CHANGELOG.md`.
22. Создать теги и релиз.
23. Установить TeX Live.

# Выводы

Целью данной работы является подготовка рабочего пространства и настройка инструментов для выполнения лабораторных работ по курсу.
