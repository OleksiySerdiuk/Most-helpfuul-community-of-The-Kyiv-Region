# Найвідповідальніша громада Київської області

## Вступ

### Мета

Дослідити дані з 24.02.2022 по теперішній час та визначити, яка з громад Київської області витрачає найбільше бюджетних коштів на допомогу ЗСУ. 

## Огляд даних

### Джерела:
https://spending.gov.ua/new/
https://www.007.org.ua/
https://opendatabot.ua/
https://decentralization.ua/

### Громади
Іванківська громада, Ірпінська громада, Баришівська громада, Березанська громада, Бишівська громада, Богуславська громада, Бориспільська громада, Бородянська громада, Борщагівська громада, Боярська громада, Броварська громада, Бучанська громада, Білогородська громада, Білоцерківська громада, Васильківська громада, Великодимерська громада, Вишгородська громада, Вишнева громада, Володарська громада, Вороньківська громада, Гатненська громада, Глевахівська громада, Гостомельська громада, Гребінківська громада, Гірська громада, Димерська громада, Дмитрівська громада, Дівичківська громада, Зазимська громада, Згурівська громада, Золочівська громада, Кагарлицька громада, Калинівська громада, Калинівська громада, Калитянська громада, Ковалівська громада,, Кожанська громада, Козинська громада, Коцюбинська громада, Макарівська громада, Маловільшанська громада, Медвинська громада, Миронівська громада, Немішаївська громада, Обухівська громада, Переяславська громада, Петрівська громада, Поліська громада, Пристолична громада, Пірнівська громада, Пісківська громада, Ржищівська громада, Рокитнянська громада, Сквирська громада, Славутицька громада, Ставищенська громада, Студениківська громада, Таращанська громада, Ташанська громада, Тетіївська громада, Томашівська громада, Узинська громада, Українська громада, Фастівська громада, Феодосіївська громада, Фурсівська громада, Циблівська громада, Чабанівська громада, Яготинська громада

### Показники
1.Загальні річні доходи 2.Загальні річні витрати 3.Витрати на оборону

## Аналіз даних

