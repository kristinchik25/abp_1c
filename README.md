# abp_1c

# Создание задач 
Создадим новую задачу в конфигураторе 
<img width="893" height="733" alt="image" src="https://github.com/user-attachments/assets/fd3b57e9-5826-4aa0-b40e-3de4d3887a14" />

В режиме отладки сразу проверяем задачу, все верно, задачи добавляются и правильно отображаются 
<img width="1430" height="694" alt="image" src="https://github.com/user-attachments/assets/5cef8ceb-334e-473a-849e-32d56447069b" />

Функционал "Выполено" работает, выполненные задачи отмечаются галочкой 

<img width="1423" height="344" alt="image" src="https://github.com/user-attachments/assets/13209f3a-628f-4ea1-a961-1e9965ee53cb" />

# Адресация задач
Создадим и наполним справочник "Сотрудники", чтобы показать фунционал распределения задач 

<img width="1276" height="573" alt="image" src="https://github.com/user-attachments/assets/84b3f222-4da3-477c-b0a8-0be392d207b6" />

Добавим реквизит адресации "Исполнитель", тип справочник "Сотрудники"
<img width="439" height="320" alt="image" src="https://github.com/user-attachments/assets/05db9a00-641b-4b2a-8066-1cb55d821ccc" />

<img width="922" height="871" alt="image" src="https://github.com/user-attachments/assets/c00beb27-b5c8-4456-ba6e-6eea767958be" />

Теперь каждой задаче можно добавить сотрудника из нашего справочника, проверяем, все работает

<img width="1425" height="696" alt="image" src="https://github.com/user-attachments/assets/f003cde1-e54c-4b22-b6be-c74c018fd29f" />


<img width="1428" height="324" alt="image" src="https://github.com/user-attachments/assets/ca9bfcec-943b-4aa8-b24a-d3a9e3d3fac1" />

# Текущие задачи активного пользователя 
Для реализации функционала понадобятся: 
- Пользователи
- Роли
- Параметр сеанса
- Основной реквизит адресации
- Список задач по исполнителю
- Отбор невыполненных задач

## Роли
Добавим одну универсальную роль в соотвествии с заданием 

<img width="995" height="630" alt="image" src="https://github.com/user-attachments/assets/33123f9f-2502-4ac5-83fd-ca3b85bf60bd" />

Обновляем конфигурацию и переходим к пользователям

## Пользователи 
Добавим пользователей в соответствии с справочником "Сотрудники", дадим роль "Все права", повторим со всеми

<img width="905" height="746" alt="image" src="https://github.com/user-attachments/assets/0cf262ec-a05f-4912-9dd9-866cc979185f" />

Вот как выглядит список пользователей после добавлений 

<img width="838" height="399" alt="image" src="https://github.com/user-attachments/assets/9fd4e29b-6107-45c5-a8be-0504c1e3d154" />

## Параметр сеанса

Добавим параметр сеанса "Текущий пользователь"

<img width="1070" height="580" alt="image" src="https://github.com/user-attachments/assets/d56d0691-6d6d-42c0-8ea8-bf1576abff37" />

Добавляем конфигурацию в модуль сеанса 

Программный код: 

````
Процедура УстановкаПараметровСеанса(ТребуемыеПараметры)
	ПараметрыСеанса.ТекущийПользователь=
	                      Справочники.Сотрудники.НайтиПоНаименованию(ИмяПользователя());
КонецПроцедуры

````

<img width="1282" height="316" alt="image" src="https://github.com/user-attachments/assets/57230fa4-6ca7-414e-a907-35c9030c22ea" />

Следующим этапом будет отбор задач по исполнителю, применим следующие настройки

<img width="624" height="403" alt="image" src="https://github.com/user-attachments/assets/278b6a9d-b7ff-4cf0-8a7a-c26911797638" />

<img width="1196" height="617" alt="image" src="https://github.com/user-attachments/assets/511a9269-3e22-4030-a813-1b00c0310836" />

<img width="561" height="523" alt="image" src="https://github.com/user-attachments/assets/52c95292-340e-4456-84ac-6eff7acd4fd0" />

<img width="1449" height="728" alt="image" src="https://github.com/user-attachments/assets/0f795e4d-646e-464e-86d7-8a42f2895925" />

<img width="1049" height="613" alt="image" src="https://github.com/user-attachments/assets/afde511c-3eea-4f29-be93-48b524929c00" />

Выносим настроенную форму на начальный экран пользователя 

<img width="1590" height="586" alt="image" src="https://github.com/user-attachments/assets/2a07068e-c6aa-4de3-ad46-460bba7bd193" />


Проверяем результат, все верно

<img width="1431" height="426" alt="image" src="https://github.com/user-attachments/assets/0047f69d-dbd6-44c5-b9b2-791948f3f5dd" />

# Бизнес-процессы
Для возможности автоматического создания задач добавим новый объект "Бизнес-процесс". Свяжем с механизмом задач, чтобы задачи автоматически распределялись между сотрудниками. 

<img width="642" height="605" alt="image" src="https://github.com/user-attachments/assets/9c546fb5-1584-45bb-8866-783aba70da42" />

Карту маршрута можно нарисовать во вкладке "Прочее"

<img width="1269" height="649" alt="image" src="https://github.com/user-attachments/assets/04f35a6c-e87a-4a8b-9321-efc978f82efa" />

# Карта маршрута 
Для примера нарисуем и заполним карту маршрута 

<img width="1086" height="949" alt="image" src="https://github.com/user-attachments/assets/da07274d-17ee-42c5-bb40-0151e177fd6d" />

