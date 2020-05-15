## Создание backup
- Переходим в папку `docker_volume_backup`
- Заранее узнаем имя нужного контейнера `docker ps` - если запушен или `docker ps -a` - если не запушен
- `docker exec -it [NAMES CONTAINER] bash`

### simple_backup_volume (не зашифрованная)
- В корне запускаем `./simple_backup_volume.sh [NAMES_CONTAINER] [Путь копируемой директории]` (пример `./simple_backup_volume.sh owncloud_db /var/lib/mysql`, `./simple_backup_volume.sh owncloud_site /mnt/data`)

### encrypted_backup_volume.sh (зашифрованная)

### encrypted_backup_volume.sh (зашифрованная, выгрузка на Amazon)

____

## Восстановление backup
- Переходим в папку `backups`
- Выполняем `./restore_volume.sh [NAMES_CONTAINER] [Нужный backup]` (Проделываем для всех нужных)
- В папке проекта делаем перезапуск `docker-compose restart`