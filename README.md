# KUCVUC

В данном репозитории находятся два самбодуля:

1. eed-frontend (клиент)
2. eed-backend (сервер)

docker-compose.yml - файл docker-compose

### Настройка доступа к сайту 
На виртуальной машине нужно открыть порты 8080, 8083
https://cloud.ru/docs/applications/ug/topics/faq/administration__open-port.html

Также возможно потребуется открыть порты в группах безопасности

### Для поднятия контейнеров выполнить: 
```cmd
sudo docker-compose up -d
```


## Веб-сервер nginx 
В репозитории приложен конфигурационный файл для nginx 

```cmd
apt update
apt install nginx 
cp ./nginx.conf /etc/nginx/nginx.conf
sudo systemctl restart nginx
```

eed-frontend - <b>185.50.203.136:80/eed-frontend</b> <- proxy to -> <b>localhost:8080/eed-frontend</b>

eed-backend - <b>185.50.203.136:8000</b> <- proxy to -> <b>localhost:8083</b>

postgres - <b>185.50.203.136:5432</b> <- proxy to -> <b>localhost:5432</b>

После этого в браузере можно сайт можно будет открыть по ip 
http://185.50.203.136/eed-frontend#/

