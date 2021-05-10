#import the python image

FROM python:2.7-stretch

MAINTAINER FontenetteClement


#Copy the the source code of API at the ROOT

COPY student_age.py /

#Run cmd on the container

RUN apt-get update -y && apt-get install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y

RUN pip install flask flask_httpauth flask_simpleldap python-dotenv

#Create the Persistent data Volume

VOLUME ["/data"]

#Copy the Json api in the data folder

COPY student_age.json /data/

#Expose the port 5000

EXPOSE 5000

#Run CMD after the Build

CMD [ "python", "./student_age.py" ]
