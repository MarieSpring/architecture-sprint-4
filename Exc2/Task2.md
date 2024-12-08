# Выбор и настройка мониторинга в системе

## Раздел «Мотивация». 
Мониторинг позволит предотвратить неполадки в системе до возникновения проблем.
Так же мониторинг позволит оптимизировать использование ресурсов, поодсветить в какой точке системы требуется увеличение ресурсов, а в какой можно сократить их использование.
Благодаря мотинотингу есть возможность оператично реагировть на сбои и устранять их до причинения серьёзного ущерба компании. 

## Раздел «Выбор подхода к мониторингу». 
«Четыре золотых сигнала» для Shop API, CRM API, MES API. Он позволяет заметить аномалии в работе заранее и быстро среагировать на ситуацию. В случае компании это кейсы с неполученными вовремя заказами.

RED для выявления проблем с заказами, которые выполняются дольше обычного, на уровне БД и брокера RabbitMq.

## Опишите, какие метрики и в каких частях системы вы будете отслеживать.

1. Number of requests (RPS) для API:
- Number of requests (RPS) for internet shop API
- Number of requests (RPS) for CRM API
- Number of requests (RPS) for MES API
- Number of requests (RPS) per user for internet shop API
- Number of requests (RPS) per user for CRM API
- Number of requests (RPS) per user for MES API
 Данные метрики отражают  общее число запросов в определённом диапазоне времени. Позволит отслеживать рост или снижение трафика. 
Добавить ярлыки Endpoint и ResponseCode.

2. Response time (latency):
- Response time (latency) for shop API
- Response time (latency) for CRM API
- Response time (latency) for MES API
Метрика отражает времят отклика системы. 
Добавить ярлыки Endpoint и ResponseCode.

3. Number of HTTP 500:
- Number of HTTP 500 for shop API
- Number of HTTP 500 for CRM API
- Number of HTTP 500 for MES API
- Number of HTTP 500 for shop API
Метрика позволит отслеживать критические серверные ошибки.
Добавить ярлыки Endpoint и RequestPath.

4. CPU %:
- CPU % for shop API
- CPU % for CRM API
- CPU % for MES API
Метрика позволит отслеживать использование ресурсов.
Добавить ярлыки Instance сервера и environment типа окружения (dev, release, prod).

5. Number of dead-letter-exchange (DLX) letters in RabbitMQ
Метрика отражает количество проходов сообщения через обменник недоставленных сообщений. Поможет выявить проблемы с производительностью или конфигурацией брокера.
Добавить ярлык reason причина попадания в DLX.

6. Number of message in flight in RabbitMQ
Метрика отражает количество сообщений в полёте (в процессе передачи между брокером и потребителем, но ещё не подтверждённых потребителем). 

7. Number of connections:
- Number of connections for shop db instance
- Number of connections for MES db instance
Метрика отражает количество соединений для экземпляра базы данных.
Добавить ярлык instance базы данных.

8. Memory Utilisation:
- Memory Utilisation for shop API
- Memory Utilisation for CRM API
- Memory Utilisation for MES API
- Memory Utilisation for shop db instance
- Memory Utilisation for MES db instance
Метрика позволяет отслеживать использование памяти в экземпляре базы данных.
Добавить ярлык instance базы данных.

9. Size of db instance:
- Size of shop db instance
- Size of MES db instance
Метрика отражает позволяет отслеживать размеры базы данных.
Добавить ярлык instance базы данных.

## Раздел «План действий».
- установить и сконфигурировать Prometheus, проверить что метрики собираются корректно
- установить и сконфигурировать Grafana для визуализации данных, полученных от Prometheus, создать дашборды для визуализации требуемых метрик, проверить что данные визуализируются корретно
- настроить алерты и сконфигурировать настройки для отправки уведомлений в предпочитаемые каналы связи (например, Telegram), проверить корректно работающие алерты и уведомления о них.

