**Финальный проект (Telecom)**

**Цель:**

Решить задачу бинарной классификации для Телеком-компании, чтобы прогнозировать отток клиентов.
Если выяснится, что пользователь планирует уйти, компания предложит такому клиенту промокоды и специальные условия.


**Ход исследования и Инструменты:**  

- Исследовательский анализ данных. Вяснили какие факторы наболее всего влияют на принятие клиентом решения прекратить пользоваться услугами телеком-компании.
- Обучение разные моделей ML для прогноза оттока клиентов компании. Выбор модели лучшего качества
- На Этапе Предобработки данных
Соединили все данные в один Датасет.

Привели данные к нужным типам.

Проверили наличие Пропусков, Дубликатов

Провели Исследовательский анализ данных

Посмотрели корреляцию признаков

BeginDate, duration, TotalCharges, Partner, MonthlyCharges те признаки, которые наиболее взаимосвязаны с признаком leave (Ушел клиент или нет)

Изучили Количество новых контрактов в определенный период времени

Рост количества подписанных договоров наблюдается в 2014 году также В конце 2019 к началу 2020 гг.

Изучили Подолжительность Контракта, Ежемесячные платежи, Общая сумма расходов для Оставшихся и Ушедших клиентов.

Средняя продолжительность контракта у оставшихся клиентов - 893 дня

Средняя продолжительность контракта у ушедших клиентов - 924 дня

Средний ежемесячный платеж у ушедших клиентов (75.546004) выше, чем у оставшихся (62.763455)

Средний общий чек у ушедших клиентов (2371.377275) также выше чем у оставшихся (2067.943095)

Статистический тест позволяет утверждать, что с большой долей вероятности Средние ежемесячные платежи и Средний общий чек у оставшихся и ушедших клиентов разные

- На этапе Подготовки данных:

Random_state = 30723

Разделили данные на Обучающую и Тестовую выборки (Размер Тесовой выборки составил 25% от общей 1.7 тыс. строк)

Произвели Кодирование кат. признаков и Масштабирование.

Обучили модели и произвели Кроссвалидацию (GridSearchCV)

Признаки которые использовались для обучения моделей:
тип оплаты,

способ оплаты,

ежемесячные траты на услуги,

всего потрачено денег на услуг,

наличие иждивенцев,

наличие пенсионного статуса по возрасту,

наличие супруга(и),

наличие возможности ведения параллельных линий во время звонка,

тип подключения(телефонная линия, оптоволокно),

Интернет безопасность,

Облачное хранилище файлов,

Антивирус,

Выделенная линия технической поддержки, Стриминговое ТВ,

каталог фильмов

- Обучили Разные модели для прогнозирования поведения клиентов на основании различных признаков:

Простые модели: LogisticRegression, DecisionTree, RandForest

Бустинг: LGBM, CatBoost

Проверили лучшую модель на тестовой выборке.

Ключевая метрика для определения качества моделей AUC-ROC (Достичь значения не менее 0.85) 
(Она устойчива к дисбалансу классов, и минимизирует очень важные ошибки второго рода(False-Negative), когда клиент собирается уйти, но модель его не распознает

**Выводы:**

**Лучшая модель - CatBoost**
Гиперпараметры:
'loss_function': ['CrossEntropy'],
'learning_rate': [0.08],
'iterations': [400],
'depth': [7]

Ключевая метрика:
**ROC_AUC = 0.9020849137403646**

F1 = 0.6298850574712643
Accuracy = 0.9085746734809768
Самые значимые признаки для CatBoost:
Продолжительность, Ежемесячный платеж, Общая сумма расходов