### Підготовка та очищення даних
Проблемні питання та методи вирішення:
1. id (int64)
Проблема: Унікальні ідентифікатори можуть бути відсутніми або дубльованими.
Рішення: Перевірити унікальність ідентифікаторів і видалити дублікати.
2. doc_vob (object)
Проблема: Можуть бути некоректні або неконсистентні дані.
Рішення: Перевірити дані на коректність і стандартизувати формат.
3. doc_vob_name (object)
Проблема: Всі значення відсутні.
Рішення: Видалити цю колонку або заповнити її даними з інших джерел (якщо можливо).
4. doc_number (object)
Проблема: Можуть бути некоректні або дубльовані номери документів.
Рішення: Перевірити унікальність та формат даних.
5. doc_date (object)
Проблема: Деякі дати відсутні.
Рішення: Конвертувати в формат дати (datetime), заповнити відсутні значення або видалити рядки з відсутніми даними.
6. doc_v_date (object)
Проблема: Деякі дати відсутні.
Рішення: Аналогічно до doc_date, конвертувати в формат дати та заповнити або видалити рядки з відсутніми даними.
7. trans_date (object)
Проблема: Можуть бути некоректні формати дат.
Рішення: Конвертувати в формат дати (datetime) і перевірити коректність.
8. amount (float64)
Проблема: Можуть бути некоректні або аномальні значення.
Рішення: Перевірити розподіл даних та обробити аномалії (наприклад, видалити або скоригувати екстремальні значення).
9. amount_cop (int64)
Проблема: Можуть бути некоректні або аномальні значення.
Рішення: Перевірити коректність значень та узгодженість з колонкою amount.
10. currency (object)
Проблема: Можуть бути некоректні або неконсистентні значення.
Рішення: Перевірити коректність та стандартизувати формат даних.
11. payer_edrpou (object)
Проблема: Можуть бути некоректні або дубльовані значення.
Рішення: Перевірити унікальність та коректність даних.
12. payer_name (object)
Проблема: Можуть бути некоректні або неконсистентні значення.
Рішення: Стандартизувати формат і перевірити коректність даних.
13. payer_account (object)
Проблема: Можуть бути некоректні або неконсистентні значення.
Рішення: Перевірити коректність даних та формат.
14. payer_mfo (object)
Проблема: Більшість значень відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
15. payer_bank (object)
Проблема: Більшість значень відсутні.
Рішення: Аналогічно до payer_mfo, видалити колонку або заповнити її даними з інших джерел.
16. payer_edrpou_fact (object)
Проблема: Всі значення відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
17. payer_name_fact (object)
Проблема: Всі значення відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
18. recipt_edrpou (object)
Проблема: Можуть бути некоректні або дубльовані значення.
Рішення: Перевірити унікальність та коректність даних.
19. recipt_name (object)
Проблема: Можуть бути некоректні або неконсистентні значення.
Рішення: Стандартизувати формат і перевірити коректність даних.
20. recipt_account (object)
Проблема: Можуть бути некоректні або неконсистентні значення.
Рішення: Перевірити коректність даних та формат.
21. recipt_mfo (object)
Проблема: Більшість значень відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
22. recipt_bank (object)
Проблема: Більшість значень відсутні.
Рішення: Аналогічно до recipt_mfo, видалити колонку або заповнити її даними з інших джерел.
23. recipt_edrpou_fact (object)
Проблема: Всі значення відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
24. recipt_name_fact (object)
Проблема: Всі значення відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
25. payment_details (object)
Проблема: Можуть бути некоректні або неконсистентні значення.
Рішення: Перевірити коректність даних та стандартизувати формат.
26. doc_add_attr (object)
Проблема: Всі значення відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
27. region_id (float64)
Проблема: Деякі значення відсутні.
Рішення: Заповнити відсутні значення або видалити рядки з відсутніми даними.
28. payment_type (object)
Проблема: Можуть бути некоректні або неконсистентні значення.
Рішення: Перевірити коректність та стандартизувати формат даних.
29. payment_data (object)
Проблема: Всі значення відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
30. source_id (int64)
Проблема: Можуть бути некоректні або дубльовані значення.
Рішення: Перевірити унікальність та коректність даних.
31. source_name (object)
Проблема: Можуть бути некоректні або неконсистентні значення.
Рішення: Перевірити коректність та стандартизувати формат даних.
32. kekv (float64)
Проблема: Деякі значення відсутні.
Рішення: Заповнити відсутні значення або видалити рядки з відсутніми даними.
33. kpk (object)
Проблема: Деякі значення відсутні.
Рішення: Заповнити відсутні значення або видалити рядки з відсутніми даними.
34. contractId (object)
Проблема: Всі значення відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
35. contractNumber (object)
Проблема: Більшість значень відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
36. budgetCode (object)
Проблема: Деякі значення відсутні.
Рішення: Заповнити відсутні значення або видалити рядки з відсутніми даними.
38. system_key (object)
Проблема: Всі значення відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).
39. system_key_ff (object)
Проблема: Всі значення відсутні.
Рішення: Видалити колонку або заповнити її даними з інших джерел (якщо можливо).

Загальні рекомендації:
Видалення колонок з великою кількістю відсутніх значень, якщо вони не несуть критичної інформації.
Заповнення відсутніх значень (наприклад, середніми значеннями, найбільш ймовірними значеннями, даними з інших джерел).
Стандартизація і нормалізація даних для забезпечення консистентності.
Перевірка унікальності ідентифікаторів і ключових колонок.
Конвертація типів даних (наприклад, з строкового формату в дати або числовий формат) для коректної обробки.

## Jupyter Notebook
https://www.datacamp.com/datalab/w/3c676a97-2e93-4301-b0eb-0d3850d12c88/edit

## Тип аналітичного рішення
Описова аналітика (Descriptive Analytics)

## Додаткові дані
1.Річний бюджет громади

## Метод збору додаткових даних
Невідомий

## Не вирішені питання
Пошук джерела даних про обсяг річного бюджету

## Приклади візуалізації даних
https://100.datavizproject.com/data-type/viz12/
![image](https://github.com/user-attachments/assets/8b28e859-5094-48c7-996c-3a04f4173a55)
https://100.datavizproject.com/data-type/viz24/
![image](https://github.com/user-attachments/assets/f4ea4eec-b593-4567-b43f-16425823140f)
https://100.datavizproject.com/data-type/viz27/
![image](https://github.com/user-attachments/assets/a33eda00-bf90-4423-97a3-825209122b6f)

## Статус проекту - "в процесі".

