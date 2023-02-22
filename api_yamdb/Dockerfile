FROM python:3.7-slim
WORKDIR /app
COPY api_yamdb/requirements.txt /app
RUN pip install -r requirements.txt
COPY api_yamdb/ /app
CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]