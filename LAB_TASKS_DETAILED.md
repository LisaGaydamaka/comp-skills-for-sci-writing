# Подробные условия лабораторных работ по курсу Practical Scientific Writing

Источник: `Practical-scientific-writing.pdf`.

Ниже — уточнённые условия лабораторных работ. Для лабораторных 2–8 там, где формулировка задания сама по себе неочевидна, добавлены конкретные фрагменты LaTeX-кода и действия, которые нужно выполнить. Лабораторная №1 оставлена без дополнительных пояснений.

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

# Лабораторная работа №2 — Структура документа LaTeX

## Задание 1. Создать первый LaTeX-документ

Создайте файл:

```text
first.tex
```

Вставьте в него:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}

\begin{document}

Hey world!

This is a first document.

\end{document}
```

Сохраните файл.

Скомпилируйте:

```bash
pdflatex first.tex
```

После выполнения команды должен появиться файл:

```text
first.pdf
```

Откройте `first.pdf` и убедитесь, что в нём отображается текст.

## Задание 2. Проверить структуру LaTeX-документа

Замените содержимое `first.tex` на:

```latex
%% Document class and document options
\documentclass[a4paper,12pt]{article}

%% Package for font encoding
\usepackage[T1]{fontenc}

%% Everything above begin{document} is the preamble

\begin{document}

%% Everything here is the document body

This is a simple document\footnote{with a footnote}.

This is a new paragraph.

\end{document}
```

Скомпилируйте:

```bash
pdflatex first.tex
```

Проверьте:

- строки, начинающиеся с `%`, не появляются в PDF;
- текст между `\begin{document}` и `\end{document}` появляется в PDF;
- `\footnote{...}` создаёт сноску;
- пустая строка между предложениями создаёт новый абзац.

## Задание 3. Проверить работу комментариев

Добавьте в тело документа:

```latex
This text will be visible.

% This text is a comment and must not be visible.

This text will also be visible.
```

Скомпилируйте документ.

Убедитесь, что строка:

```text
This text is a comment and must not be visible.
```

в PDF отсутствует.

## Задание 4. Проверить работу абзацев

Добавьте:

```latex
This is the first paragraph.

This is the second paragraph.

This is the third paragraph.
```

Скомпилируйте документ.

В PDF должны получиться три отдельных абзаца.

## Задание 5. Проверить работу обычных пробелов

Добавьте:

```latex
Word1 Word2

Word1     Word2

Word1          Word2
```

Скомпилируйте документ.

Проверьте, что несколько обычных пробелов в исходном `.tex`-файле не создают несколько пробелов в PDF.

## Задание 6. Проверить неразрывный пробел `~`

Добавьте:

```latex
Section 1

Section~1
```

Скомпилируйте документ.

`~` используется там, где два элемента не должны переноситься на разные строки. Например:

```latex
Figure~1
Table~2
Section~3
Equation~4
```

## Задание 7. Запустить LaTeX двумя способами

Выполните:

```bash
pdflatex first
```

Затем:

```bash
pdflatex first.tex
```

Обе команды должны компилировать один и тот же файл.

## Задание 8. Проверить специальные символы LaTeX

Вставьте в тело документа:

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

Скомпилируйте документ.

В PDF должны быть видны символы:

```text
{ } $ % & # _ \ ^ ~
```

---

# Лабораторная работа №3 — Набор математики

## Задание 1. Сравнить inline math и display math

Создайте LaTeX-документ и вставьте:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}

\begin{document}

Inline formula: $y = mx + c$.

Display formula:

\[
y = mx + c
\]

\end{document}
```

Скомпилируйте его.

Проверьте разницу:

- `$ ... $` помещает формулу внутрь строки;
- `\[ ... \]` помещает формулу отдельно и центрирует её.

Теперь возьмите формулу:

```latex
$5^{2}=3^{2}+4^{2}$
```

и замените её на:

```latex
\[
5^{2}=3^{2}+4^{2}
\]
```

Снова скомпилируйте и сравните результат.

## Задание 2. Добавить греческие буквы

Добавьте:

```latex
\[
\alpha \quad
\beta \quad
\gamma \quad
\delta \quad
\theta \quad
\lambda \quad
\pi \quad
\sigma \quad
\omega
\]
```

Добавьте прописные греческие буквы:

```latex
\[
\Gamma \quad
\Delta \quad
\Theta \quad
\Lambda \quad
\Pi \quad
\Sigma \quad
\Omega
\]
```

