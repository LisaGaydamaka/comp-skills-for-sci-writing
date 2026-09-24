# Подробные условия лабораторных работ по курсу Practical Scientific Writing

Источник: `Practical-scientific-writing.pdf`.

Ниже — уточнённые условия лабораторных работ. Начиная с лабораторной №2 количество заданий здесь строго совпадает с количеством пунктов в `LAB_TASKS.md`. Каждый пункт из краткого файла имеет отдельное подробное задание с конкретными действиями и, где это необходимо, примером кода. Лабораторная №1 оставлена без дополнительных пояснений.

## Лабораторная работа №1 — Подготовка рабочего пространства

1. Настроить структуру рабочего пространства лабораторных работ.
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
12. Каталоги лабораторных должны называться:
    - `lab01`;
    - `lab02`;
    - и т. д.
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


---

## Лабораторная работа №2 — Структура документа LaTeX

## Задание 1. Создать файл `first.tex`

Создайте файл:

```text
first.tex
```

## Задание 2. Вставить простой LaTeX-документ

Вставьте в `first.tex`:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}

\begin{document}

Hey world!

This is a first document.

\end{document}
```

Сохраните файл.

## Задание 3. Скомпилировать документ

В каталоге с `first.tex` выполните:

```bash
pdflatex first.tex
```

## Задание 4. Получить `first.pdf`

После успешной компиляции убедитесь, что рядом с `first.tex` появился файл:

```text
first.pdf
```

## Задание 5. Открыть и проверить PDF

Откройте `first.pdf` и убедитесь, что в нём есть строки:

```text
Hey world!
This is a first document.
```

## Задание 6. Разобраться со структурой документа

Замените содержимое `first.tex` на:

```latex
\documentclass[a4paper,12pt]{article}
\usepackage[T1]{fontenc}

% Всё выше begin{document} — преамбула.

\begin{document}

This is the document body.

\begin{center}
This text is inside an environment.
\end{center}

\end{document}
```

Проверьте на этом примере:
- команду LaTeX;
- обязательный аргумент `{}`;
- необязательный аргумент `[]`;
- преамбулу;
- тело документа;
- окружение `\begin{...}` / `\end{...}`.

## Задание 7. Использовать комментарии `%`

Добавьте в тело документа:

```latex
This text will be visible.

% This line is a comment and must not be visible.

This text will also be visible.
```

Скомпилируйте документ и убедитесь, что строка-комментарий в PDF не отображается.

## Задание 8. Разделить текст на абзацы

Добавьте:

```latex
This is the first paragraph.

This is the second paragraph.

This is the third paragraph.
```

Скомпилируйте документ. В PDF должны быть три отдельных абзаца.

## Задание 9. Проверить обычные и неразрывные пробелы

Добавьте:

```latex
Word1 Word2

Word1     Word2

Figure~1
Section~2
```

Скомпилируйте документ. Несколько обычных пробелов должны отображаться как один, а `~` должен создавать неразрывный пробел.

## Задание 10. Запустить LaTeX из терминала двумя способами

Выполните по очереди:

```bash
pdflatex first
```

```bash
pdflatex first.tex
```

Обе команды должны компилировать один и тот же документ.

## Задание 11. Освоить специальные символы LaTeX

Добавьте:

```latex
Curly braces: \{ \}

Dollar: \$

Percent: \%

Ampersand: \&

Hash: \#

Underscore: \_

Backslash: \textbackslash

Caret: \textasciicircum

Tilde: \textasciitilde
```

## Задание 12. Проверить правильный вывод специальных символов

Скомпилируйте документ и убедитесь, что в PDF отображаются:

```text
{ } $ % & # _ \ ^ ~
```

> В главе 2 отдельного раздела `Exercises` нет.

---

## Лабораторная работа №3 — Набор математики

## Задание 1. Взять примеры математических выражений из главы

Создайте файл `math.tex`:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{amsmath}
\usepackage{amsfonts}

\begin{document}

$y = mx + c$

\[
5^2 = 3^2 + 4^2
\]

\end{document}
```

