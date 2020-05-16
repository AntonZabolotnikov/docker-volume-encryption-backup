## docker_volume_backup
Бэкопирование docker контейнеров (README.md в папке)

## encrypt_files
Файлы:
- init.sh - генерация ключей
- encrypt.sh - шифрует файлы
- decript.sh - расшифровщик

Шифрование:
- Переходим в папку `encrypt_files`
- Запускаем `init.sh` для создания ключей (достаточно одного раза)
- Появится папка `keys` с ключами, папки `encrypt` и `decrypt`
- Запускаем `./encrypt.sh [source file path] [public key file path]` для шифрования (пример `./encrypt.sh test.txt keys/pem/id_rsa.pub.pem`)
- В папке `encrypt` получаем зашифрованный файл с ключом 

Дешифрование:
- Запускаем `./decrypt.sh [file] [encrypted key] [private key] [output file]` (пример: `./decrypt.sh encrypt/test.txt.enc encrypt/test.txt.key.bin.enc keys/pem/id_rsa.pem test.txt`)
- В папке `decrypt` появится расшифрованный файл