Скомпилируйте документ и проверьте результат.

## Задание 3. Проверить верхние и нижние индексы

Добавьте:

```latex
\[
a^{2}
\]

\[
a_{1}
\]

\[
x_{i}^{2}
\]

\[
x_{n+1}^{k+2}
\]
```

Проверьте, как работают `^` и `_`.

## Задание 4. Проверить математические команды

Добавьте:

```latex
\[
y = 2\sin\theta^{2}
\]
```

Также:

```latex
\[
\log \alpha + \log \beta = \log(\alpha\beta)
\]
```

## Задание 5. Создать интеграл

Добавьте:

```latex
\[
\int_{-\infty}^{+\infty} e^{-x^2} \, dx
\]
```

Проверьте:

- нижний предел `-\infty`;
- верхний предел `+\infty`;
- степень `-x^2`;
- небольшой пробел перед `dx`, создаваемый `\,`.

## Задание 6. Создать нумерованное уравнение

Добавьте:

```latex
\begin{equation}
\int_{-\infty}^{+\infty} e^{-x^2} \, dx
\end{equation}
```

Скомпилируйте документ.

У уравнения должен появиться номер.

## Задание 7. Проверить `amsmath` и `align`

В преамбулу добавьте:

```latex
\usepackage{amsmath}
```

В тело документа:

```latex
\begin{align*}
Q_{n,0} &= 1 \quad Q_{0,k} = [k=0]; \\
Q_{n,k} &= Q_{n-1,k}+Q_{n-1,k-1}+\binom{n}{k},
\quad\text{for $n$, $k>0$.}
\end{align*}
```

Проверьте, что строки выравниваются по символу `&`.

## Задание 8. Создать матрицы

Добавьте:

```latex
\[
\begin{matrix}
a & b & c \\
d & e & f
\end{matrix}
\quad
\begin{pmatrix}
a & b & c \\
d & e & f
\end{pmatrix}
\quad
\begin{bmatrix}
a & b & c \\
d & e & f
\end{bmatrix}
\]
```

Скомпилируйте и сравните три варианта матриц.

## Задание 9. Проверить математические шрифты

В преамбулу добавьте:

```latex
\usepackage{amsfonts}
```

В документ добавьте:

```latex
\[
\mathrm{ABC}
\]

\[
\mathit{ABC}
\]

\[
\mathbf{ABC}
\]

\[
\mathsf{ABC}
\]

\[
\mathtt{ABC}
\]

\[
\mathbb{ABC}
\]
```

Скомпилируйте и сравните результат.

## Задание 10. Проверить вложение команд шрифтов

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

Скомпилируйте и сравните результат.

## Задание 11. Проверить `fleqn`

Создайте отдельный вариант документа:

```latex
\documentclass[fleqn]{article}
\usepackage[T1]{fontenc}

\begin{document}

\[
y = mx + c
\]

\[
x^2 + y^2 = z^2
\]

\end{document}
```

Скомпилируйте.

Формулы должны располагаться слева, а не по центру.

## Задание 12. Проверить `leqno`

Используйте:

```latex
\documentclass[leqno]{article}
\usepackage[T1]{fontenc}

\begin{document}

\begin{equation}
x^2 + y^2 = z^2
\end{equation}

\end{document}
```

Скомпилируйте.

Номер уравнения должен находиться слева.

---

# Лабораторная работа №4 — Вставка графики

## Задание 1. Вставить собственное изображение

Поместите изображение в каталог с `.tex`-файлом, например:

```text
my-image.png
```

Создайте:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{graphicx}

\begin{document}

\begin{center}
\includegraphics[width=0.5\textwidth]{my-image.png}
\end{center}

\end{document}
```

Замените `my-image.png` на имя своего файла.

## Задание 2. Проверить `height`

Используйте:

```latex
\includegraphics[height=3cm]{my-image.png}
```

Скомпилируйте.

## Задание 3. Проверить `width`

Используйте:

```latex
\includegraphics[width=0.5\textwidth]{my-image.png}
```

Затем:

```latex
\includegraphics[width=0.8\textwidth]{my-image.png}
```

Сравните размер изображения.

## Задание 4. Проверить `angle`

Используйте:

```latex
\includegraphics[width=0.4\textwidth,angle=30]{my-image.png}
```

Затем попробуйте:

```latex
\includegraphics[width=0.4\textwidth,angle=90]{my-image.png}
```

## Задание 5. Проверить `scale`

Используйте:

```latex
\includegraphics[scale=0.5]{my-image.png}
```

Затем:

```latex
\includegraphics[scale=1.0]{my-image.png}
```

Сравните результат.

## Задание 6. Сравнить `\textwidth` и `\linewidth`

Создайте документ:

```latex
\documentclass[twocolumn]{article}
\usepackage[T1]{fontenc}
\usepackage{graphicx}