## Задание 2. Переключать выражения между inline math и display math

Сначала используйте:

```latex
$y = mx + c$
```

Затем замените на:

```latex
\[
y = mx + c
\]
```

Скомпилируйте оба варианта.

## Задание 3. Посмотреть, как меняется результат

Сравните два PDF:
- inline-формула должна находиться внутри строки;
- display-формула должна находиться отдельно от текста.

## Задание 4. Добавить строчные и прописные греческие буквы

Добавьте:

```latex
\[
\alpha \quad \beta \quad \gamma \quad \delta \quad
\theta \quad \lambda \quad \pi \quad \sigma \quad \omega
\]

\[
\Gamma \quad \Delta \quad \Theta \quad \Lambda \quad
\Pi \quad \Sigma \quad \Omega
\]
```

## Задание 5. Поэкспериментировать с математическими шрифтами

Добавьте:

```latex
\[
\mathrm{ABC} \quad
\mathit{ABC} \quad
\mathbf{ABC} \quad
\mathsf{ABC} \quad
\mathtt{ABC} \quad
\mathbb{ABC}
\]
```

Скомпилируйте и сравните оформление.

## Задание 6. Попробовать вложенные команды шрифтов

Добавьте:

```latex
\[
\mathbf{\mathit{ABC}}
\]

\[
\mathit{\mathbf{ABC}}
\]

\[
\mathrm{\mathbf{ABC}}
\]
```

Скомпилируйте и сравните варианты.

## Задание 7. Добавить параметр класса `[fleqn]`

Измените первую строку документа на:

```latex
\documentclass[fleqn]{article}
```

## Задание 8. Проверить выравнивание display-формул влево

Добавьте:

```latex
\[
x^2 + y^2 = z^2
\]
```

Скомпилируйте и убедитесь, что формула расположена слева.

## Задание 9. Добавить параметр `[leqno]`

Используйте:

```latex
\documentclass[leqno]{article}
```

и нумерованную формулу:

```latex
\begin{equation}
x^2 + y^2 = z^2
\end{equation}
```

## Задание 10. Проверить положение номера формулы слева

Скомпилируйте документ и убедитесь, что номер уравнения находится слева.

---

## Лабораторная работа №4 — Вставка графики

## Задание 1. Вставить собственное изображение

Поместите, например, `my-image.png` рядом с `.tex`-файлом и используйте:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{graphicx}

\begin{document}

\includegraphics[width=0.5\textwidth]{my-image.png}

\end{document}
```

## Задание 2. Поэкспериментировать с `height`, `width`, `angle`, `scale`

По очереди проверьте:

```latex
\includegraphics[height=3cm]{my-image.png}
\includegraphics[width=0.5\textwidth]{my-image.png}
\includegraphics[width=0.4\textwidth,angle=30]{my-image.png}
\includegraphics[scale=0.5]{my-image.png}
```

## Задание 3. Задать ширину относительно `\textwidth`

Используйте:

```latex
\includegraphics[width=0.5\textwidth]{my-image.png}
```

## Задание 4. Задать ширину относительно `\linewidth`

Используйте:

```latex
\includegraphics[width=0.5\linewidth]{my-image.png}
```

## Задание 5. Сравнить `twocolumn` и обычный режим

Сначала используйте:

```latex
\documentclass[twocolumn]{article}
```

Затем:

```latex
\documentclass{article}
```

В обоих вариантах оставьте изображения с `\textwidth` и `\linewidth` и сравните результат.

## Задание 6. Использовать `lipsum`

В преамбулу добавьте:

```latex
\usepackage{lipsum}
```

В тело документа:

```latex
\lipsum[1-6]
```

## Задание 7. Добавить плавающее изображение `figure`

Используйте:

```latex
\begin{figure}[ht]
\centering
\includegraphics[width=0.5\textwidth]{my-image.png}
\caption{My image}
\end{figure}
```

## Задание 8. Проверить `h`, `t`, `b`, `p`

По очереди меняйте:

```latex
\begin{figure}[h]
\begin{figure}[t]
\begin{figure}[b]
\begin{figure}[p]
```

Каждый вариант компилируйте отдельно.

## Задание 9. Посмотреть, как спецификаторы взаимодействуют

Используйте длинный текст:

```latex
\lipsum[1-10]
```

и несколько рисунков с разными спецификаторами, затем сравните их фактическое размещение.

## Задание 10. Добавить нумерованные элементы

Добавьте:

```latex
\section{First section}
\subsection{First subsection}

