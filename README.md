# Employee-Attrition-Analytics-in-Excel

У цьому файлі представлено покроковий опис виконання проєкту з дата клінінгу та EDA у Microsoft Excel.

## 1. Завантаження [датасету із Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

Датасет містить дані про близько 1500 працівників. Метою аналізу буде, зрозуміти причини плинності кадрів і знайти способи зменшення цього показника.

## 2. Імпорт та підготовка даних

Скористаємось інструментом для імпорту даних у Excel і перейдемо до редактору **Power Query** щоб підготувати дані перед роботою.

### 1) Видалення непотрібних стовпців

У таблиці є стовпці *EmployeeCount*, *Over18*, *StandardHours*. У всіх цих стовпцях міститься лише одне унікальне значення.

![image](https://github.com/user-attachments/assets/8f0ac4e4-56e8-490d-a1a6-05e7db391042)

Тому ці стовпці не є інформативними і їх потрібно видалити.

### 2) Заповнення числових даних словами

На сторінці Kaggle цього датасету є пояснення деяких позначень. Це стосується стовпців *Education*, *EnvironmentSatisfaction*, *JobInvolvement*, *JobSatisfaction*, *PerformanceRating*, *RelationshipSatisfaction*, *WorkLifeBalance*. Замінимо числові дані на відповідні їм текстові. Для початку змінимо тип цих стовпців. 

Продемонструємо усе на стовпці *Education*.

![image](https://github.com/user-attachments/assets/cd1969fb-1e50-4be1-a5b8-3067a92d5289) **---->**
![image](https://github.com/user-attachments/assets/16eea66b-dfaf-4c92-b83d-82f9abca52ff) **---->**
![image](https://github.com/user-attachments/assets/b298704a-5835-4d13-93df-c5170fbbfa5b) **---->**

![image](https://github.com/user-attachments/assets/08d8c328-7c17-4a17-b9c8-2155031bf5b1) **---->**
![image](https://github.com/user-attachments/assets/ee185d19-91f2-4ba7-a4ac-02b3f0f0cebd) **---->**

*повторюємо це з іншими числовими значеннями* **---->**
![image](https://github.com/user-attachments/assets/920ebc66-c9f2-4940-a3c5-8d3f627797fd)

Тепер зробимо такі ж дії з іншими стовпцями.

Також можна уточнити стовпець *JobLevel* (хоч визначення й не було у Kaggle).

![image](https://github.com/user-attachments/assets/597b8dc9-f5d6-4ea1-b9db-931d4f6f8385)

### 3) Стандартизація даних

Стовпці *Attrition* та *OverTime* містять значення **Yes**, **No** і є текстового типу. Краще змінити значення на **True**, **False** відповідно та тип на **Bool**.

![image](https://github.com/user-attachments/assets/ffe35f95-ebcc-4f74-abc1-660e2f136b45) **---->**
![image](https://github.com/user-attachments/assets/0ecbb836-045e-4df5-a39f-9396e04b0f0f) **---->**
![image](https://github.com/user-attachments/assets/4f4d0390-e345-4a0b-b4f5-84467e5d2753) **---->**

![image](https://github.com/user-attachments/assets/913d212f-b7e6-4dad-bc20-5c645b1cd88e) **---->**
![image](https://github.com/user-attachments/assets/6700c883-be15-46ec-95e5-2af742be8ddb) **---->**

![image](https://github.com/user-attachments/assets/7c17cd74-2f08-4381-998f-41049ade1997) **---->**
![image](https://github.com/user-attachments/assets/34bc9bf6-9efa-49da-b6a4-45ea1f09ce01)

Також є стовпець *BusinessTravel*, що містить такі значення 

![image](https://github.com/user-attachments/assets/62f37230-950d-46a0-acf8-6a53ff0126c6)

Замінимо дефіс на нижнє підкреслювання у цьому стовпці, щоб дані виглядали в одному стилі.

![image](https://github.com/user-attachments/assets/dd2774e1-766b-46ae-af1d-c9a1b60af547) **---->**
![image](https://github.com/user-attachments/assets/ee3974c9-44b4-4faf-b49b-bc99c2e06418)

### 4) Завершення підготовки

Перенесемо стовпець *EmployeeNumber* на першу позицію, оскільки це значення тут є Primary Key. І після цього завершуємо підготовку даних.
В результаті маємо таку гарну таблицю (продемонстровано лише фрагмент).

![image](https://github.com/user-attachments/assets/15021a72-402d-4d6b-a097-87ddcae4a961)

## 3. Аналіз даних

### 1) Побудова зведених таблиць

Проаналізуємо які параметри найбільше впливають на звільнення працівників. Для початку відфільтруємо усі значення так, щоб бачити лише звільнених працівників і перенесемо ці дані на окремий аркуш.

![image](https://github.com/user-attachments/assets/6b96579d-1f30-4e13-a1f6-abc6fb004977)

Створимо ще один аркуш, на якому використаємо зведені таблиці для пошуку значень яким відповідає найбільша кількість звільнених працівників. 

Я переглянув багато з цих значень і виділив серед них основні.

![image](https://github.com/user-attachments/assets/734bcb54-8135-4cc5-af9e-cfc96cbc64b6)

![image](https://github.com/user-attachments/assets/c3ec824f-8c75-499f-ae3e-ac2aebef8fb0)

![image](https://github.com/user-attachments/assets/8d5a1a77-6977-4189-be0b-0154b648fdf3)

![image](https://github.com/user-attachments/assets/bbf2a06c-ea51-4ec1-a779-4c23a379fd0f)

![image](https://github.com/user-attachments/assets/215d8651-f404-409a-9ab3-1da0ba7bc39f)

Також я зробив ще одну зведену таблицю, використовуючи дані із тієї першої таблиці, що містить дані не лише звільнених працівників. 

У цій зведеній таблиці було проаналізовано різницю у середніх значеннях різних числових характеристик.

![image](https://github.com/user-attachments/assets/0590b1e7-2a43-4453-bc47-c17694c2286e)

Змінимо формат числа, щоб заокруглювати числа до 2-х знаків після коми. Це буде зручно для подальшої візуалізації.

![image](https://github.com/user-attachments/assets/978356eb-139f-414f-827b-b15dcc662240)

### 2) Візуалізація

Тепер, використовуючи зведені таблиці, візуалізуємо отримані дані та проаналізуємо їх.

#### **Відсоток звільнень залежно від сфери діяльності**

![image](https://github.com/user-attachments/assets/69a15338-f7cd-41b2-98ff-96564165a4af)

Переважна більшість звільнень стосується працівників у сфері розробки та дослідження, майже в півтора рази менша кількість звільнень стосується працівників у сфері продажів. А найменша кількість звільнень відбувається у сфері управління персоналом. Переглянемо загальну кількість робітників у всіх сферах

![image](https://github.com/user-attachments/assets/fe1bd035-b254-4cb9-a600-56330d7318a8)

Бачимо, що ця різниця у кількості звільнень спричинена загальною різницею в кількості працівників у цих відділеннях.

#### **Відсоток звільнень залежно від професії та рівня посади**

![image](https://github.com/user-attachments/assets/1707c645-3109-41db-b16e-805dcc92b3f0)

![image](https://github.com/user-attachments/assets/bc743b45-c8c8-4a71-bc63-3ff58b1da83b)

Найбільша кількість звільнень припадає на професії *Laboratory Technician*, *Sales Executive*, *Research Representative*, *Sales Representative*. А за рівнем посади переважна більшість звільнень (60%) припадає на працівників-початківців та ще 20% на досвідчених працівників, а менеджмент зазнає найменше звільнень.

Як і в попередньому кроці розглянемо загальну кількість працівників у певних професіях. Але окрім цього використаємо функцію **Xlookup** щоб по назві професії знайти її рівень на сферу.

```
  =XLOOKUP(D81,Employee_Attrition_Table!O:O,Employee_Attrition_Table!N:N,"Не знайдено",0)
```

![image](https://github.com/user-attachments/assets/bf0b27f8-c5e6-4b76-a578-c8b6e9e5564a)

Помітно що справді більша частина працівників належить до тих професій та рівнів посади, що найбільше зазнають звільнень. Отже, як і в попередньому випадку, причиною великої кількості звільнень у цих категоріях є велика кількість працівників у них.

#### **Відсоток звільнень залежно від залученості в роботу**

![image](https://github.com/user-attachments/assets/4018f963-4343-4be0-a3c1-a863647a55ff)

Подивимось на загальну кількість людей, а не лише серед звільнених

![image](https://github.com/user-attachments/assets/b2b2267b-efeb-4e56-8cc3-9524a6d9fd15)

Також скористаємось **Xlookup** щоб об'єднати ці значення у новій таблиці

```
  =XLOOKUP(E17,E$2:E$5,E$9:E$12,"Не знайдено")
```

![image](https://github.com/user-attachments/assets/af58c2b5-d58e-4d52-a1dc-696818fac09b)

Тепер візуалізуємо це

![image](https://github.com/user-attachments/assets/2c024731-253c-4628-88fb-e811141f1e02)

Помітно, що при високій та дуже високій залученості кількість звільнень у відсотковому відношенні менша за загальний відсоток працівників. Це значить, що робітники, які мають високу залученість у роботі мають тендецію до того щоб не йти з роботи чи не бути звільненими. У людей з середньою та низькою залученістю спостерігається протилежна тенденція. Хоч таких робітників і небагато, але ті, які є, звільняються частіше.

#### **Відсоток звільнень залежно від віку**

![image](https://github.com/user-attachments/assets/f3d6528a-8b9a-43a6-a375-4c416630d6f8)

Так як і в попередньому кроці за допомогою **Xlookup** створюємо нову таблицю для того щоб зробити наглядну візуалізацію.

Після цього маємо такий графік.

![image](https://github.com/user-attachments/assets/84745e76-3073-440f-8fba-a820a0284740)

Тут помітно, що найбільше звільнень відбуваються із працівниками віком від 28 до 32 років, а також є пік у точці 26 років.

#### **Зв'язок середніх значень деяких числових характеристик зі звільненням**

![image](https://github.com/user-attachments/assets/668fd5a7-4c49-4d14-85b5-5af2dd9608ea)

Тут беруться до уваги такі характеристики як *Загальний робочий стаж*, *Стаж у цій компанії*, *Стаж на цій посаді*, *Кількість років, що пройшли з моменту останнього підвищення*, *Кількість років роботи із поточним менеджером*. Тут ми чітко бачимо, що у людей, які не звільнились, в середньому всі ці характеристики є вищими, порівняно зі звільненими.
