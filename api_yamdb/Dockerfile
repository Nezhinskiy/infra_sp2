FROM python:3.7-slim

LABEL author='Nezhinsky'

WORKDIR /app

COPY requirements.txt .

RUN pip3 install --upgrade pip

RUN pip3 install --root-user-action=ignore -r /app/requirements.txt --no-cache-dir

COPY ./ .

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]
