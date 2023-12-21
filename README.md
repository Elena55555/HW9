# Домашнее задание урока  Stream API и Optional.
Цель сегодняшней домашней работы — научиться менять реализацию через циклы на Steam API.

В этой домашней работе вам понадобятся данные из курсовой.
 

Шаг 1. Добавить в поле Employee поля «Зарплата» и «Отдел» из курсовой работы.

Шаг 2. В текущий проект на Spring перенести методы работы с отделами из курсовой работы. 

Шаг 3. Заменить реализацию через циклы на Stream API. Написать новый контроллер и сервис, которые будут:

1. Возвращать сотрудника с максимальной зарплатой на основе номера отдела, который приходит в запрос из браузера.
    
    ```java
    /departments/max-salary?departmentId=5
    ```
    
2.  Возвращать сотрудника с минимальной зарплатой на основе номера отдела.
    
    ```java
     /departments/min-salary?departmentId=5 
    ```
    
3. Возвращать всех сотрудников по отделу. 
    
    ```java
    /departments/all?departmentId=5
    ```
    
4. Возвращать всех сотрудников с разделением по отделам.
    
    ```java
     /departments/all
    ```
    
 
    Для того чтобы получить список сотрудников, надо в новый сервис заинжектить старый сервис и запросить список всех сотрудников, затем этот список пропустить через Stream API.
    
    Для поиска минимальной или максимальной зарплаты нужно после фильтрации использовать методы min и max, передав в качестве компаратора строку кода, представленную ниже.
    
    ```java
    Comparator.comparingInt(employee -> employee.getSalary())
    ```
    
- Критерии оценки:
    - В поле Employee  добавлены новые поля «Зарплата» и «Отдел»
    - Переписаны контроллер и сервис, которые возвращают сотрудника с максимальной зарплатой на основе номера отдела, который приходит в запрос из браузера.
    - Переписаны контроллер и сервис, которые возвращают сотрудника с минимальной зарплатой на основе номера отдела.
    - Переписаны контроллер и сервис, которые возвращают всех сотрудников по отделу
    - Переписаны контроллер и сервис, которые возвращают всех сотрудников с разделением по отделам.
    - Реализация проекта заменена через циклы на Stream API.

🐝 FAQ 

Вопросы, которые уже задавали ученики после этого урока. 
Возможно, вы найдёте ответ на свой вопрос.

- Смотреть
    1. ***Нужно сотрудников также с помощью метода add добавлять, или же в main создать записи о сотрудниках ?***
    
    **Ответ**:  Все действия в программе  мы теперь проводим через сервис с методом add. 
    
    1. ***В домашке написано "В текущий проект на Spring перенести методы работы с отделами из курсовой работы." Но в курсовой работе почти все методы завязаны на зарплате (общая сумма за, минимальная, максимальная, средняя и вывод ФИО сотрудников). Это имеется в виду?***
    
    **Ответ**: Да, нужно перенести те поля, которые ранее не использовались и, соответственно, методы по поиску зарплаты среди сотрудников департамента.