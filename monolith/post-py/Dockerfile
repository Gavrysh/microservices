FROM python:3.6.0-alpine

ENV POST_DATABASE_HOST post_db
ENV POST_DATABASE posts
ENV APP_HOME /app

WORKDIR $APP_HOME

COPY requirements.txt $APP_HOME
RUN apk add --no-cache --virtual .build-deps build-base \
    && pip install --no-cache-dir -r $APP_HOME/requirements.txt \
    && apk del .build-deps

COPY . $APP_HOME

ENTRYPOINT ["python3", "post_app.py"]