\begin{enumerate}
\item First item
\item Second item
\end{enumerate}
```

## Задание 11. Проверить количество запусков для `\label` и `\ref`

Используйте:

```latex
See section~\ref{sec:first}.

\section{First section}
\label{sec:first}
```

Запустите `pdflatex` один раз, затем второй раз и сравните ссылку.

## Задание 12. Добавить float-объекты

Добавьте ещё один объект:

```latex
\begin{figure}[ht]
\centering
\includegraphics[width=0.4\textwidth]{my-image.png}
\caption{Second image}
\end{figure}
```

## Задание 13. Поставить `\label` перед `\caption`

Используйте:

```latex
\begin{figure}[ht]
\centering
\includegraphics[width=0.4\textwidth]{my-image.png}
\label{fig:test}
\caption{Test image}
\end{figure}

Figure~\ref{fig:test}.
```

Скомпилируйте два раза.

## Задание 14. Поставить `\label` правильно

Измените фрагмент на:

```latex
\begin{figure}[ht]
\centering
\includegraphics[width=0.4\textwidth]{my-image.png}
\caption{Test image}
\label{fig:test}
\end{figure}

Figure~\ref{fig:test}.
```

Скомпилируйте два раза и сравните результат с предыдущим пунктом.

## Задание 15. Поставить `\label` после `\end{equation}`

Используйте:

```latex
\begin{equation}
e^{i\pi}+1=0
\end{equation}
\label{eq:test}

Equation~\ref{eq:test}.
```

## Задание 16. Посмотреть, что произойдёт

Скомпилируйте два раза и сравните с правильным вариантом:

```latex
\begin{equation}
e^{i\pi}+1=0
\label{eq:test}
\end{equation}

Equation~\ref{eq:test}.
```

---

## Лабораторная работа №5 — Таблицы

## Задание 1. Взять простую таблицу из примера

Используйте:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}

\begin{document}

\begin{tabular}{lll}
Animal & Food & Size \\
dog & meat & medium \\
horse & hay & large \\
frog & flies & small \\
\end{tabular}

\end{document}
```

## Задание 2. Поэкспериментировать с оформлением таблицы

Добавьте линии:

```latex
\begin{tabular}{|l|l|l|}
\hline
Animal & Food & Size \\
\hline
dog & meat & medium \\
horse & hay & large \\
frog & flies & small \\
\hline
\end{tabular}
```

## Задание 3. Проверить выравнивание `l`, `c`, `r`

По очереди используйте:

```latex
\begin{tabular}{lll}
```

```latex
\begin{tabular}{ccc}
```

```latex
\begin{tabular}{rrr}
```

## Задание 4. Сделать строку со слишком малым количеством элементов

Для трёх столбцов добавьте:

```latex
dog & meat \\
```

Скомпилируйте и посмотрите результат.

## Задание 5. Сделать строку со слишком большим количеством элементов

Добавьте:

```latex
horse & hay & large & extra \\
```

Попробуйте скомпилировать и посмотрите сообщение LaTeX.

## Задание 6. Использовать `\multicolumn`

Добавьте:

```latex
fuath & \multicolumn{2}{c}{unknown} \\
```

## Задание 7. Объединить несколько столбцов

Проверьте полный пример:

```latex
\begin{tabular}{lll}
Animal & Food & Size \\
dog & meat & medium \\
fuath & \multicolumn{2}{c}{unknown} \\
\end{tabular}
```

---

## Лабораторная работа №6 — Библиография

## Задание 1. Попробовать пример с `natbib` и BibTeX

Создайте `learnlatex.bib`:

