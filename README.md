Создание соревнований с нуля на платформе Яндекс.Контест

1.	Первые шаги
2.	Начало настройки задачи
a.	«Общее»
b.	Поле ответ
c.	Тесты и решения
d.	Настройки чекеров
e.	Условия
f.	Загруженные файлы
3.	Работа с набором задач
4.	Переход к соревнованию
a.	Настройки монитора
5.	Итог
6.	Дополнительно
a.	Паттерн ответа
Первые шаги
Соревнование с системе Яндекс.Контест – это набор задач и набор настроек.
Краткий алгоритм создания соревнования: 
•	в соревнование добавляется набор задач; 
•	в набор задач добавляются задачи; 
•	для соревнования устанавливаются общие и индивидуальные настройки.
 

Начнем с задач:
1.	Сформулируем задачу: Сколько будет A + B = ?, если А = 2 и В = 2.
2.	Перейдем по ссылки https://admin.contest.yandex.ru/problems (попадем на страницу, где отображаются все задачи, к которым вы имеете доступ). С главной страницы администратора можно попасть следующим образом:  
3.	На этой странице мы можем создать новую задачу или загрузить уже созданную:

 
Соответственно, мы выбираем «Создать задачу»;
4.	Вводим название задачи и нажимаем кнопку «Создать».

Настройки задачи

После чего нас перекинет на страницу параметров нашей новой задачи. 
Пройдемся по подразделам, которые требуется настроить.

«Общее»
В этом подразделе изменяется название задачи и тип задачи. От типа задачи будет много завесить.
 

ОБНОВИТЬ СКРИН ПОСЛЕ ДОБАВЛЕНИЯ ЗАДАЧИ НА СООТВЕСТВИЕ
 

Описание типов задач:
problem-with-checker – тип задачи по программированию с использованием своего чекера;

test-problem – тип задач в виде теста, где можно выбрать 1 или несколько правильных ответов;

text-answer-problem – тип задач, где ответом является слово, словосочетание, число и т.п.;

interactive-problem – не используем;

problem-with-match-sets– тип задач, который используем для создания задач на соответствие.

Соответственно, отталкиваясь от задачи, которую вам дали, вы определяете «Тип задачи».

«Поле ответа» 

Устанавливаем способ подачи ответа «Изменить тип»

Для задач на программирования используем тип problem-with-checker. Участник может отправить файл(код) на проверку или написать ответ (код) в окне:


 



Для задач типа test-problem можно выбрать два варианта подачи ответов:
 
 
                                                            		#Добавить вариант ответа


Для задач типа text-answer-problem возможны способа занесения ответа:
•	Текст и файл
•	Однострочный ответ
•	Текст
•	Файл

Для «Однострочного ответа» можно установить ограничения на количество вводимых участником символов, ограничение на ввод только числа, только буквы и т.д. Сделать это можно, установив нужный «Паттерн ответа»:
 





Как видит участник эти настройки
 
Последний тип задачи problem-with-match-sets используется для создания заданий на сопоставление. Здесь выбираем только один тип ответа «Сопоставление». Обратите внимание, что первый набор отвечает за кол-во колонок, а второй набор за кол-во строк.
#добавить колонку

 
#добавить строку
Правильные соотношения выставляются метками «точками»
Внимание! В строке может быть только один правильный ответ. 
В столбце лучше тоже не проставлять больше 1 правильного варианта!
#Так увидит участник эту задачу 
 
«Тесты и решения»	
 
Раздел, в котором необходимо указать тесты и их кол-во.
В задачах test-problem, text-answer-problem, problem-with-custom-config задействуется только один тест. (этот раздел можно не трогать)
В задачах на программирование (problem-with-checker) используется больше тестов.
Рассмотрим добавление тестов для программирования (во всех остальных задачах делаем точно также, но добавляем один тест)

Вверху справа добавляем тест
 



 
В название тестового файла: 0 – идентифицирует наш тест, цифра 4, 5, 6 и тд. определяет номер теста. В 04 – записываем данные для проверки, в файл c окончанием *.a записывается ответ!
Результат обновляем в самом низу страницы.


