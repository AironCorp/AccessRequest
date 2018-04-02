# AccessRequest
My First Security App

Приложение электронный пропуск с проверкой на сервере совершает запрос на сервере.

1. Приложение локально хранит пропуски и синхронизирует их с сервером.
2. Пропуски создаются локально и верифицируются на сервере, после сохраняются на нём.
3. Форма создания пропусков состоит полей:
   1.Фотография.
   2.Имя.
   3.Фамилия.
   4.Отчество.
   4.Описание цели визита.

Электронный Пропуск

 Электронный Пропуск - добавление

  /AccessRequest/addAccess
   
   PUT
    name              String       ФИО
    data_create       String       Дата создания
    data_update       String       Дата обновления
    description       String       Описание
    photo             String       Фото
    acces             String       Допуск

 Электронный Пропуск - обновление

  /AccessRequest/upAccess
   
   POST
    _id               String       Индефикатор пропуска
    name              String       ФИО
    data_update       String       Дата обновления
    description       String       Описание
    photo             String       Фото
    acces             String       Допуск

 Электронный Пропуск - список

  /AccessRequest/getListAccess
   
   GET
   AccesList          Object[]     Список 
    _id               String       Индефикатор пропуска
    name              String       ФИО
    data_update       String       Дата обновления
    description       String       Описание
    photo             String       Фото

 Электронный Пропуск - удалить

  /AccessRequest/delAccess
   
   DELETE
    _id               String       Индефикатор пропуска

P.S.
Функция обновления и удаления, это функции администратора. 
Будет 2 приложения, в одном можно только получать список 
и создавать пропуска бездопуска с параметром Access = 0

Администраторское приложение будет иметь доступ ко всем функциям и редактировать поле допуска Access
Access = 0,пропуск не действителен.
