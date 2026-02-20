# Відповідь - Beet Seed
Навантажувальне тестування API JSONPlaceholder за допомогою JMeter.

Назва - OSCAR_Test Plan, містить запити GET, POST, PUT, PATCH, DELETE до сервісу JSONPlaceholder.

OSCAR_Thread_Group (параметри):
1. Number of Threads (users): 1
2. Ramp-up period (seconds): 10
3. Loop Count: 3

HTTP Request Defaults (параметри):
1. Protocol: https
2. Server Name: jsonplaceholder.typicode.com

HTTP Header Manager (параметри):
1. Content-Type: application/json; charset=UTF-8

Застосовані ассерти:
1. Response Code: 200 OK (GET, PUT, PATCH, DELETE)
2. Response Code: 201 Created (POST)
3. JSON Assertion: перевірка наявності поля ID, JSON Path - $.id (GET, POST, PUT, PATCH)
4. Text response: перевірка порожнього поля {} (DELETE)
5. Size Assertion: перевірка розміру даних відповіді > 50 байт (GET, POST, PUT, PATCH, DELETE)

Результати тестування (OSCAR_Summary Report):
1. Кількість запитів (Total): 15
2. Успішність (Error %): 0.00
2. Середній час відповіді (Average/ms): 267 
3. Пропускна здатність (Throughput/sec): 3.7

Висновки:
1. Тестування продуктивності API JSONPlaceholder підтвердило коректну роботу використанних методів. 
2. Застосовані ассерти підтвердили правильну обробку запитів сервером, який повернув очікуванні статус коди, структуру JSON та розмір даних.

Скріншоти: 
<img width="1494" height="970" alt="Дерево результатів" src="https://github.com/user-attachments/assets/f9f108d3-622a-4be8-b548-4192694a0051" />
<img width="1920" height="963" alt="OSCAR_Summary Report" src="https://github.com/user-attachments/assets/bf6e618a-9cd3-44b6-b6a4-124c906dac6d" />


# Відповідь - Beet Sprout 
Навантажувальне тестування API JSONPlaceholder за допомогою JMeter.

Назва - OSCAR_Stress_Test_Plan, містить запити GET, POST, PUT, PATCH, DELETE до сервісу JSONPlaceholder.

OSCAR_Thread_Group (параметри):
1. Number of Threads (users): 501
2. Ramp-up period (seconds): 60
3. Loop Count: Infinite; Same user on each iteration; duration - 120 sec

HTTP Request Defaults (параметри):
1. Protocol: https
2. Server Name: jsonplaceholder.typicode.com

HTTP Header Manager (параметри):
1. Content-Type: application/json; charset=UTF-8

Застосовані ассерти:
1. Response Code: 200 OK (GET, PUT, PATCH, DELETE)
2. Response Code: 201 Created (POST)
3. JSON Assertion: перевірка наявності поля ID, JSON Path - $.id (GET, POST, PUT, PATCH)
4. Text response: перевірка порожнього поля {} (DELETE)
5. Size Assertion: перевірка розміру даних відповіді > 50 байт (GET, POST, PUT, PATCH, DELETE)

Результати тестування (OSCAR_Summary Report)
Навантаження у 501 (users) показало, що сервер відповідає з помилкою, а саме у запиті OSCAR_HTTP Request POST
Вихідні дані:
1. Кількість запитів (POST): 45905 (total 228841)
2. Успішність (POST/Error): 0.01% (Other Methods/Error 0.00%)
2. Середній час відповіді (POST/Average): 222ms (total 197ms) 
3. Пропускна здатність (POST/Throughput): 382.3sec (total 1902.2sec)

Висновки:
При тестування продуктивності API JSONPlaceholder виявлено точку, де відбувається перенавантаження серверу, це 501 users. Для методу POST ця кількість була достатньою, щоб API серверу видало помилку 0.01%, але всі інші запити показали значення 0.00%.  

Скріншоти: <img width="1920" height="568" alt="StressTest 501" src="https://github.com/user-attachments/assets/952a799d-9c54-4cd0-b4f0-11a61fffcc5e" />