\begin{document}

Image relative to textwidth:

\includegraphics[width=0.5\textwidth]{my-image.png}

Image relative to linewidth:

\includegraphics[width=0.5\linewidth]{my-image.png}

\end{document}
```

Скомпилируйте.

После этого замените:

```latex
\documentclass[twocolumn]{article}
```

на:

```latex
\documentclass{article}
```

Снова скомпилируйте и сравните размеры.

## Задание 7. Проверить плавающие объекты

В преамбулу добавьте:

```latex
\usepackage{graphicx}
\usepackage{lipsum}
```

В тело документа:

```latex
\lipsum[1-4]

Test location.

\begin{figure}[ht]
\centering
\includegraphics[width=0.5\textwidth]{my-image.png}
\caption{My image}
\end{figure}

\lipsum[5-10]
```

Скомпилируйте документ и посмотрите, где LaTeX разместит рисунок.

## Задание 8. Проверить `h`, `t`, `b`, `p`

По очереди используйте:

```latex
\begin{figure}[h]
```

```latex
\begin{figure}[t]
```

```latex
\begin{figure}[b]
```

```latex
\begin{figure}[p]
```

Каждый вариант скомпилируйте отдельно и сравните расположение рисунка.

## Задание 9. Проверить работу `\label` и `\ref`

Создайте:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}

\begin{document}

See section~\ref{sec:first}.

See subsection~\ref{subsec:first}.

See item~\ref{item:first}.

\section{First section}
\label{sec:first}

\subsection{First subsection}
\label{subsec:first}

\begin{enumerate}
\item First item
\label{item:first}

\item Second item
\end{enumerate}

\end{document}
```

Выполните:

```bash
pdflatex first.tex
```

Посмотрите PDF.

Затем выполните команду второй раз:

```bash
pdflatex first.tex
```

Сравните результат.

## Задание 10. Проверить положение `\label` относительно `\caption`

Сначала используйте неправильный вариант:

```latex
\begin{figure}[ht]
\centering
\includegraphics[width=0.4\textwidth]{my-image.png}
\label{fig:test}
\caption{Test image}
\end{figure}

Figure~\ref{fig:test}.
```

Скомпилируйте документ два раза и посмотрите номер ссылки.

Затем измените на:

```latex
\begin{figure}[ht]
\centering
\includegraphics[width=0.4\textwidth]{my-image.png}
\caption{Test image}
\label{fig:test}
\end{figure}

Figure~\ref{fig:test}.
```

Снова скомпилируйте два раза и сравните результат.

## Задание 11. Проверить `\label` после `equation`

Сначала используйте:

```latex
\begin{equation}
e^{i\pi}+1=0
\end{equation}
\label{eq:test}

Equation~\ref{eq:test}.
```

Скомпилируйте два раза.

После этого используйте правильное расположение:

```latex
\begin{equation}
e^{i\pi}+1=0
\label{eq:test}
\end{equation}

Equation~\ref{eq:test}.
```

Скомпилируйте два раза и сравните результат.

---

# Лабораторная работа №5 — Таблицы

## Задание 1. Создать простую таблицу

Создайте файл с содержимым:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{array}

\begin{document}

\begin{tabular}{lll}
Animal & Food & Size \\
dog & meat & medium \\
horse & hay & large \\
frog & flies & small \\
\end{tabular}

