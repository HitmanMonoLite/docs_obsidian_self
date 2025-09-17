**Необходимо:**
1. Зарегистрированный **домен** (например, `example.com`)
2. Доступ к **серверу с root-правами**
3. Сервер должен быть **доступен по 80 или 443 порту** извне

---
```
sudo apt update
```

Установка Certbot (Ubuntu/Debian) Nginx:
```
sudo apt install certbot python3-certbot-nginx
```

Для Apache:
```
sudo apt install certbot python3-certbot-apache
```

---
Для Nginx (автоматическая настройка):
```
sudo certbot --nginx
```

Для Apache:
```
sudo certbot --apache
```

- автоматически найдет конфиг
- попросит email
- предложит редирект с HTTP на HTTPS
- установит сертификат

---
Только получить сертификат (без автонастройки):
```
sudo certbot certonly --standalone -d example.com
```

После успешного выпуска:

|Файл|Назначение|
|---|---|
|`/etc/letsencrypt/live/example.com/fullchain.pem`|сертификат + цепочка|
|`/etc/letsencrypt/live/example.com/privkey.pem`|приватный ключ|
