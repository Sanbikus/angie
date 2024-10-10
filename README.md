0.В лабораторной используется Ubuntu 22.04 LTS
1.Получить сертификат для доступа к закрытому репозиторию angie-repo.crt , angie-repo.key
2.Создать рекомендуемый путь для сертификатов sudo mkdir -p /etc/ssl/angie/
3.положить файлы .crt и .key в рекомендуемый путь /etc/ssl/angie/
4.Обновить пакетную базу sudo apt-get update
5.установить требуемые пакеты для ubuntu sudo apt-get install -y apt-transport-https lsb-release \
               ca-certificates curl gnupg2
6.Скачайте открытый ключ репозитория Angie PRO для проверки подлинности пакетов  sudo curl -o /etc/apt/trusted.gpg.d/angie-signing.gpg \
            https://angie.software/keys/angie-signing.gpg

7.Подключение закрытого репозитория 
echo "deb https://download.angie.software/angie-pro/$(. /etc/os-release && echo "$ID/$VERSION_ID $VERSION_CODENAME") main" \
    | sudo tee /etc/apt/sources.list.d/angie.list > /dev/null

8. Выполняется установка пакета angie pro  sudo apt-get install -y angie-pro
9.Установка дополнительных пакетов sudo apt-get install angie-pro-console-light
9.1 sudo apt-get install angie-pro-module-auth-jwt
9.2 sudo apt-get install angie-pro-module-auth-ldap
