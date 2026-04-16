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

Перейдем к параметру сеанса. 
