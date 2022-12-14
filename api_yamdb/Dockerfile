FROM python:3.7-slim

LABEL author='Nezhinsky'

WORKDIR /app

COPY requirements.txt /app

RUN python -m venv /opt/venv

ENV PATH="/opt/venv/bin:$PATH"

RUN pip install --upgrade pip

RUN pip install --root-user-action=ignore -r /app/requirements.txt --no-cache-dir

COPY ./ /app

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]
