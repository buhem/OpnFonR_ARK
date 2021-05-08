FROM dhlabbasel/ark-resolver

ENV PYTHONUNBUFFERED True

COPY [".", "./"]


RUN pip install --upgrade pip && \
    pip install -U sanic-cors sanic aiohttp aiofiles aiodns argparse configparser Flask gunicorn && \
    pip install -r /requirements.txt --user


COPY [".", "./app"]

WORKDIR /app

ENTRYPOINT ["python", "./ark.py"]
CMD exec gunicorn --bind :$PORT --workers 1 --threads 8 --timeout 0 main:app
