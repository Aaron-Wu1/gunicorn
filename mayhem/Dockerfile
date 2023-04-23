FROM python:3.11.0-slim-buster as development
WORKDIR /app/
# COPY requirements.txt ./
RUN pip3 install --upgrade pip
RUN pip3 install gunicorn
# ENV FLASK_DEBUG=0
COPY . ./
EXPOSE 8000
CMD ["gunicorn", "-b", ":8000", "gunicorn.app:wsgiapp.py"]



# FROM python:3.11.0-slim-buster as builder

# # set work directory
# WORKDIR /usr/src/app

# # set environment variables
# ENV PYTHONDONTWRITEBYTECODE 1
# ENV PYTHONUNBUFFERED 1

# # install system dependencies
# RUN apt-get update && \
#     apt-get install -y --no-install-recommends gcc


# # install python dependencies
# COPY requirements.txt ./
# RUN pip wheel --no-cache-dir --no-deps --wheel-dir /usr/src/app/wheels -r requirements.txt

# RUN pip install -r requirements.txt

# FROM python:3.11.0-slim-buster as production

# # create directory for the app user
# RUN mkdir -p /home/app

# # create the app user
# RUN addgroup --system app && adduser --system --group app

# # create the appropriate directories
# ENV HOME=/home/app
# ENV APP_HOME=/home/app/web
# RUN mkdir $APP_HOME
# WORKDIR $APP_HOME

# # install dependencies
# RUN apt-get update && apt-get install -y --no-install-recommends netcat
# COPY --from=builder /usr/src/app/wheels /wheels
# COPY --from=builder /usr/src/app/requirements.txt .
# RUN pip install --upgrade pip
# RUN pip install --no-cache /wheels/*

# # copy project
# COPY . $APP_HOME

# # chown all the files to the app user
# RUN chown -R app:app $APP_HOME

# # change to the app user
# USER app
# WORKDIR /home/app/
# CMD ["gunicorn", "-b", "127.0.0.1:8000", "web.app:app"]