```bibtex
@book{Graham1995,
  author = {Ronald L. Graham and Donald E. Knuth and Oren Patashnik},
  title = {Concrete Mathematics},
  publisher = {Addison-Wesley},
  year = {1995}
}
```

Создайте `natbib-example.tex`:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{natbib}

\begin{document}

The mathematics showcase is from \citet{Graham1995}.

\bibliographystyle{plainnat}
\bibliography{learnlatex}

\end{document}
```

## Задание 2. Выполнить последовательность LaTeX → BibTeX → LaTeX → LaTeX

Выполните:

```bash
pdflatex natbib-example.tex
bibtex natbib-example
pdflatex natbib-example.tex
pdflatex natbib-example.tex
```

## Задание 3. Попробовать пример с `biblatex` и Biber

Создайте `biblatex-example.tex`:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage[style=authoryear]{biblatex}
\addbibresource{learnlatex.bib}

\begin{document}

The mathematics showcase is from \autocite{Graham1995}.

\printbibliography

\end{document}
```

## Задание 4. Выполнить последовательность LaTeX → Biber → LaTeX

Выполните:

```bash
pdflatex biblatex-example.tex
biber biblatex-example
pdflatex biblatex-example.tex
```

## Задание 5. Создать новые записи в `.bib`

Добавьте в `learnlatex.bib`:

```bibtex
@book{TestBook2026,
  author = {Ivan Ivanov},
  title = {Test Book},
  publisher = {Test Publisher},
  year = {2026}
}
```

## Задание 6. Добавить новые цитирования

Для `natbib` добавьте:

```latex
New source: \citep{TestBook2026}.
```

Для `biblatex`:

```latex
New source: \autocite{TestBook2026}.
```

## Задание 7. Добавить цитирование отсутствующего источника

Добавьте:

```latex
\citep{MissingSource}
```

или:

```latex
\autocite{MissingSource}
```

Не добавляйте `MissingSource` в `.bib`.

## Задание 8. Посмотреть, как отображается отсутствующая ссылка

Скомпилируйте документ и проверьте:
- отображение ссылки;
- предупреждение LaTeX/BibTeX/Biber.

## Задание 9. Попробовать числовой стиль для `natbib`

Замените:

```latex
\usepackage{natbib}
```

на:

```latex
\usepackage[numbers]{natbib}
```

Скомпилируйте документ заново.

## Задание 10. Попробовать `style=numeric` для `biblatex`

Замените:

```latex
\usepackage[style=authoryear]{biblatex}
```

на:

```latex
\usepackage[style=numeric]{biblatex}
```

Выполните LaTeX → Biber → LaTeX и сравните результат.

---

## Лабораторная работа №7 — Презентации LaTeX

В этой главе нет отдельного раздела `Exercises`, поэтому подробные задания соответствуют 11 пунктам из краткого файла.

## Задание 1. Создать презентацию класса `beamer`

Создайте `presentation.tex`:

```latex
\documentclass{beamer}

\author{Your Name}
\title{Practical Scientific Writing}

\begin{document}

\end{document}
```

## Задание 2. Выбрать тему `Copenhagen`

Добавьте в преамбулу:

```latex
\usetheme{Copenhagen}
```

## Задание 3. Указать автора и название презентации

Используйте:

```latex
\author{Your Name}
\title{Practical Scientific Writing}
```

## Задание 4. Создать титульный слайд

Добавьте:

```latex
\begin{frame}
\titlepage
\end{frame}
```

## Задание 5. Создавать слайды через `frame`

Добавьте:

```latex
\begin{frame}{Article}
Some text about the article.
\end{frame}
```

## Задание 6. Добавлять текст, блоки, списки и колонки

Используйте, например:

```latex
\begin{frame}{Content}

\begin{block}{Example}
Block text.
\end{block}

\begin{itemize}
\item First item
\item Second item
\end{itemize}

\begin{columns}
\begin{column}{0.5\textwidth}
Left column.
\end{column}
\begin{column}{0.5\textwidth}
Right column.
\end{column}
\end{columns}

\end{frame}
```

## Задание 7. Использовать `\pause`

Добавьте:

