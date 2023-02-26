# docker/backend/Dockerfile

FROM python:3.11.2-alpine

WORKDIR /app

ENV PIP_DISABLE_PIP_VERSION_CHECK 1
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

ADD ./backend/requirements.txt /app/backend/

RUN pip install --upgrade pip
RUN pip install gunicorn
RUN pip install -r backend/requirements.txt

ADD ./docker /app/docker
ADD ./backend /app/backend

RUN chmod +x /app/docker/backend/wsgi-entrypoint.sh