БЫЛО:
 
СТАЛО: 
 

Определим Sample, нажав на «Добавить сэмплы»:
 
Суть sample тестов, чтобы участник ориентировался на пример. Сэмпл – тест участник видит, а Остальные тесты участник не видит.
#Так увидит их на странице участник
 
Также, наборы тестов выходных и входных данных можно посмотреть и исправить в разделе «Загруженные файлы»

«Настройки чекера»
Чекер – это программа в системе Яндекс.Контест, которая сверяет ответ участника с эталонным ответом и возвращает в систему вердикт ответа (верно/не верно/ошибка). В этом сезоне будем использовать только чекеры ejudge-exitcode-checher. (Кто знаком с системой может пользоваться другими типами)
 



1.	ejudge-exitcode-checher (БУДЕМ ИСПОЛЬЗОВАТЬ ВСЕГДА ЕГО) – тип чекера используется, если чекер формата .py
o	часто используемый чекер такого типа, это checkreg.py . Его используем, когда в разделе «поле ответа» используем регулярное выражение. Также есть чекер checkok.py , который всегда возвращает вердикт «ОК».
Если чекер возвращает не вердикт, а количество баллов, то нужно использовать кнопку «Чекер выставляет баллы» (остальные параметры трогать не нужно)

o	Есть чекер checker1000.py, который проверяет количество символов в ответе, например, в развернутом ответе (сочинение и т.п.), ограничиваем участника по символам.
 
o	Например, такие чекеры могут использоваться в задачах «множественного выбора», «задачи на сопоставление»: 1 правильный ответ = +1 балл, неправильный -1
 
 
Чекер будет сразу проставлять баллы за ответ, если поставить «Да» в графе «Чекер выставляет баллы»

Также, Вам придется подгонять чекеры для своих задач, если не подходят стандартные, которые 
Вы сможете найти по ссылке https://yadi.sk/d/_hZs2FrTVNyYWg

«Условия»

В данном разделе вносятся условия и комментарии к задачам.
Выбираем «Тип условия» - TeX(для отображения условия используется язык tex) и добавим одно услувие. Также, есть редактор «Markdown + KaTeX»
 

Создается форма для «условия»


 
После редактирования условия нажмите на «Сохранить»
Если задача не на программирование, то достаточно оформить так (пример из старого интерфейса):

 
«Загруженные файлы»

Раздел, где отображается директория всех файлов, которые относятся к нашей задаче.
Например, можно исправить входных и выходные данных наших тестов:

 
Редактировать файлы через нажатие на «карандаш». В файлах 01, 02, 03,… записаны условия для тестов (для программирования), в файлах 01.а, 02.а, 03.а,… записываются ответы, с которыми будем сравнивать.
Работа с набором задач
1.	Чтобы добавить задачу в набор задач следует перейти в раздел «Управление наборами задач» или перейти по ссылки https://admin.contest.yandex.ru/problemsets
 
2.	Создаем новый набор задач
 
После этого попадем на страницу набора задач «Новый набор»
 
3.	Мы уже создали задачу, поэтому просто добавим существующую, нажав на «плюсик» и выберем из списка нашу задачу.

4. Вписываем название нашей задачи, чтобы найти её и нажимаем на «ID». 
 

#Можем выбрать нумерацию задач
#Номер задачи (число или буквы)
   		  
Набор задач создан.

Переход к соревнованию

После завершения настроек задач наш участник не сможет увидеть набор задач. Для этого нам нужно создать соревнование.
Перейдем во вкладку «Соревнования» или по ссылке https://admin.contest.yandex.ru/contests
 
Находим переход «Добавить соревнование» и выпадает модальное окно, где указываем название нашего соревнования. (+ создаст новый пустой набор задач «Новое соревнование»)
 
Попадаем на страницу настроек уже нашего соревнования. 
Настройки соревнования будут проводиться только
Далее выставляем настройки соревнований. Базовые настройки для соревнований «Я – профессионал» указаны на следующих скриншотах: 
 
#Время зависит от условия проведения соревнования
 
