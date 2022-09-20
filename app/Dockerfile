FROM python:3.10.7-alpine

LABEL maintainer='look-in44@yandex.ru'

WORKDIR /usr/src/app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

COPY . .

RUN apk update && \
    apk add postgresql-dev \
    gcc \
    python3-dev \
    musl-dev && \
    pip install --upgrade pip && \
    pip install -r requirements.txt && \
    sed -i 's/\r$//g' /usr/src/app/entrypoint.sh && \
    chmod +x /usr/src/app/entrypoint.sh

ENTRYPOINT [ "/usr/src/app/entrypoint.sh" ]
