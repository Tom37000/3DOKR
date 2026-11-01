FROM python:3.11-alpine

WORKDIR /usr/src/app

COPY requirements.txt .

RUN pip install -r requirements.txt

RUN adduser -D supinfo

USER supinfo

COPY --chown=supinfo:supinfo . .

EXPOSE 8080

CMD ["python", "app.py"]