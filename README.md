# Ansible playbook: nginx with PHP-FPM and Let's Encrypt

Ansible playbook для установки nginx с заменой стандартной конфигурации на преднастроенную конфигурацию php-fpm и автоматической установкой сертификата Let's Encrypt.

---

## Packages

- `nginx`
- `php-fpm`
- `certbot`
- `python3-certbot-nginx`

---

## Tree

```bash
ansible/
├── inventory/
│   ├── hosts.yml                # Хосты
│   └── group_vars/
│       └── webservers.yml       # Переменные для хостов
├── playbook/
│   ├── 01_check_connection.yml  # Проверка подключения
│   └── 02_nginx_install.yml     # Установка nginx
└── roles/
    └── nginx/
        ├── defaults/
        │   └── main.yml         # Значения по умолчанию
        ├── handlers/
        │   └── main.yml         # Перезапуск nginx
        ├── tasks/
        │   └── main.yml         # Установка и настройка
        ├── templates/
        │   └── nginx.conf.j2    # Шаблон nginx.conf
        └── vars/
            └── main.yml         # Переменные
```
