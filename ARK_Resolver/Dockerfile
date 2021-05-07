FROM dhlabbasel/ark-resolver


COPY [".", "./"]


RUN pip install --upgrade pip && \
    pip install -U sanic-cors sanic aiohttp aiofiles aiodns argparse configparser io hashlib hmac urllib string re && \
    pip install -r /requirements.txt --user


COPY [".", "./app"]

WORKDIR /app

ENTRYPOINT ["python", "./ark.py"]
