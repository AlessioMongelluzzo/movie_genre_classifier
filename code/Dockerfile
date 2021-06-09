FROM python:3.8

WORKDIR /app
RUN pip install tensorflow numpy gunicorn flask

ADD ./models ./models
ADD ./aux ./aux
ADD gen_clf_server.py gen_clf_server.py

EXPOSE 5000
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "gen_clf_server:app"]