\end{document}
```

Скомпилируйте.

## Задание 2. Проверить выравнивание `l`

Используйте:

```latex
\begin{tabular}{lll}
Animal & Food & Size \\
dog & meat & medium \\
horse & hay & large \\
frog & flies & small \\
\end{tabular}
```

Все три столбца должны быть выровнены влево.

## Задание 3. Проверить выравнивание `c`

Используйте:

```latex
\begin{tabular}{ccc}
Animal & Food & Size \\
dog & meat & medium \\
horse & hay & large \\
frog & flies & small \\
\end{tabular}
```

Скомпилируйте.

## Задание 4. Проверить выравнивание `r`

Используйте:

```latex
\begin{tabular}{rrr}
Animal & Food & Size \\
dog & meat & medium \\
horse & hay & large \\
frog & flies & small \\
\end{tabular}
```

Скомпилируйте.

## Задание 5. Сделать строку со слишком малым количеством элементов

Используйте:

```latex
\begin{tabular}{lll}
Animal & Food & Size \\
dog & meat \\
horse & hay & large \\
\end{tabular}
```

Скомпилируйте и посмотрите результат.

## Задание 6. Сделать строку со слишком большим количеством элементов

Используйте:

```latex
\begin{tabular}{lll}
Animal & Food & Size \\
dog & meat & medium \\
horse & hay & large & extra \\
frog & flies & small \\
\end{tabular}
```

Попробуйте скомпилировать и посмотрите сообщение LaTeX.

## Задание 7. Использовать `\multicolumn`

Используйте пример:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{array}
\usepackage{booktabs}

\begin{document}

\begin{tabular}{lll}
\toprule
Animal & Food & Size \\
\midrule
dog & meat & medium \\
horse & hay & large \\
frog & flies & small \\
fuath & \multicolumn{2}{c}{unknown} \\
\bottomrule
\end{tabular}

\end{document}
```

Здесь:

```latex
\multicolumn{2}{c}{unknown}
```

означает:

- объединить 2 столбца;
- выровнять содержимое по центру;
- вывести текст `unknown`.

---

# Лабораторная работа №6 — Библиография

## Задание 1. Создать библиографическую базу

Создайте файл:

```text
learnlatex.bib
```

Добавьте:

```bibtex
@article{Thomas2008,
  author = {Thomas, Christine M. and Liu, Tianbiao and Hall, Michael B. and Darensbourg, Marcetta Y.},
  title = {Series of Mixed Valent {Fe(II)Fe(I)} Complexes},
  journal = {Inorg. Chem.},
  year = {2008},
  volume = {47},
  number = {15},
  pages = {7009-7024},
  doi = {10.1021/ic800654a}
}

@book{Graham1995,
  author = {Ronald L. Graham and Donald E. Knuth and Oren Patashnik},
  title = {Concrete Mathematics},
  publisher = {Addison-Wesley},
  year = {1995}
}
```

## Задание 2. Проверить `natbib`

Создайте:

```text
natbib-example.tex
```

Вставьте:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{natbib}

\begin{document}

The mathematics showcase is from \citet{Graham1995}.

Some parenthetical citation: \citep{Graham1995}.

Chemistry example: \citep{Thomas2008}.

Together: \citep{Graham1995,Thomas2008}.

\bibliographystyle{plainnat}
\bibliography{learnlatex}

\end{document}
```

## Задание 3. Скомпилировать вариант `natbib`

Выполните строго по порядку:

```bash
pdflatex natbib-example.tex
bibtex natbib-example
pdflatex natbib-example.tex
pdflatex natbib-example.tex
```

Откройте `natbib-example.pdf`.

Проверьте:

- ссылки на источники появились в тексте;
- в конце появился список литературы.

## Задание 4. Проверить `biblatex`

Создайте:

```text
biblatex-example.tex
```

Вставьте:

```latex
\documentclass{article}
\usepackage[T1]{fontenc}

\usepackage[style=authoryear]{biblatex}
\addbibresource{learnlatex.bib}

\begin{document}

The mathematics showcase is from \autocite{Graham1995}.

Another citation: \parencite{Graham1995}.

Text citation: \textcite{Thomas2008}.

Together: \autocite{Thomas2008,Graham1995}.

\printbibliography

