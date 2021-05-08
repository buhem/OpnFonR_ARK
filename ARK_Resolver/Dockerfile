FROM dhlabbasel/ark-resolver

ENV PYTHONUNBUFFERED True

ENV APP_HOME /app
WORKDIR $APP_HOME

COPY [".", "./"]


RUN pip install --upgrade pip && \
    pip install -U sanic-cors sanic argparse configparser Flask gunicorn && \
    pip install -r /requirements.txt --user

#aiohttp aiofiles aiodns
#COPY [".", "./app"]

#WORKDIR /app

ENTRYPOINT ["python", "./app/ark.py"]
#CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 --timeout 0 main:app
