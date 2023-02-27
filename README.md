# Домашнее задание к занятию 12.3. «SQL. Часть 1» - `Мальцев Виктор

---

Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” 
и не содержат пробелов.

Ответ:

select DISTINCT district from sakila.address where district like 'K%a' and district not like '% %';

![alt text](https://github.com/vmmaltsev/screenshot2/blob/main/Screenshot_24.png)



---

Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, 
которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно 
и стоимость которых превышает 10.00.

Ответ:

select * from sakila.payment where payment_date >= '20050615' and payment_date <'20050619'
HAVING amount >'10';

![alt text](https://github.com/vmmaltsev/screenshot2/blob/main/Screenshot_21.png)

---

Задание 3

Получите последние пять аренд фильмов.

Ответ:

SELECT * FROM sakila.rental ORDER BY rental_id DESC LIMIT 5;
SELECT * FROM sakila.rental ORDER BY rental_date DESC LIMIT 5;

![alt text](https://github.com/vmmaltsev/screenshot2/blob/main/Screenshot_22.png)
![alt text](https://github.com/vmmaltsev/screenshot2/blob/main/Screenshot_25.png)


---

Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie.

Сформируйте вывод в результат таким образом:

    все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
    замените буквы 'll' в именах на 'pp'.

Ответ:

SELECT customer_id, store_id, REPLACE (LOWER(first_name), 'll', 'pp'), LOWER(last_name), email, address_id, active, create_date, last_update
FROM sakila.customer 
where active = '1' AND first_name in ('Kelly', 'Willie');

![alt text](https://github.com/vmmaltsev/screenshot2/blob/main/Screenshot_23.png)



