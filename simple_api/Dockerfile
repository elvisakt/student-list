FROM python:2.7-stretch

LABEL maintainer="226588"

COPY student_age.py /

RUN mkdir /data

RUN apt-get update -y && apt-get install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y

RUN pip install flask flask_httpauth flask_simpleldap python-dotenv

VOLUME /data

ADD student_age.json /data/student_age.json

EXPOSE 5000

CMD [ "python", "./student_age.py" ]

RUN tail -f /dev/null
