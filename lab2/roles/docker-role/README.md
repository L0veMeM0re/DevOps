Docker Role
=========

Данная роль предназначена для установки Docker и его зависимостей на серверах с использованием Ansible. Она автоматически устанавливает Docker CE, настраивает автозапуск сервиса и добавляет текущего пользователя в группу Docker для работы без прав `sudo`.

Requirements
------------

- **Операционная система**: Ubuntu (тестировалась на последних версиях LTS).
- **Ansible**: версия 2.9 и выше.
- Необходимы права `root` или эквивалентные для установки пакетов и настройки системы.

Role Variables
--------------

- `docker_packages`: список пакетов, необходимых для установки Docker. Значение по умолчанию:

  docker_packages:
    - apt-transport-https
    - ca-certificates
    - curl
    - software-properties-common
    - docker-ce
  
- `docker_repository`: URL репозитория Docker для добавления в систему. Значение по умолчанию:

      "deb [arch=amd64](https://download.docker.com/linux/ubuntu) {{ ansible_distribution_release }} stable"  


-`docker_user`: имя пользователя, который будет добавлен в группу docker. Значение по умолчанию:

docker_user: "{{ ansible_user }}"



Dependencies
------------

Данная роль не имеет внешних зависимостей и не требует других ролей для работы.


License
-------

BSD

Роль создана в рамках лабораторной работы по Ansible. Для вопросов и предложений можно связаться через GitLab.
------------------




