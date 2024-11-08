# Spring Micro Demo

Это учебное приложение, использующее Spring Boot с Eureka Server, Eureka Clients и API Gateway. Приложение демонстрирует работу микросервисной архитектуры с использованием Netflix Eureka для обнаружения сервисов.

## Содержание

- [Требования](#требования)
- [Запуск приложения](#запуск-приложения)
- [Проверка работоспособности](#проверка-работоспособности)
- [Лицензия](#лицензия)

## Требования

- Java 17 или выше
- Gradle 8.5 или выше
- IntelliJ IDEA или другая IDE для работы с Java

## Запуск приложения

Для запуска приложения выполните следующие шаги:

1. **Запустите Eureka Server**:
    - Во вкладке Services в IntelliJ IDEA запустите `EurekaServerApplication`.

2. **Запустите все клиенты**:
    - Запустите `EurekaClientApplication-inst1`, затем `EurekaClientApplication-inst2` (или другие экземпляры, если они есть).

3. **Запустите API Gateway**:
    - Запустите `ApiGatewayApplication`.

4. **Проверьте регистрацию приложений**:
    - В браузере в адресной строке введите:
      ```
      http://localhost:8761/
      ```
    - Вы должны увидеть зарегистрированные приложения.

5. **Проверьте работоспособность приложений**:
    - Для проверки работы API Gateway выполните следующие запросы:
        - Для получения случайного номера:
          ```
          http://localhost:8765/main/test
          ```
          Должен выдать номер, состоящий из букв и цифр.

        - Для получения имени:
          ```
          http://localhost:8765/new/name
          ```
          Должен выдать "Masha". Если по этому запросу ничего не выдает, проверьте, возможно, вы не запустили `EurekaClient2Application`.