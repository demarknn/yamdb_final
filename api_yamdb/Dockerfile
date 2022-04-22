FROM python:3.7-slim

WORKDIR /app

COPY api_yamdb/requirements.txt api_yamdb/app/

RUN pip3 install -r api_yamdb/app/requirements.txt --no-cache-dir

COPY api_yamdb/ api_yamdb/app/

RUN cd api_yamdb/app/

CMD ["gunicorn", "api_yamdb.wsgi:app", "--bind", "0:5000" ] 
# CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:5000" ] 