FROM sanicframework/sanic:20.12

ENV PYTHONUNBUFFERED True

ENV APP_HOME /app
WORKDIR $APP_HOME

COPY [".", "./"]

RUN pip install --upgrade pip && \
    pip install -U sanic-cors configargparse configparser gunicorn requests websockets==8.1 && \
    pip install -r requirements.txt --user
    

CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 --timeout 0 --worker-class sanic.worker.GunicornWorker

ENTRYPOINT ["python3", "ark.py"]
