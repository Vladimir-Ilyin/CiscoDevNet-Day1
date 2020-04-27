DevNet Марафон день 1
=======================

За основу взят скрипт Оксаны https://github.com/presidentoksana/devnet_marathon

Скрипт адаптирован для исполнения в среде Windows

В скрипте добавлены функции

```bash
    get_version(connection, hostname)
    # При успехе возвращает словарь с номером версии ПО, наименованием ПО и тип ПО NPE/PE
    # иначе возвращает False

    get_platform(connection, hostname)
    # При успехе возвращает словарь с типом платформы
    # иначе возвращает False

    get_cdp(connection, hostname)
    # При успехе возвращает словарь со статусом протокола CDP и количеством обнаруженных пиров соседей
    # иначе возвращает False

    set_config(connection, hostname)
    # При успехе возвращает статус NTP:
    #   NTP is sync     - сервер доступен, конфигурация применена, часы синхронизированы
    #   NTP not sync    - сервер доступен, конфигурация применена, часы не синхронизированы
    #   NTP unavaible   - сервер NTP недоступен, конфигурация не применялась
    # иначе возвращает False

    get_config_commands_from_file(config_commands_file)
    # Вспомогательная функция для чтения файла с конфигурационными командами
    # в функции дополнительно выполняется подстановка IP адреса NTP в команду конфигурации
```