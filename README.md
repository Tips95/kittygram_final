Kittygram
Cоциальная сеть для обмена фотографиями любимых питомцев.
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
Установка запуск
Клонирование кода приложения с GitHub.
git clone SSH-ссылка
Создать файл .env.example в котором перечислены все переменные окружения.
POSTGRES_DB=
POSTGRES_USER=
POSTGRES_PASSWORD=
Проверить созданные образы.
docker image ls
Запустить Docker Compose на компьютере.
docker compose -f docker-compose.production.yml up
Собрать статику.
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
Применить миграции.
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
Автор
Магомед Юнусов