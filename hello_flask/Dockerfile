

#STAGE 1:BUILD STAGE
FROM python:3.8-slim as build

WORKDIR /app

RUN  apt-get update && apt-get install -y \
    gcc \
    python3-dev \
    libmariadb-dev \
    pkg-config

    COPY . .

    RUN pip install flask mysqlclient

#STAGE 2: PRODUCTION STAGE 

FROM python:3.8-slim

WORKDIR /app

COPY --from=Build /app /app

EXPOSE 5000

CMD ["python", "app.py" ] 

