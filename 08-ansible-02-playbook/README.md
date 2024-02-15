
# Playbook установки ClickHouse и Vector

Этот Ansible playbook автоматизирует установку и настройку ClickHouse и Vector на заданных хостах. Playbook разработан с учетом модульности и настраиваемости для облегчения процесса настройки.

## Обзор Playbook

Playbook состоит из двух основных разделов:

### 1. Установка ClickHouse

- Загружает и устанавливает пакеты ClickHouse на указанных хостах.
- Обрабатывает возможные сбои, пытаясь загрузить альтернативные пакеты в случае сбоя.
- Настраивает базу данных ClickHouse и перезапускает сервис.

### 2. Установка Vector

- Загружает и устанавливает пакеты Vector на указанных хостах.
- Настраивает Vector с использованием стандартного шаблона, принимая логи из ClickHouse.
- Гарантирует установку службы Vector, запускает службу и перезапускает ее при необходимости.

## Параметры Playbook

Playbook можно настроить, используя следующие параметры:

- **clickhouse_version:** Указывает версию устанавливаемых пакетов ClickHouse.
- **clickhouse_packages:** Список пакетов ClickHouse для установки.
- **vector_version:** Указывает версию устанавливаемых пакетов Vector.

## Теги

Playbook включает следующие теги для выборочного выполнения:

- **clickhouse:** Выполняет задачи, связанные с установкой ClickHouse.
- **vector:** Выполняет задачи, связанные с установкой Vector.

## Использование

Чтобы выполнить playbook, используйте следующую команду:

```bash
ansible-playbook -i inventory/prod.yml site.yml

Чтобы выполнить только задачи, связанные с ClickHouse или Vector, используйте теги:
ansible-playbook -i inventory/prod.yml site.yml --tags clickhouse
ansible-playbook -i inventory/prod.yml site.yml --tags vector

```


## Скрины к ДЗ с 5-8

5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
![Снимок экрана от 2024-02-14 05-03-18](https://github.com/arklucis/mnt-homeworks/assets/154414081/cb656684-751c-443f-9e55-b266609db378)

6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
![Снимок экрана от 2024-02-14 05-05-40](https://github.com/arklucis/mnt-homeworks/assets/154414081/e1e18993-3d50-4a52-96ca-6738abed296b)

7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
![Снимок экрана от 2024-02-14 05-22-01](https://github.com/arklucis/mnt-homeworks/assets/154414081/4d158e59-40a0-41df-9554-a8778fd090fc)
![Снимок экрана от 2024-02-14 05-22-16](https://github.com/arklucis/mnt-homeworks/assets/154414081/c2402e62-3457-4225-b250-403ae99303dd)

9. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
![Снимок экрана от 2024-02-14 05-22-46](https://github.com/arklucis/mnt-homeworks/assets/154414081/b149db8f-6754-4f7b-a857-4d929c8d77d5)

10.Готовый playbook выложите в свой репозиторий, поставьте тег 08-ansible-02-playbook на фиксирующий коммит, в ответ предоставьте ссылку на него.
```
https://github.com/arklucis/mnt-homeworks/releases/tag/08-ansible-02-playbook
```
