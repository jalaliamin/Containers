FROM ubuntu
WORKDIR /


ARG settScript="settScript.sh"

COPY ./data/$settScript .

RUN chmod +x $settScript && ./$settScript && rm ./$settScript


COPY ./data/hello.py .
ENTRYPOINT python hello.py
