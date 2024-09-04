FROM python:3.12.4

RUN pip install -U pip

RUN pip install pipenv

WORKDIR /app

COPY [ "Pipfile", "Pipfile.lock", "./"]

RUN pipenv install --system --deploy

COPY static /app/static/

COPY templates /app/templates/

COPY app.py /app/

EXPOSE 9696

CMD [ "gunicorn", "app:app", "-b", "0.0.0.0:9696", "-w", "2" ]