#На отборочном этапе используем 1 попытку для сдачи ответа, в демо-версиях – 3.  
#Участники должны видеть только свои задачи
 
#На демо-версии мы показываем «Вердикт», т.е. нужно выбрать «На всех посылках»
 
  
#На основные соревнования «Вердикт» скрываем, т.е. выбрать «Не показывать»  
 


«Настройки монитора»

Монитор – это способ оценивания задач, и ранжирование участников по набранным результатам.
Основная настройка – тип монитора, в олимпиаде «Я - профессионал» используется только scoring.
•	Монитор типа scoring – баллы за задачу определяют чекеры в самих задачах.





И самые последние настройки (обратите внимание на «Видимость монитора», обязательное поле!):
 

Done.

Итог
Если вы создали задачу и соревнование согласно всем предыдущим разделам инструкции, то страница для просмотра участника будет выглядеть следующим образом:
 
Дополнительно
«Паттерн ответа»
Паттерн ответа – позволяет ограничить участника при отправлении ответа. Мы его используем в разделе «Поле ответа». 
Эти ограничения мы задаем с помощью регулярных выражений.
Например,
^\d+$ - ограничение на ввод ответа только в виде одного числа
 
 
 
^[a-zA-Z]+$ - ограничение на ввод ответа на английском языке одного слова
 
 
 

Множество элементарных регулярных выражений можно найти на сайте https://regex101.com/ внизу справа!





















 
`# -Заголовки`

## Заголовок level 2

### Заголовок level 3

#### Заголовок level 4

***

Альтернативный синт. заголовка 1
===============

Альтернативный синтаксис заголовка 2
---------------

Разделители (три зведочки)

***

На разделы (три тире)

---

Текста (> 3 подчеркиваний)

______

# -Форматирование текста

**Жирный текст**

*Курсив*

***Курсив и жирный текст***

Разделение и создание параграфов обозначаются пустой строкой

Новый параграф Разделение и создание параграфов обозначаются пустой строкой
Переход на новую строку обозначается двумя или более пробелами, а после Enter.
Новая строка после двух или более пробелом и Enter. Или использовать `{br}` {br} Текст на след строке

# -Списки


**Нумерованный список**

1. First item
2. Second item
3. Third item
    
    1. Indented item
    2. Indented item

4. Fourth item


**Маркированный список**

- First item
- Second item
- Third item
    - Indented item
    - Indented item
- Fourth item

***

# -Математические формулы

**Строчная формула:**  
Пусть $\lambda \leq 1$

**Большая формула:**
$$\intop_0^1 x^2 dx = \frac{1}{3}$$

***

# -Добавление ссылок

[Текст ссылки](http://someURL.ru)

***





# -Вставка картинок

Размеры картинки можно регулировать параметрами **width** и **height** (если указать 1 параметр, то второй установится пропорционально). Например,

![alt](pic1.jpg){:style="width: 300px;"}










Для этого нужно загрузить картинку в корневую директорию задачи (раздел **Файлы**)








![alt](pic2.png){:style="width: 300px;"}

***















# -Таблицы

Первый столбец выравнивание по левому краю, второй - по центру, третий - по правому краю. Также, в таблице можно использовать математические формулы и форматирование текста. Ячейка в таблице обозначается двумя вертикальными слешами «|ячейка|»

| Тема | Примеры | Третий стобец |
| :- | :-: | -: |
| много текста, много текста, много текста, много текста, много текста, много текста, много текста, много текста,много текста, много текста, много текста, много текста,много текста, много  | много текста, много текста, много текста, много текста, много текста, много текста, много текста, много текста,много текста, много текста, много текста, много текста,много текста, много текста, много текста, много текста,много текста, много текста, много текста, много текста,много текста, много текста, много текста, много текста,  | много текста, много текста, много текста, много текста,много текста, много текста, много текста, много текста,много текста, много текста, много текста, много текста,много текста, много текста, много текста, много текста,много текста, много текста, много текста, много текста, |

***

# - Добавление текст программного кода

```
int n = 3;
for( int i = 0; i < n; i++ ) {
    printf( "number is %d", i );
}

code for I in list
```



