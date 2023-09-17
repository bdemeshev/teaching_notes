# teaching_notes

* Есть одна довольно известная задача по комбинаторике. 
Садовник за три дня должен посадить семь одинаковых деревьев. 
Сколькими способами он может это сделать?

Классический способ решения — рассмотреть деревья и разделители дней: :tree: :tree: | :tree: :tree: :tree: :tree: | :tree:.
И отсюда видно, что ответ — это биномиальный коэффициент, $C_9^2$.

Трудность в том, что люди не очень хорошо воспринимают равнозначность знаков | и :tree:. 

Для решения трудности можно выбрать более осмысленный значок для перегородки, например, :moon:. 
Та же последовательность теперь вглядит так: :tree: :tree: :moon: :tree: :tree: :tree: :tree: :moon: :tree:, и увидеть биномиальный коэффициент гораздо проще. 

Более того, теперь значки соответствуют действиям. Посадил дерево, посадил дерево, поспал, ... И мы из девяти действий выбираем два сна.

#combinatorics

* Когда определяют несмещённые оценки обычно вводят понятия истинного значения параметра, $a$ и смещения, $bias(\hat a) = E(\hat a) - a$. 

Разумно сначала повторить, что $\hat a$ — это случайный величина и рассмотрить несколько её независимых копий, $\hat a_1$, $\hat a_2$, ..., $\hat a_T$.
Здесь $T$ — сколько дней или раз мы проводили эксперимент, а $n$ — число наблюдений, используемое в каждом эксперименте.
Повторяя эксперимент, мы получаем новую выборку, а значит очередное значение оценки $\hat a_k$, то есть новую точку на числовой оси.
У этих случайных точек есть "центр кучкования", точка $E(\hat a)$. 

Определив "центр кучкования", можно определить смещение словами, смещение оценки — это разница между центром кучкования копий оценки и истинным значением параметра.
Словесное описание формулы может облегчить понимание. 

#statistics

* Для школьников идея переноса слагаемого из одной части уравнения в другую воспринимается тяжелее,
чем идея прибавления или вычитания константы из обеих частей.
На примере уравнения $2x + 15 = 3x - 7$.
Для начинающего школьника идея «вычтем 15 из обеих частей уравнения» звучит проще, чем «перенесём 15 из левой части в правую».
Обычно любопытный начинающий сразу спросит, «А почему меняется знак?».
А с прибавлением или вычитанием константы всё сразу и так ясно: одно и то же действие делаем с одним и тем же числом.

#algebra

* Не моё, но люблю. Кажется, идея Александра Шеня.
Преподавание любой дисциплины — это не строительство дома, кирпич за кирпичом.
Преподавание больше похоже на бросание камней в бурный поток, чтобы построить дамбу.
Часть камней смывает, часть падают не той стороной, но если разумно их кидать, то получим добротную дамбу.

#teaching


* В курсах часто говорят, что незавимость — это более сильное требование, чем некоррелированность.
Но при этом пропускают в рассказе промежуточные стадии и не говорят, как сформулировать независимость используя понятие корреляции.

Итак, независимость величин $X$ и $Y$ — это некоррелированость любой функции от $X$ и любой функции от $Y$.
Сразу ведь видно, что это более сильное условие, чем некоррелированость $X$ и $Y$?

И промежуточные стадии! Из независимости $X$ и $Y$ следует два факта-близнеца.
Условное ожидание $Y$ при известном $X$ не зависит от $X$, то есть, $E(Y|X) = E(Y)$.
И близнец, условное ожидание $X$ при известном $Y$ не зависит от $Y$, то есть, $E(X|Y) = E(X)$.

Оба этих факта-близнеца также можно сформулировать в терминах некоррелированности.
Например, условие $E(Y|X) = E(Y)$ равносильно тому, что величина $Y$ и любая функция от $X$ некоррелированны.

