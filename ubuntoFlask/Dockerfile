FROM ubuntu
WORKDIR /

ARG settScript="settScript.sh"

COPY ./data/$settScript .

RUN apt-get update && chmod +x $settScript && apt-get install sudo && sudo ./$settScript && sudo rm ./$settScript

COPY ./data/hello.py .
ENTRYPOINT python hello.py