\end{document}
```

## Задание 5. Скомпилировать вариант `biblatex`

Выполните:

```bash
pdflatex biblatex-example.tex
biber biblatex-example
pdflatex biblatex-example.tex
```

Откройте получившийся PDF.

## Задание 6. Создать новую запись в `.bib`

Добавьте в `learnlatex.bib` тестовую запись:

```bibtex
@book{TestBook2026,
  author = {Ivan Ivanov},
  title = {Test Book},
  publisher = {Test Publisher},
  year = {2026}
}
```

## Задание 7. Добавить цитирование новой записи

Для `natbib` добавьте:

```latex
New source: \citep{TestBook2026}.
```

Для `biblatex`:

```latex
New source: \autocite{TestBook2026}.
```

Заново выполните соответствующую последовательность компиляции.

Проверьте, что новая книга появилась в списке литературы.

## Задание 8. Добавить ссылку на источник, которого нет в базе

Добавьте:

```latex
\citep{MissingSource}
```

или для `biblatex`:

```latex
\autocite{MissingSource}
```

При этом не добавляйте запись `MissingSource` в `learnlatex.bib`.

Скомпилируйте документ и посмотрите:

- как отображается такая ссылка;
- какое предупреждение выдаёт LaTeX/BibTeX/Biber.

## Задание 9. Проверить числовой стиль `natbib`

Замените:

```latex
\usepackage{natbib}
```

на:

```latex
\usepackage[numbers]{natbib}
```

Снова выполните:

```bash
pdflatex natbib-example.tex
bibtex natbib-example
pdflatex natbib-example.tex
pdflatex natbib-example.tex
```

Посмотрите, как изменились ссылки.

## Задание 10. Проверить `style=numeric` в `biblatex`

Замените:

```latex
\usepackage[style=authoryear]{biblatex}
```

на:

```latex
\usepackage[style=numeric]{biblatex}
```

Выполните:

```bash
pdflatex biblatex-example.tex
biber biblatex-example
pdflatex biblatex-example.tex
```

Сравните результат с `style=authoryear`.

---

# Лабораторная работа №7 — Презентации LaTeX

## Задание 1. Создать минимальную презентацию Beamer

Создайте:

```text
presentation.tex
```

Вставьте:

```latex
\documentclass{beamer}

\usetheme{Copenhagen}

\author{Your Name}
\title{Practical Scientific Writing}

\begin{document}

\end{document}
```

Скомпилируйте.

## Задание 2. Создать титульный слайд

Между `\begin{document}` и `\end{document}` добавьте:

```latex
\begin{frame}
\titlepage
\end{frame}
```

## Задание 3. Добавить обычные слайды

Добавьте:

```latex
\begin{frame}{Article}
Some text about the article.
\end{frame}

\begin{frame}{Mathematics}
A helpful slide about mathematics.
\end{frame}
```

Скомпилируйте.

## Задание 4. Добавить блоки

Добавьте:

```latex
\begin{frame}{Article}

\begin{block}{Example}
This is an example of a block.
\end{block}

