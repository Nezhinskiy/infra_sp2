FROM python:3.7-slim

RUN mkdir /app

COPY api_yamdb/requirements.txt /app

RUN python -m venv /opt/venv

ENV PATH="/opt/venv/bin:$PATH"

RUN pip install --upgrade pip

RUN pip install -r /app/requirements.txt --no-cache-dir

COPY api_yamdb /app
 
WORKDIR /app

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]
