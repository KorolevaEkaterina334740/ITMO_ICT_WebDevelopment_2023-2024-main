# Задание №4

???+ question "Задание"

    Реализовать двухпользовательский или многопользовательский чат. Реализация
    многопользовательского чата позволяет получить максимальное количество
    баллов.

    Реализовать с помощью протокола TCP – 100% баллов, с помощью UDP – 80%.  
    Обязательно использовать библиотеку `threading`.

    Для реализации с помощью UDP, `threading` использовать для получения
    сообщений у клиента.  
    Для применения с TCP необходимо запускать клиентские подключения И прием
    и отправку сообщений всем юзерам на сервере в потоках.  
    Не забудьте сохранять юзеров, чтобы потом отправлять им сообщения.

=== "Сервер"

    ```Python title="server.py"
    --8<-- "laboratory_work_1/4/server.py"
    ```
    

    Для реализации многопользовательского чата нам понадобится 
    библиотека threading. 
    В рамках данного задания сервер будет работать по принципу широкого вещания:
    при получении сообщения от подключенного пользователя, 
    сервер ретранслирует его всем остальным подключенным пользователям. 
    
    

=== "Клиент"

    ```Python title="client.py"
    --8<-- "laboratory_work_1/4/client.py"
    ```

    В реализации клиента при подключении к серверу мы запускаем процесс авторизации. 
    После авторизации, запускается бесконечный цикл, в котором клиенту предлагается ввести сообщение. 
    После ввода сообщения, благодаря серверу, оно отобразится у всех
    подключенных клиентов. 

    