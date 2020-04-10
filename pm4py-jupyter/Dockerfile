FROM python:3.7-slim

RUN apt-get update && \
	apt-get -y install wget && \
	apt-get -y install sudo && \
#	sudo apt-get -y install gcc gcc- g++ && \
	sudo apt -y install graphviz && \
	sudo apt -y install libblas-dev && \
	sudo apt -y install liblapack-dev && \
	sudo apt -y install libsuitesparse-dev && \
	sudo apt-get -y install python3-tk && \
	sudo pip install pm4py jupyter && \
	jupyter notebook --generate-config && \
	echo "c.NotebookApp.ip = '0.0.0.0'" >> /root/.jupyter/jupyter_notebook_config.py && \
	echo "c.NotebookApp.port = 5000" >> /root/.jupyter/jupyter_notebook_config.py && \
	echo "c.NotebookApp.allow_root = True" >> /root/.jupyter/jupyter_notebook_config.py && \
	apt-get -y autoremove && \
	apt-get -y clean && \
	rm -r /root/.cache/pip

ENTRYPOINT jupyter notebook