<img width="811" height="800" alt="image" src="https://github.com/user-attachments/assets/a9958c27-6649-4236-8b1f-be37b2d6e574" />

Проверим конфигурацию 

<img width="1074" height="468" alt="image" src="https://github.com/user-attachments/assets/150bec53-fbd3-42f8-a089-092d147ba960" />

Проведем все задачи процесса

<img width="744" height="383" alt="image" src="https://github.com/user-attachments/assets/b981572d-c637-40f1-847f-5c7f7db8636c" />

Бизнес-процесс завершен 

<img width="1439" height="423" alt="image" src="https://github.com/user-attachments/assets/f37d1c4e-4dd0-49c4-b800-b5c90bdf337d" />

# Персональная адресация
Необходимо настроить этот параметр, чтобы исполнитель задачи назначался автоматически, через двойное нажатие на элементы схемы, назначаем исполнителя

<img width="380" height="769" alt="image" src="https://github.com/user-attachments/assets/8c5ed0b1-1e16-48ea-9232-d7b1011300af" />

# Карта маршрута у пользователя 
Дадим возможность пользователям отслеживать положение этапов бизнес-процессов, создадим основную форму для бизнес-процесса

<img width="895" height="800" alt="image" src="https://github.com/user-attachments/assets/8b0b2f9d-fabf-49eb-9048-4d02e0aa95f4" />

Настраиваем объект карта маршрута 

<img width="821" height="908" alt="image" src="https://github.com/user-attachments/assets/2ccc4a66-ccc6-4ab4-a7a4-59caf8550a4d" />

<img width="1279" height="618" alt="image" src="https://github.com/user-attachments/assets/a207a30d-1de8-48f0-b25b-54a575c892f2" />

Для формы воспользуемся событием При создании на сервере 

<img width="647" height="273" alt="image" src="https://github.com/user-attachments/assets/9241bcef-d350-4017-9e16-cb7d6bb1b389" />

<img width="1264" height="612" alt="image" src="https://github.com/user-attachments/assets/4371595d-7887-4272-a599-cfe40ef3b7fb" />


Заполняем программный код программным кодом 

<img width="1265" height="610" alt="image" src="https://github.com/user-attachments/assets/f8822ff6-caeb-4156-a7a5-545ea464bbfb" />


# Точка выбора варианта 
Создаем перечисление "ВидыРабот"
<img width="665" height="564" alt="image" src="https://github.com/user-attachments/assets/c26ae921-7c64-4212-93e3-84a473dd1774" />

Добавляем реквизит в бизнес-процесс

<img width="1035" height="722" alt="image" src="https://github.com/user-attachments/assets/a00aced8-1342-4d21-b306-87d69b220d84" />

Отображаем поле на форме бизнес-процесса

<img width="1307" height="805" alt="image" src="https://github.com/user-attachments/assets/23620fa3-d65e-45b0-938e-f03aba893295" />


Открываем карту маршрута и изображаем на ней карту выбора

<img width="708" height="670" alt="image" src="https://github.com/user-attachments/assets/98d290b5-490c-4edd-8fe5-9436546289a5" />



# Ролевая адресация 
Таблица ролей 
| Фамилия    | Должность           | Подразделение      |
|------------|---------------------|--------------------|
| Кукурузин  | Мастер-приемщик     | Администрация      |
| Данилов    | Механик             | Ремонтный цех      |
| Зияев      | Маляр               | Покрасочный цех    |

Создадим справочники "Подразделения" и "Должности"

<img width="1356" height="649" alt="image" src="https://github.com/user-attachments/assets/6f206b54-5f9a-44c5-8c73-b1d47656a108" />

<img width="1321" height="649" alt="image" src="https://github.com/user-attachments/assets/904ec3ce-74ae-40ae-86ac-1258040a3a2a" />

Теперь приступим к созданию регистра адресации, настроим его

<img width="626" height="640" alt="image" src="https://github.com/user-attachments/assets/90de9f2c-6295-405c-aa51-7708fa17caf3" />

<img width="1388" height="550" alt="image" src="https://github.com/user-attachments/assets/6f5b3669-0de2-4d0b-a329-8e12f90d9745" />

<img width="1405" height="551" alt="image" src="https://github.com/user-attachments/assets/99deea56-2390-4ca1-b137-82270cd662c2" />

<img width="1394" height="552" alt="image" src="https://github.com/user-attachments/assets/f0d7aee3-bc5c-49ba-bc83-2589dd6413bc" />

Регистр адресации готов,  теперь необходимо связать механизм Задач с Регистром сведений

<img width="1407" height="622" alt="image" src="https://github.com/user-attachments/assets/4974f2d7-a7e1-433d-bb26-2bca281dd496" />

<img width="1394" height="586" alt="image" src="https://github.com/user-attachments/assets/5f0eb145-1584-47c1-8700-690778fb59ef" />

Теперь свяжем реквизиты адресации с измерениями регистра сведений 

<img width="747" height="294" alt="image" src="https://github.com/user-attachments/assets/cbe64de5-470b-41d3-8e52-f6ba8b10f98e" />

<img width="750" height="294" alt="image" src="https://github.com/user-attachments/assets/36e79f8b-632e-40cd-b48d-86eb6723620b" />

<img width="761" height="300" alt="image" src="https://github.com/user-attachments/assets/d586d44b-96b9-43e7-945e-e29012ca8487" />

Наконец заполняем регистр адресации 

<img width="1076" height="417" alt="image" src="https://github.com/user-attachments/assets/96a9ee3d-7147-4241-a370-01949a37ff85" />

Все задания выполнены верно и в полном объеме
