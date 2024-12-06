# Анализ данных в разработке игр
Отчет по лабораторной работе #3 выполнил(а):
- Федосова Анастасия Андреевна
- РИ-230914
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1. Предложите вариант изменения найденных переменных для 10 уровней в игре. Визуализируйте изменение уровня сложности в таблице. 
- Задание 2. Создайте 10 сцен на Unity с изменяющимся уровнем сложности.
- Задание 3. Решение в 80+ баллов должно визуализировать данные из google-таблицы, и с помощью Python передавать в проект Unity. В Python данные также должны быть визуализированы
- Выводы.
- ✨Magic ✨

## Цель работы
Разработать оптимальный баланс для десяти уровней игры Dragon Picker

## Задание 1
### Предложите вариант изменения найденных переменных для 10 уровней в игре. Визуализируйте изменение уровня сложности в таблице. 
Я решила изменить сложность уровней линейно, убавляя и прибавляя постоянные значения.
Основные факторы сложности - скорость дракона и время разброса яиц. Получается, чем быстрее дракон и меньший промежуток падения яиц, тем выше сложность.
Ссылка на GoogleSheet: https://docs.google.com/spreadsheets/d/1-CzOcjDpIeViLnmHFhGGsNNcRaKx2THLCp5tYiNT_wc/edit?gid=1685939914#gid=1685939914


## Задание 2
### Создайте 10 сцен на Unity с изменяющимся уровнем сложности.
Созданные сцены на Unity находятся в папке DragonPickerFedosova

## Задание 3
### Решение в 80+ баллов должно заполнять google-таблицу данными из Python. В Python данные также должны быть визуализированы.

Скрипт на python, заполняющий таблицу из первого задания данными:
```python
# Инициализация значений
initial_speed = 4
egg_drop_interval = 2
horizontal_distance = 10
direction_chance = 0.01
row_index = 2

# Обновление значений с помощью цикла
for i in range(row_index, 12):
    sh.sheet1.update(('B' + str(i)), str(initial_speed))  # Записываем скорость
    sh.sheet1.update(('C' + str(i)), str(round(egg_drop_interval, 3)))  # Интервал сброса, округленный до 3 знаков
    sh.sheet1.update(('D' + str(i)), str(horizontal_distance))  # Горизонтальное расстояние
    sh.sheet1.update(('E' + str(i)), str(round(direction_chance, 3)))  # Вероятность направления, округленная до 3 знаков

    initial_speed += 1  # Увеличиваем скорость на 1
    egg_drop_interval -= 0.1  # Уменьшаем интервал сброса на 0.1
    horizontal_distance += 1  # Увеличиваем горизонтальное расстояние на 1
    direction_chance += 0.05  # Увеличиваем вероятность изменения направления на 0.05
```
## Выводы
Я разработала достаточно оптимальный вариант увеличения сложности для игры. Научилась отображать сложность уровней. Научилась писать код на заполнение гугл-таблиц и отображать данные в python

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
