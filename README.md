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
2. Response Code: 201 OK (POST)
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
