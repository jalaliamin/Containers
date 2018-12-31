FROM ubuntu
WORKDIR /


ARG settScript="settScript.sh"

COPY ./data/$settScript .

RUN chmod +x $settScript
RUN ./$settScript
RUN rm ./$settScript


COPY ./data/hello.py .
ENTRYPOINT python hello.py