```latex
\begin{frame}{Pause example}
First text.

\pause

Second text.

\pause

Third text.
\end{frame}
```

## Задание 8. Использовать `\uncover`

Добавьте:

```latex
\begin{frame}{Uncover example}

\uncover<1->{First text.}

\uncover<2->{Second text.}

\uncover<3->{Third text.}

\end{frame}
```

## Задание 9. Попробовать другие темы оформления

Замените тему на:

```latex
\usetheme{Warsaw}
\usecolortheme{beaver}
```

Скомпилируйте и сравните оформление.

## Задание 10. Изучить три способа создания научных постеров

Проверьте три варианта:
- `a0poster`;
- `beamerposter`;
- `tikzposter`.

Минимальный пример `tikzposter`:

```latex
\documentclass[24pt,a0paper,portrait]{tikzposter}

\title{My Scientific Poster}
\author{Your Name}

\begin{document}
\maketitle

\block{Introduction}{
Introduction text.
}

\end{document}
```

## Задание 11. Освоить основные элементы постера

Добавьте в выбранный вариант постера:
- заголовок;
- автора;
- организацию;
- колонки;
- блоки;
- изображения;
- таблицы;
- библиографию.

> В книге не указано требование вроде «сделать презентацию на N слайдов» или «обязательно сдать постер».

---

## Лабораторная работа №8 — TikZ: диаграммы и чертежи как код

В кратком файле здесь три задания, поэтому в подробном файле также три задания.

## Задание 1. Построить граф в TikZ

Создайте `graph.tex`:

```latex
\documentclass[border=1cm]{standalone}
\usepackage{tikz}

\begin{document}

\begin{tikzpicture}

\node[circle,draw] (A) at (0:2) {A};
\node[circle,draw] (B) at (60:2) {B};
\node[circle,draw] (C) at (120:2) {C};
\node[circle,draw] (D) at (180:2) {D};
\node[circle,draw] (E) at (240:2) {E};
\node[circle,draw] (F) at (300:2) {F};

\draw (A) -- (B);
\draw[dashed] (B) -- (C);
\draw[->] (C) -- (D);
\draw[dotted] (D) -- (E);
\draw[<->] (E) -- (F);
\draw[thick] (F) -- (A);

\end{tikzpicture}

\end{document}
```

Граф не обязан полностью совпадать с образцом; главное — сохранить похожие свойства.

## Задание 2. Построить графики `y=e^x` и `y=ln(x)`

Создайте `plot.tex`:

```latex
\documentclass[border=1cm]{standalone}
\usepackage{tikz}

\begin{document}

\begin{tikzpicture}[scale=1.2]

\draw[->] (-3,0) -- (3,0) node[right] {$x$};
\draw[->] (0,-3) -- (0,3) node[above] {$y$};
\node[below left] at (0,0) {$O$};

\draw (1,0.08) -- (1,-0.08) node[below] {$1$};
\draw (0.08,1) -- (-0.08,1) node[left] {$1$};

\draw[domain=-2.5:1,samples=100,smooth]
plot (\x,{exp(\x)})
node[right] {$y=e^x$};

\draw[domain=0.08:3,samples=100,smooth]
plot (\x,{ln(\x)})
node[right] {$y=\ln(x)$};

\end{tikzpicture}

\end{document}
```

Скомпилируйте:

```bash
pdflatex plot.tex
```

## Задание 3. Построить несколько итераций ковра Серпинского

Создайте `sierpinski-carpet.tex`:

```latex
\documentclass[border=1cm]{standalone}
\usepackage{tikz}
\usetikzlibrary{math}

\begin{document}

\begin{tikzpicture}

% Здесь должна находиться рекурсивная функция ковра Серпинского.

\end{tikzpicture}

\end{document}
```

Измените пример треугольника Серпинского из книги так, чтобы:
1. использовался квадрат;
2. квадрат делился на сетку `3 × 3`;
3. центральная часть пропускалась;
4. рекурсия применялась к остальным восьми квадратам;
5. можно было менять глубину рекурсии;
6. были получены несколько итераций ковра Серпинского.
