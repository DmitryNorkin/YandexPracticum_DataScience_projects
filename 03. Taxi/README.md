<div id="badges">
  <a href="Количество заказов такси на следующий час">
    <img src="https://img.shields.io/badge/LinkedIn-blue?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn Badge"/>
  </a>
  <a href="[link to your Medium profile]">
    <img src="https://img.shields.io/badge/Medium-white?style=for-the-badge&logo=medium&logoColor=black" alt="Medium Badge"/>
  </a>
  <a href="[link to your Tableau profile]">
    <img src="https://img.shields.io/badge/tableau-navy?style=for-the-badge&logo=tableau&logoColor=white" alt="Tableau Badge"/>
  </a>
</div>



**"Количество заказов такси на следующий час"**

**Цель:**
В данном Проекте для того, чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час.

Значение метрики RMSE на тестовой выборке должно быть не больше 48.

**Ход исследования и Инструменты:**

1. Выполнили ресемплирование временного ряда по одному часу.

Выявили:

- Тренд (плавное изменение среднего значения ряда без повторяющихся закономерностей) увеличения количества заказов в течение всего времени!

- Сезонность: Пиковые значения количества заказов приходится в полночь. Минимальные значения в 6 часов утра

2. Провели обучение разных моделей с различными гиперпараметрами.

(LGB, RandomForest, CatBoost, LinRegression, ElasticNetCV) 

**Выводы:**

Все модели на тестовой выборке дали качество приемлемое для условия проекта

Лучше всех прогнозирует LGB, RMSE = 40.287981
