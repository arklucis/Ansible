# Домашнее задание к занятию 3 «Использование Ansible»

## Подготовка к выполнению

1. Подготовьте в Yandex Cloud три хоста: для `clickhouse`, для `vector` и для `lighthouse`.
2. Репозиторий LightHouse находится [по ссылке](https://github.com/VKCOM/lighthouse).

## Основная часть

1. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает LightHouse.
2. При создании tasks рекомендую использовать модули: `get_url`, `template`, `yum`, `apt`.
3. Tasks должны: скачать статику LightHouse, установить Nginx или любой другой веб-сервер, настроить его конфиг для открытия LightHouse, запустить веб-сервер.
4. Подготовьте свой inventory-файл `prod.yml`.
5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
![Снимок](https://github.com/arklucis/Ansible/assets/154414081/e1940b9c-4ce3-4fa7-b61c-c4025b647dbb)

6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
![Снимок1](https://github.com/arklucis/Ansible/assets/154414081/1cddf657-366f-423c-a90d-c52f5f2e0da0)

7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
![Снимок2](https://github.com/arklucis/Ansible/assets/154414081/011efa08-fb6e-4e0d-9723-4ffafe4a5f74)
![Снимок3](https://github.com/arklucis/Ansible/assets/154414081/af753db4-895c-443e-ab6a-1d5bad324249)
![Снимок4](https://github.com/arklucis/Ansible/assets/154414081/6249ba61-6693-4733-9686-0ae625af1faf)

8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
9. Подготовьте README.md-файл по своему playbook. В нём должно быть описано: что делает playbook, какие у него есть параметры и теги.
10. Готовый playbook выложите в свой репозиторий, поставьте тег `08-ansible-03-yandex` на фиксирующий коммит, в ответ предоставьте ссылку на него.

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
