FROM python:3.7-slim

LABEL author='Nezhinsky'

WORKDIR /app

COPY requirements.txt .

RUN pip install --upgrade pip

RUN pip install --root-user-action=ignore -r /app/requirements.txt --no-cache-dir

COPY ./ .

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]
