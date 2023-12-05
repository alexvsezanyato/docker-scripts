Команды выполняются из корня проекта, если не описано иное.
Процесс установки описан для использования в демонстрационном режиме.

```bash
cp .env.docker site/.env
./container build
./container up
```

```bash
docker exec -it coal-php-fpm bash # (вход в контейнер с php)
composer install
php artisan key:generate # Если connection refused, то ждем, контейер mysql с БД инициализируется
php artisan migrate
php artisan db:seed
exit # (выход из контейнера)
```

```bash
./container node # (вход в контейнер с нодой)
- npm install
- npx mix
```

Читаем что ответила команда, если ошибок нет, то получаем список скомпилированных фалов или сообщение что дополнительные зависимости установлены, надо запустить команду ещё раз.

```
        Additional dependencies must be installed. This will only take a moment.
        
        Running: npm install @babel/preset-react --save-dev --legacy-peer-deps
        
        Finished. Please run Mix again.
```

Если получили такое сообщение, ещё раз вводим ```npx mix```.
Теперь должны получить список скомпилированных файлов.

Уже можно открыть сайт, по умолчанию доступен на http://localhost:8800/ (порт указан в ответе команды ./container up).

Для отправки почты надо сконфигурировать .env
