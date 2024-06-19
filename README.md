# Lab5
Функція task1

import array
import binascii

def task1(dict_list):
    merged_dict = {}
    for dictionary in dict_list:
        merged_dict.update(dictionary)
    return merged_dict
Опис:

Вхідний параметр: dict_list - список словників.
Об'єднує всі словники зі списку dict_list в один словник merged_dict за допомогою методу update().
Повертає об'єднаний словник merged_dict.
Функція task2

def task2(input_string):
    array_name, values_string = input_string.split(':')
    array_type = values_string.split(',')[0].split('(')[1]
    values = [int(val.strip()) for val in values_string.split('[')[1].split(']')[0].split(',') if val.strip()]
    interpreted_array = array.array(array_type, values)
    bytes_representation = interpreted_array.tobytes()
    return interpreted_array, bytes_representation
Опис:

Вхідний параметр: input_string - рядок, що містить ім'я масиву і його значення у форматі "name:type(values)".
Розбиває вхідний рядок за двокрапкою для отримання імені масиву і рядка значень.
Отримує тип масиву з рядка значень.
Розбиває рядок значень, щоб отримати список значень у масиві.
Створює масив interpreted_array за допомогою класу array.array з визначеним типом і значеннями.
Перетворює масив в байтове представлення за допомогою interpreted_array.tobytes().
Повертає створений масив interpreted_array і його байтове представлення.
Функція task3

def task3(input_array):
    unique_elements = []
    for item in input_array:
        if item not in unique_elements:
            unique_elements.append(item)
    return unique_elements
Опис:

Вхідний параметр: input_array - список елементів.
Створює список unique_elements для зберігання унікальних елементів.
Проходиться по кожному елементу item у вхідному списку input_array.
Додає елемент до unique_elements, якщо він ще не міститься там.
Повертає список унікальних елементів unique_elements.
Функція task4

def task4(input_array):
    full_range = set(range(10, 21))
    input_set = set(input_array)
    missing_numbers = full_range - input_set
    
    if missing_numbers:
        return missing_numbers.pop()
    else:
        return None
Опис:

Вхідний параметр: input_array - список чисел.
Створює множину full_range із чисел від 10 до 20 включно.
Створює множину input_set з елементів input_array.
Знаходить недостаючі числа, які є у full_range, але відсутні у input_set.
Якщо знайдені недостаючі числа (missing_numbers), повертає одне з них (видаляє його з множини missing_numbers).
Якщо немає недостаючих чисел, повертає None.
Функція task5

def task5(dict_list):
    distinct = []
    for dictionary in dict_list:
        for value in dictionary.values():
            if value not in distinct:
                distinct.append(value)
    unique_count = len(distinct)
    return distinct
Опис:

Вхідний параметр: dict_list - список словників.
Створює порожній список distinct для зберігання унікальних значень зі словників.
Проходиться по кожному словнику dictionary у списку dict_list.
Додає значення з кожного словника до distinct, якщо воно ще не міститься там.
Обчислює кількість унікальних значень за допомогою len(distinct).
Повертає список унікальних значень distinct.
Функція task6

def task6(dictionaries):
    letters_lists = [list(dictionary.keys()) for dictionary in dictionaries]
    combinations_count = 1
    for letters_list in letters_lists:
        combinations_count *= len(letters_list)
    return combinations_count
Опис:

Вхідний параметр: dictionaries - список словників.
Створює список letters_lists, що містить списки ключів з кожного словника dictionary у dictionaries.
Ініціалізує змінну combinations_count до 1.
Перемножує кількість ключів у кожному списку letters_list із letters_lists, щоб отримати загальну кількість комбінацій.
Повертає загальну кількість комбінацій combinations_count.
Функція task7

def task7(dictionary):
    sorted_keys = sorted(dictionary.keys(), reverse=True)
    largest_keys = sorted_keys[:3]
    return largest_keys
Опис:

Вхідний параметр: dictionary - словник з ключами і значеннями.
Сортує ключі словника dictionary у зворотньому порядку (reverse=True).
Вибирає перші три ключі з відсортованого списку sorted_keys.
Повертає список largest_keys, що містить три найбільші ключі за значенням (відсортовані у зворотньому порядку).
Функція task8

def task8(dict_list):
    combined_values = {}
    for dictionary in dict_list:
        item = dictionary['item']
        amount = dictionary['amount']
        if item in combined_values:
            combined_values[item] += amount
        else:
            combined_values[item] = amount
    return combined_values
Опис:

Вхідний параметр: dict_list - список словників, де кожен має ключі 'item' і 'amount'.
Створює порожній словник combined_values для об'єднаних значень.
Проходиться по кожному словнику dictionary у списку dict_list.
Додає кількість 'amount' до існуючого значення у combined_values[item], якщо 'item' вже є у combined_values.
Якщо 'item' ще не існує у combined_values, створює новий запис для нього з кількістю 'amount'.
Повертає словник combined_values з об'єдн







