FROM mongo

RUN apt-get -qq update && apt-get -qq install -y --no-install-recommends \
    nano

COPY /driver_db_dump.json /driver_db_dump.json

CMD mongoimport --host mongodb --db clinical_reporting --collection biograph_genes --jsonArray --file /driver_db_dump.json --drop
