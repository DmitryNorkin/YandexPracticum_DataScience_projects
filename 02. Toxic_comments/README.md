**Определение токсичных комментариев**

В данном проекте:

**Цель:**  

Используя NLP классифицировать комментарии на поизитивные и негативные

**Ход Исследования и инструменты:**

1. Была проведена обработка данных:

Лемматизация и обработка регулярными выражениями.

Векторизация текста.

2. Использовали Модели для Классификации:  

LogisticRegression

LinearSVC

LGBMClassifier

**Выводы:** 

Все модели показали приемлемое по условию проекта качество f1 >0.75

LinearSVC показала Лучшее качество прогноза (f1 = 0.775)
