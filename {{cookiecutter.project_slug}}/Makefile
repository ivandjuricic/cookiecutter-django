{% if cookiecutter.use_docker == 'y' %}PYTHON_COMMAND = docker-compose  -f -f local.yml run django python{% else %}PYTHON_COMMAND = python{% endif %}

runserver:
	{% if cookiecutter.use_docker == 'y' %}docker-compose -f local.yml up {% else %}python manage.py runserver{% endif %}

{% if cookiecutter.use_docker == 'y' %}build:
	docker-compose -f local.yml build

bash:
	docker-compose -f local.yml run django bash

down:
	docker-compose -f local.yml down

teardown:
	docker-compose -f local.yml down --remove-orphans --volumes
	docker-compose -f local.yml kill
	docker-compose -f local.yml rm -f -v{% endif %}

migrations:
	${PYTHON_COMMAND} manage.py makemigrations

migrate:
	${PYTHON_COMMAND} manage.py migrate ${APP} ${NUMBER}

createsuperuser:
	${PYTHON_COMMAND} manage.py createsuperuser

static:
	${PYTHON_COMMAND} manage.py collectstatic --no-input

makemessages:
	${PYTHON_COMMAND} manage.py makemessages ${LANGUAGES}

compilemessages:
	${PYTHON_COMMAND} manage.py compilemessages

shell:
	${PYTHON_COMMAND} manage.py shell

test:
	${PYTHON_COMMAND} manage.py test
