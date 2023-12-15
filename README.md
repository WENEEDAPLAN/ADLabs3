# DAinGD-lab3
# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #3 выполнил(а):
- Соколов Владимир Александрович
- РИ220941

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

## Цель работы
Сделать баланс 10 уровней игры Dragon Picker

## Задание 1
### Предложите вариант изменения найденных переменных для 10 уровней в игре. Визуализируйте изменение уровня сложности в таблице.
Ход работы:
- В игре возможно изменить 4 переменные
- Я предлагаю менять их одновременно и линейно

![image](https://github.com/WENEEDAPLAN/ADLabs31/assets/117916056/b9d4c215-4bd7-4bb1-a37a-3b4190d42000)


## Задание 2
###  Создайте 10 сцен на Unity с изменяющимся уровнем сложности. 
Ход работы:
- Я изменил значения переменных в соответсвтвии с данными в таблице на всех уровнях игры

![image](https://github.com/WENEEDAPLAN/ADLabs31/assets/117916056/5148954f-cf31-4dc3-91c4-6cc1ac1fdcca)



## Задание 3
### Решение в 80+ баллов должно заполнять google-таблицу данными из Python. В Python данные также должны быть визуализированы.
Ход работы:
- Код и таблица выглядят следующим образом

```
import gspread
import numpy as np

gc = gspread.service_account(filename='aidew-407713-df6a4ae09be3.json')
sh = gc.open("AIDew")

levels = 1
coefficient = 1
speed = 4
time_between_egg = 2.00
left_right_distance = 10.00
chance_direction = 0.01

total_columns = 10
initial_coefficient = 1

update_data = [['Levels', 'Coefficient', 'Speed', 'TimeBetweenEgg', 'LeftRightDistance', 'ChanceDirection']]

for i in range(total_columns):
    speed = 4 * coefficient
    time_between_egg = 2.00 / coefficient
    left_right_distance = 10.00 * coefficient
    chance_direction = 0.01 * coefficient

    update_data.append([levels, coefficient, speed, time_between_egg, left_right_distance, chance_direction])

    levels += 1
    if levels > 1:
        coefficient = initial_coefficient + 0.2 * (levels - 1)

sh.sheet1.update('A1:F' + str(total_columns + 1), update_data)

```

![image](https://github.com/WENEEDAPLAN/ADLabs31/assets/117916056/2452d1ec-ba8a-431a-ba44-350abc1a39c9)



## Выводы

Я создал линейную модель баланса на 10 уровнях игры Dragon Picker и заполнил таблицу с помощтю кода Python


| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
