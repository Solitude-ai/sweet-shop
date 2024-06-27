# sweet-shop
Учебная практика

Создание базы данных 
Create table Оплата (
Код_оплаты int primary key,
Сумма money not null,
Дата date)

Create table Способ_получения (
Код_способа int primary key,
Выбор_получения char(30))

Create table Заказ (
Код_заказа int primary key,
Код_способа int,
Наполение char(50),
Сумма money,
Дата date,
Foreign key(Код_способа) references Способ_получения(Код_способа))

Create table Покупатель (
Код_покупателя int primary key,
ФИО char(70),
Номер char(15),
Адрес char(80),
Код_заказа int,
Код_оплаты int,
Foreign key(Код_заказа) references Заказ(Код_заказа),
Foreign key(Код_оплаты) references Оплата(Код_оплаты))
