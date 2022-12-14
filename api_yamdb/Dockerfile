FROM python:3.7-slim

WORKDIR /app

COPY api_yamdb/requirements.txt /app

RUN python -m venv /opt/venv

ENV PATH="/opt/venv/bin:$PATH"

RUN pip3 install --upgrade pip

RUN pip3 install --root-user-action=ignore -r /app/requirements.txt --no-cache-dir

COPY api_yamdb/ /app

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]
