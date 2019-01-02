FROM python:3.7-slim
RUN pip install flask numpy pandas

# FROM ubuntu
# 
# WORKDIR /
# 
# ARG settScript="settScript.sh"
# 
# COPY ./data/$settScript .
# 
# RUN chmod +x $settScript && bash ./$settScript && rm ./$settScript

COPY ./data/hello.py .

ENTRYPOINT python hello.py
