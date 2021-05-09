#FROM dhlabbasel/ark-resolver
#FROM python:3.9-slim
FROM sanicframework/sanic:20.12

ENV PYTHONUNBUFFERED True

ENV APP_HOME /app
WORKDIR $APP_HOME

COPY [".", "./"]

#sanic Flask

#change argparse by configargparse
RUN pip install --upgrade pip && \
    pip install -U sanic-cors configargparse configparser gunicorn requests websockets && \
    pip install -r requirements.txt --user
    

#aiohttp aiofiles aiodns
#COPY [".", "./app"]

#WORKDIR /app

#ENTRYPOINT ["python", "./app/ark.py"]

#EXPOSE 8080

#ENTRYPOINT ["python3", "ark.py"]


#CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 --timeout 0 'ark:main()'

CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 --timeout 0 ark:main --worker-class sanic.worker.GunicornWorker

#error
#CMD exec uwsgi --http :$PORT --workers 1 --threads 8 --timeout 0 --wsgi-file ark.py --callable main
