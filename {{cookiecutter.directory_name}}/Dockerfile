FROM python:{{cookiecutter.python_version}}

ENV TZ 'Asia/Shanghai'
ENV PYTHONUNBUFFERED '0'

WORKDIR /app

RUN set -ex && pip install pipenv --upgrade -i https://pypi.douban.com/simple/

COPY Pipfile Pipfile
COPY Pipfile.lock Pipfile.lock
RUN set -ex && pipenv install --deploy --system

COPY . /app

CMD ["python", "{{cookiecutter.file_name}}.py"]