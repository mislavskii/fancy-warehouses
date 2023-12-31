# ТЗ для вакансии “Backend разработчик (Python, Junior)”

## Время на выполнение задания

Одни сутки (до 24ч) с момента получения задания и до момента отправки решения задания менеджеру в чат.

<aside>
💡 Скорость выполнения будет также оцениваться, поэтому не затягивайте по возможности со сдачей!

</aside>

## Файл с данными для задания

[trial_task.json](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0f8850ad-e46f-4f37-99ea-0e4e2a6af5b6/trial_task.json)

## Описание задания

### **Объяснение полей:**

```python
{
"order_id": 85787,	# уникальный id заказа  ( int, варьируется в пределах (100, 100000))
"warehouse_name": "хутор близ Диканьки",	# склад откуда отправился заказ (str)
"highway_cost": -90,	# стоимость доставки заказа (суммарная стоимости доставки всех продуктов) (int)
"products": [		# продукты входящие в заказ
{
"product": "зеленая пластинка",		# наименования продукта (str)
"price": 10,	# цена продажи за единицу товара	(int)
"quantity": 3	# количество проданного товара	(int)
},
{
"product": "зеленая пластинка",	# наименования продукта (str)
"price": 10,	# цена продажи за единицу товара	(int)
"quantity": 2	# количество проданного товара (int)
},
{
"product": "билет в Израиль",	# наименования продукта (str)
"price": 1000,	# цена продажи за единицу товара	(int)
"quantity": 1	# количество проданного товара (int)
}
]
},
```

### Объяснение highway_cost (стоимости доставки):

Когда заказ доставляется из склада, то списывается стоимость доставки. У каждого склада есть определенный тариф, определяющий стоимость доставки. Это тариф имеет размерность стоимость доставки на единицу товара.

Например для склада "гиперборея" стоимость тарифа составляет 20 рублей на единицу товара. Причем тариф не зависит от того какой именно товар мы заказали. Так, если мы заказали 5 зеленых пластинок и 3 билета в Израиль,
то стоимость тарифа будет 20*(5+3) = 160 рублей.

### Уточнение по виду отчета:

В поле "products" не обязательно могут быть только уникальные значения наименовая товаров ("product"). Иногда (как в примере выше) названия товаров могут повторяться в поле "products".

Однако поле "products" не может быть пустым

### Доп пояснение:

доходом с товара является цена продажи * количество товара

расходом является тариф для данного склада * количество товара

прибылью является доход - расход

### Требования для выполнения задания

- Использовать библиотеку Pandas

<aside>
💡 Решение задания присылайте в виде файла с кодом формата .py или .ipynb, который мы сможем запустить и увидеть решение. Для описания решения (если считаете нужным) можете использовать комментарии в самом коде или отдельным файлом.

</aside>

### Задачи:

1. Найти тариф стоимости доставки для каждого склада
2. Найти суммарное количество , суммарный доход , суммарный расход и суммарную прибыль для каждого товара (представить как таблицу со столбцами
'product', 'quantity', 'income', 'expenses', 'profit')
3. Составить табличку со столбцами 'order_id' (id заказа) и 'order_profit' (прибыль полученная с заказа). А также вывести среднюю прибыль заказов
4. Составить табличку типа 'warehouse_name' , 'product','quantity', 'profit', 'percent_profit_product_of_warehouse' (процент прибыли продукта заказанного из определенного склада к прибыли этого склада)
5. Взять предыдущую табличку и отсортировать 'percent_profit_product_of_warehouse' по убыванию, после посчитать накопленный процент. Накопленный процент - это новый столбец в этой табличке, который должен называться
'accumulated_percent_profit_product_of_warehouse'. По своей сути это постоянно растущая сумма отсортированного по убыванию столбца 'percent_profit_product_of_warehouse'.
6. Присвоить A,B,C - категории на основании значения накопленного процента ('accumulated_percent_profit_product_of_warehouse'). Если значение накопленного процента меньше или равно 70, то категория A.
Если от 70 до 90 (включая 90), то категория Б. Остальное - категория C. Новый столбец обозначить в таблице как 'category'

### Файл с примером выполнения для 4,5,6 пунктов

[testovoe_zadanie_tasks with an example.txt](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9f160a7f-d1b0-4c81-8766-b1dee5bc9a45/testovoe_zadanie_tasks_with_an_example.txt)

## Ответы на частые вопросы

**Когда стоит ожидать обратной связи по результатам проверки задания?**

- Мы постараемся проверить и ответить вам до 3 суток после получения вашего задания. Однако, время ответа может возрасти при большом потоке соискателей.

**Куда отсылать решение задания?**

- Для того чтобы мы могли оценить время ваше

го выполнения высылайте решение в тот же чат с менеджером нашей вакансии, где вы получили задание.