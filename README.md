## Лабораторная работа №1 [15.02.2025]
### Задание №1
Выберите из таблицы orders все заказы

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%201/1.PNG?raw=true)

```
SELECT * FROM orders;
```
### Задание №2
Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%201/2.PNG?raw=true)

```
SELECT * FROM orders WHERE status IN ('cancelled','in_progress','delivery');
```
### Задание №3
Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new"

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%201/3.PNG?raw=true)

```
SELECT * FROM orders WHERE status IN ('new', 'cancelled');
```
### Задание №4
Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count).
Вывести нужно только номер (id) и сумму (sum) заказа

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%201/4.PNG?raw=true)

```
SELECT user_id, sum FROM orders WHERE products_count > 3;
```
## Лабораторная работа №2 [22.02.2025]
### Задание №161
#### Таблица

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/161/Table%201.PNG?raw=true)

1) Выберите из таблицы orders 3 самых дешевых заказа за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/161/1.PNG?raw=true)

```
select * from orders id where sum < 3000 and status != ('cancelled') order by sum desc limit 10 offset 3;
```
2) Выберите из таблицы orders 2 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/161/2.PNG?raw=true)

```
select * from orders where sum <=10000 and status != ('cancelled') order by sum desc limit 2;
```
### Задание №166
#### Таблица

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/166/Table%202.PNG?raw=true)

3) Добавьте в таблицу orders данные о новом заказе стоимостью 8000 рублей. В заказе 4 товара (products).

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/166/3.PNG?raw=true)

```
insert into orders (id, products, sum) value (6, 4, 8000);
```
#### Результат:

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/166/Result%20table.PNG?raw=true)

### Задание №167
#### Таблица

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/167/Table%203.PNG?raw=true)

4) Добавьте в таблицу products новый товар — «VR-очки», стоимостью 70000 рублей в количестве (count) 2 штук.
   
![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/167/4.PNG?raw=true)

```
insert into products (id, name, count, price) value (7, 'VR-очки', 2, 70000);
```
#### Результат:

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/167/Result%20table%202.PNG?raw=true)

### Задание №172
#### Таблица

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/172/Table%204.PNG?raw=true)

5) В таблицу products внесли данные с ошибкой, вместо "PS5" в наименовании написали IMAC. Исправьте ошибку.

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/172/5.PNG?raw=true)

```
update products set name='PS5' where id=7;
```
#### Результат:

![](https://github.com/ArthurTen/DB_Labs_Ten/blob/main/Lab%202/172/Result%20table%203.PNG?raw=true)

## Лабораторная работа №3 [01.03.2025]

Создайте таблицу users с полем id типа INT и двумя текстовыми полями, которые будут хранить имя (first_name) и фамилию (last_name). Длина имени и фамилии не превышает 50 символов.
Добавьте в таблицу трех пользователей: Дмитрия Иванова, Анатолия Белого и Дениса Давыдова.

![](https://github.com/ArthurTen/Lab_3/blob/main/lab3/1.PNG?raw=true)

```
CREATE TABLE users (
    id INT,
    first_name VARCHAR(50),
    last_name VARCHAR(50)
);
INSERT INTO users (id, first_name, last_name)
VALUES
    (1, 'Дмитрий', 'Иванов'),
    (2, 'Анатолий', 'Белый'),
    (3, 'Денис', 'Давыдов');
```

#### Результат:

![](https://github.com/ArthurTen/Lab_3/blob/main/lab3/Table.PNG?raw=true)

## Лабораторная работа №4

Задание 161

![](https://github.com/ArthurTen/Lab_4/blob/main/lab4/161/1.PNG?raw=true)

Таблица:

![](https://github.com/ArthurTen/Lab_4/blob/main/lab4/161/Table1.PNG?raw=true)
```
SELECT * FROM orders WHERE STATUS != "cancelled" ORDER BY SUM DESC LIMIT 4;
```

Задание 162

![](https://github.com/ArthurTen/Lab_4/blob/main/lab4/162/2.PNG?raw=true)

Таблица:

![](https://github.com/ArthurTen/Lab_4/blob/main/lab4/162/Table2.PNG?raw=true)
```
SELECT NAME, price FROM products where COUNT != 0 ORDER BY price ASC LIMIT 4;
```

Задание 163

![](https://github.com/ArthurTen/Lab_4/blob/main/lab4/163/3.PNG?raw=true)

Таблица:

![](https://github.com/ArthurTen/Lab_4/blob/main/lab4/163/Table3.PNG?raw=true)

```
SELECT * FROM orders WHERE SUM >= 3200 ORDER BY DATE desc LIMIT 3;
```

Задания 4 и 5

![](https://github.com/ArthurTen/Lab_4/blob/main/lab4/Task_4_5/4.PNG?raw=true)

![](https://github.com/ArthurTen/Lab_4/blob/main/lab4/Task_4_5/5.PNG?raw=true)

```
select * from products order by price limit 10,5;
```

Таблица:

![](https://github.com/ArthurTen/Lab_4/blob/main/lab4/Task_4_5/Table4.PNG?raw=true)

```
DROP TABLE IF EXISTS products;
CREATE TABLE products (
    id INT UNSIGNED NOT NULL,
    name VARCHAR(255) NULL,
    count INTEGER NULL,
    price INTEGER NULL
);
INSERT INTO products (id, name, count, price)
VALUES
    (1, 'Стиральная машина', 5, 10000),
    (2, 'Холодильник', 0, 10000),
    (3, 'Микроволновка', 3, 4000),
    (4, 'Пылесос', 2, 4500),
    (5, 'Вентилятор', 0, 700),
    (6, 'Телевизор', 7, 31740),
    (7, 'Тостер', 2, 2500),
    (8, 'Принтер', 4, 3000),
    (9, 'Активные колонки', 1, 2900),
    (10, 'Ноутбук', 4, 36990),
    (11, 'Посудомоечная машина', 0, 17800),
    (12, 'Видеорегистратор', 23, 4000),
    (13, 'Смартфон', 8, 12300),
    (14, 'Флешка', 4, 1400),
    (15, 'Блендер', 0, 5500),
    (16, 'Газовая плита', 5, 11900),
    (17, 'Клавиатура', 3, 1800);
```
