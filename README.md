# Проект YaMDb

![example workflow](https://github.com/demarknn/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

## Адрес проекта

http://yamdb.demarknn.ru/api/v1/auth/signup/

http://yamdb.demarknn.ru/admin/

http://yamdb.demarknn.ru/redoc/


Проект YaMDb собирает отзывы (Review) пользователей на произведения (Titles). 
Произведения делятся на категории: «Книги», «Фильмы», «Музыка».
К проекту по адресу http://yamdb.demarknn.ru/redoc/ подключена документация API YaMDb. 
В ней описаны возможные запросы к API и структура ожидаемых ответов. 
Для каждого запроса указаны уровни прав доступа: пользовательские роли, которым разрешён запрос.


## Содержание файла .env

```
SECRET_KEY = '...'                            # Secret key Django
DB_ENGINE=django.db.backends.postgresql       # указываем, что работаем с postgresql
DB_NAME='...'                                 # имя базы данных
POSTGRES_USER='...'                           # логин для подключения к базе данных
POSTGRES_PASSWORD='...'                       # пароль для подключения к БД (установите свой)
DB_HOST=db                                    # название сервиса (контейнера)
DB_PORT=5432                                  # порт для подключения к БД 
```

Запустите docker-compose командой ```docker-compose up```. 
Команды внутри контейнеров выполняют посредством подкоманды ```docker-compose exec```
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input 
```

Вы можете импортировать и экспортировать данные в БД в формате json
```
docker-compose exec web python manage.py dumpdata > fixtures.json 
docker-compose exec web python manage.py loaddata db.json 
```

Создан мной в рамках курса Python разработчик плюс в Яндеск.Практикуме. 
Данный код распространяется по лицензии MIT. 

```
Copyright (c) 2022 Veselnikov Ivan

Данная лицензия разрешает, безвозмездно, лицам, получившим копию данного программного обеспечения и 
сопутствующей документации (в дальнейшем именуемыми "Программное Обеспечение"), 
использовать Программное Обеспечение без ограничений, включая неограниченное право на использование, 
копирование, изменение, объединение, публикацию, распространение, сублицензирование и/или продажу копий Программного Обеспечения, 
также как и лицам, которым предоставляется данное Программное Обеспечение, при соблюдении следующих условий:

Вышеупомянутый копирайт и данные условия должны быть включены во все копии или значимые части данного Программного Обеспечения.

ДАННОЕ ПРОГРАММНОЕ ОБЕСПЕЧЕНИЕ ПРЕДОСТАВЛЯЕТСЯ «КАК ЕСТЬ», БЕЗ ЛЮБОГО ВИДА ГАРАНТИЙ, ЯВНО ВЫРАЖЕННЫХ ИЛИ ПОДРАЗУМЕВАЕМЫХ, 
ВКЛЮЧАЯ, НО НЕ ОГРАНИЧИВАЯСЬ ГАРАНТИЯМИ ТОВАРНОЙ ПРИГОДНОСТИ, СООТВЕТСТВИЯ ПО ЕГО КОНКРЕТНОМУ НАЗНАЧЕНИЮ И НЕНАРУШЕНИЯ ПРАВ. 
НИ В КАКОМ СЛУЧАЕ АВТОРЫ ИЛИ ПРАВООБЛАДАТЕЛИ НЕ НЕСУТ ОТВЕТСТВЕННОСТИ ПО ИСКАМ О ВОЗМЕЩЕНИИ УЩЕРБА, УБЫТКОВ ИЛИ ДРУГИХ ТРЕБОВАНИЙ 
ПО ДЕЙСТВУЮЩИМ КОНТРАКТАМ, ДЕЛИКТАМ ИЛИ ИНОМУ, ВОЗНИКШИМ ИЗ, ИМЕЮЩИМ ПРИЧИНОЙ ИЛИ СВЯЗАННЫМ С ПРОГРАММНЫМ ОБЕСПЕЧЕНИЕМ ИЛИ 
ИСПОЛЬЗОВАНИЕМ ПРОГРАММНОГО ОБЕСПЕЧЕНИЯ ИЛИ ИНЫМИ ДЕЙСТВИЯМИ С ПРОГРАММНЫМ ОБЕСПЕЧЕНИЕМ.
```
