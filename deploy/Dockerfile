FROM python:3.8-buster

WORKDIR /code

COPY . .

RUN sed -i "s@http://deb.debian.org@http://mirrors.aliyun.com@g" /etc/apt/sources.list \
    && apt-get update \
    && pip install -i https://mirrors.aliyun.com/pypi/simple/ -r requirements.txt

CMD ["uvicorn", "src.main:app", "--host", "0.0.0.0", "--port", "8181"]
#CMD ["uvicorn", "src.main:app"]


# docker run --name chia_signature -p 8181:8181 powduck/chia_signature:v1