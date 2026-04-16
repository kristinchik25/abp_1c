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
