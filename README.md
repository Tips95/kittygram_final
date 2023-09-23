Kittygram
Kittygram - это социальная сеть для обмена фотографиями любимых питомцев.

Стек
Django==3.2.3
djangorestframework==3.12.4
django-cors-headers==3.13.0
djoser==2.1.0
webcolors==1.11.1
psycopg2-binary==2.9.3
Pillow==9.0.0
pytest==6.2.4
pytest-django==4.4.0
pytest-pythonpath==0.7.3
PyYAML==6.0
python-dotenv==1.0.0
Установка и запуск
Клонирование кода приложения с GitHub:

Выполните команду git clone, замените SSH-ссылка на фактическую SSH-ссылку на ваш репозиторий на GitHub.
git clone SSH-ссылка

Создание файла .env.example:
Создайте файл с именем .env.example, и внутри него перечислите все переменные окружения, которые необходимы для вашего проекта. Вам нужно будет заполнить их данными.
POSTGRES_DB=
POSTGRES_USER=
POSTGRES_PASSWORD=

Проверка созданных образов:
Выполните команду, чтобы увидеть список созданных Docker-образов.
docker image ls
Запуск Docker Compose на компьютере:

Запустите приложение с помощью Docker Compose, используя указанный файл конфигурации.
docker compose -f docker-compose.production.yml up

Сборка статики:
Выполните следующие команды, чтобы собрать статические файлы и скопировать их в соответствующую директорию:
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/

Применение миграций:
Запустите миграции базы данных для вашего приложения:
docker compose -f docker-compose.production.yml exec backend python manage.py migrate

Автор
Магомед Юнусов