В этой цепочке можно строить разные контр-примеры.
Например, придумайте зависимую пару $X$ и $Y$ такую, что $E(Y|X)=E(Y)$ и $E(X|Y) = E(X)$.
Или, придумайте некоррелированную пару $X$ и $Y$ такую, что $E(Y|X) \neq E(Y)$ и $E(X|Y) \neq E(X)$.

Педанты могут заменить слова «любая функция» на «измеримая функция»,
а вместо нулевой корреляции говорить о нулевой ковариации,
чтобы не исключать случайные величины — константы.

#probability

* Когда и как впервые ввести понятие сигма-алгебры?

Насколько мне известно, есть две традиции.
Первая — вообще не вводить сигма-алгебры.
Так часто поступают в курсах теории вероятностей для нематематиков.

Вторая — сначала дать аксиоматику событий и сигма-алгебр, затем ввести случайные величины.

При наличии времени мне кажется разумной третья стратегия.

Поначалу пропустить сигма-алгебры и определить случайные величины как произвольные функции множества исходов.
А затем определить сигма-алгебру, порождаемую случайной величиной или набором случайных величин.
Именно так, начать с частного случая сигма-алгебры.
Очень классно здесь то, что на простой двумерной табличке пары случайных величин
можно попросить студентов вычислить кучу разных сигма-алгебр $\sigma(X)$, $\sigma(X, Y)$, $\sigma(X - Y)$ и т.д.
В конце концов, все сигма-алгебры порождаются неким наобором случайных величин.
Дальше можно говорить об измеримости случайной величины относительно сигма-алгебры и об условном ожидании относительно сигма-алгебры.
Далее студенты могут сами выдвинуть список свойств, которым должна удовлетворять сигма-алгебра.
В классическом подходе этот список свойств возникает с потолка.

И дальше, да и то не во всех курсах, можно сказать, что сигма-алгебры нужны и в основании и закрыть логический пропуск начала курса.

#probability

* Не надо рассказывать про циклы, условия и типы в начале вводного курса по анализу данных.
В начале лучше рассказать про манипуляции с табличками данных и графический анализ.
А когда потребуется цикл — тогда его и рассказать. Не раньше.
Иначе мы получаем `for` в студенческих работах для того, чтобы взять логарифм от столбца данных.

#programming

* Мета-теорема. Любую теорему или определение с двойным индексом можно переписать проще и понятнее без двойного индекса.
Кажется, автор идеи — Дональд Кнут. А может и фольклорная.
Например, классическое определение, набор событий $\{A_1, A_2, ... \}$ называется взаимно независимым,
если для любого $k$ и любой последовательности индексов $i_1 < i_2 < ... < i_k$ (в аудитории уже куча пустых взглядов, а мы ещё не закончили)
выполнено равенство

$$
P(A_{i_1} \cap \ldots \cap A_{i_k}) = \prod_{j=1}^k P(A_{i_j}).
$$

А вот альтернативная, почему-то почти неизвестная в России, формулировка:

Набор событий является взаимно независимым, если любое событие из набора независимо от пересечения любого количества остальных событий из набора.

#probability

#meta-theorem

* Потрясающий пример задачи на классификацию — игра «Свечка — не свечка».

Главное — это внимательно слушать! Ты внимательно слушаешь?

#machine-learning

* Никогда не понимал, почему для свободных неизвестных в линейной алгебре вводят новые буквы, а не сохраняют имеющиеся.

Например, типичный ответ с бесконечным множеством решений в учебнике выглядит так:

$$
\begin{cases}
x = a, a \in \mathbb{R}, \\
y = b, b \in \mathbb{R}, \\
z = 2a - 3b.
\end{cases}
$$

А что мешает обойтись без $a$ и $b$?

$$
\begin{cases}
x \in \mathbb{R}, \\
y \in \mathbb{R}, \\
z = 2x - 3y.
\end{cases}
$$

#linear-algebra


