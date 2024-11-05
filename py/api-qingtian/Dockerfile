FROM python:3.11.2


RUN apt-get update && \
    apt-get install -y redis-server


EXPOSE 6379
WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["sh", "-c", "redis-server /etc/redis/redis.conf --appendonly yes & python app.py"]
