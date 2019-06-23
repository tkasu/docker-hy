FROM ubuntu:16.04

RUN apt-get update && apt-get -y install curl

ENV WEBSITE=""

ENTRYPOINT ["echo", "Searching.."]
RUN ["sleep", "1"]
ENTRYPOINT curl http://$WEBSITE