\begin{block}{Euclid's theorem}
This is a theorem.
\end{block}

\end{frame}
```

## Задание 5. Добавить маркированный список

Добавьте:

```latex
\begin{frame}{Itemize}

\begin{itemize}
\item First element
\item Second element
\item Third element
\end{itemize}

\end{frame}
```

## Задание 6. Добавить нумерованный список

Добавьте:

```latex
\begin{frame}{Enumerate}

\begin{enumerate}
\item First element
\item Second element
\item Third element
\end{enumerate}

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

## Задание 8. Использовать `\pause` в списке

Добавьте:

```latex
\begin{frame}{Step-by-step list}

\begin{enumerate}

\item First element

\pause

\item Second element

\pause

\item Third element

\end{enumerate}

\end{frame}
```

## Задание 9. Использовать `\uncover`

Добавьте:

```latex
\begin{frame}{Sets}

A \alert{set} is a collection of objects.

\uncover<2->{
For example:
\[
Z=\{\text{cow},\text{pig},\text{elephant}\}.
\]
}

\uncover<3->{
We call the objects in $Z$ the elements of $Z$.
}

\uncover<4->{
\[
\text{cow} \in Z
\]
}

\end{frame}
```

Проверьте последовательное появление элементов.

## Задание 10. Создать колонки

Добавьте:

```latex
\begin{frame}{Columns}

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

## Задание 11. Изменить тему оформления

Сначала используйте:

```latex
\usetheme{Copenhagen}
```

Затем замените на:

```latex
\usetheme{Warsaw}
\usecolortheme{beaver}
```

Скомпилируйте снова и сравните оформление.

## Задание 12. Проверить `a0poster`

Создайте:

```text
poster-a0.tex
```

Используйте:

```latex
\documentclass[a0,portrait]{a0poster}

\usepackage{multicol}

\columnsep=100pt

\begin{document}

\begin{minipage}{.7\textwidth}
\VeryHuge My Scientific Poster \\[0.75cm]
\Large Your Name \\
\Large RUDN University
\end{minipage}

\begin{multicols}{2}

\section*{Introduction}
Some introduction text.

\section*{Results}
Some results.

\end{multicols}

\end{document}
```

## Задание 13. Проверить `beamerposter`

Создайте:

```text
poster-beamer.tex
```

Используйте:

```latex
\documentclass[xcolor={svgnames}]{beamer}

\usetheme{Copenhagen}

\usepackage[
  orientation=portrait,
  size=a0,
  scale=1.4
]{beamerposter}

\title{My Scientific Poster}
\author{Your Name}
\institute{RUDN University}

\begin{document}

\begin{frame}

\begin{columns}

\begin{column}{.5\textwidth}
First column.
\end{column}

\begin{column}{.5\textwidth}
Second column.
\end{column}

\end{columns}

\end{frame}

\end{document}
```

## Задание 14. Проверить `tikzposter`

Создайте:

```text
poster-tikz.tex
```

Используйте:

```latex
\documentclass[24pt,a0paper,portrait]{tikzposter}

\title{My Scientific Poster}
\author{Your Name}
\institute{RUDN University}

\begin{document}

\maketitle

\begin{columns}

\column{.5}

\block{Introduction}{
Introduction text.
}

\column{.5}

\block{Results}{
Results text.
}

\end{columns}

\end{document}
```

Скомпилируйте и сравните три подхода к созданию постеров.

---

# Лабораторная работа №8 — TikZ: диаграммы и чертежи как код

## Задание 1. Построить граф в TikZ

Создайте:

```text
graph.tex
```

Базовая структура:

```latex
\documentclass[border=1cm]{standalone}

\usepackage{tikz}

\begin{document}

\begin{tikzpicture}

% graph here

\end{tikzpicture}

\end{document}
```

Чтобы выполнить требование с расположением узлов по окружности, можно начать с такого варианта:

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

\draw (A) -- node[above]{1} (B);
\draw[dashed] (B) -- node[above]{2} (C);
\draw[->] (C) -- node[above]{3} (D);
\draw[dotted] (D) -- node[below]{4} (E);
\draw[<->] (E) -- node[below]{5} (F);
\draw[thick] (F) -- node[below]{6} (A);

\draw[bend left] (A) to node{2} (D);
\draw[bend right] (B) to node{3} (E);

\end{tikzpicture}

\end{document}
```

Граф не обязан полностью совпадать с образцом; главное — получить граф с похожими свойствами.

## Задание 2. Построить графики `y=e^x` и `y=ln(x)`

Создайте:

```text
plot.tex
```

Используйте:

```latex
\documentclass[border=1cm]{standalone}

\usepackage{tikz}

\begin{document}

\begin{tikzpicture}[scale=1.2]

% Axes
\draw[->] (-3,0) -- (3,0) node[right] {$x$};
\draw[->] (0,-3) -- (0,3) node[above] {$y$};

% Origin
\node[below left] at (0,0) {$O$};

% Marks x=1 and y=1
\draw (1,0.08) -- (1,-0.08)
      node[below] {$1$};

\draw (0.08,1) -- (-0.08,1)
      node[left] {$1$};

% y = e^x
\draw[
  domain=-2.5:1,
  samples=100,
  smooth
]
plot (\x,{exp(\x)})
node[right] {$y=e^x$};

% y = ln(x)
\draw[
  domain=0.08:3,
  samples=100,
  smooth
]
plot (\x,{ln(\x)})
node[right] {$y=\ln(x)$};

\end{tikzpicture}

\end{document}
```

Скомпилируйте:

```bash
pdflatex plot.tex
```

Проверьте наличие:

- оси `x`;
- оси `y`;
- точки отсчёта `O`;
- отметки `1` на обеих осях;
- графика `y=e^x`;
- графика `y=ln(x)`.

## Задание 3. Переделать треугольник Серпинского в ковёр Серпинского

Создайте:

```text
sierpinski-carpet.tex
```

Начните с:

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

Алгоритм, который нужно реализовать:

1. Нарисовать квадрат.
2. Разделить его мысленно на сетку `3 × 3`.
3. Центральный квадрат не рисовать.
4. Для остальных восьми квадратов повторить тот же процесс.
5. Добавить параметр глубины рекурсии.
6. Получить несколько итераций, например:
   - итерация 0;
   - итерация 1;
   - итерация 2;
   - итерация 3.

Рекурсивная функция должна выполнять восемь рекурсивных вызовов — для всех частей сетки, кроме центральной.

Полный готовый код ковра здесь специально не приведён, потому что адаптация рекурсивного кода треугольника Серпинского под ковёр Серпинского и является самим заданием лабораторной работы.
