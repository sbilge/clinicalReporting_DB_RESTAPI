FROM mongo

LABEL maintainer="sueruen@informatik.uni-tuebingen.de"

RUN apt-get -qq update && apt-get -qq install -y --no-install-recommends \
    nano

COPY /driver_db_dump.json /driver_db_dump.json

CMD  mongod --bind_ip localhost --fork --syslog /log && mongoimport --host localhost --db clinical_reporting --collection biograph_genes --jsonArray --file /driver_db_dump.json --drop
