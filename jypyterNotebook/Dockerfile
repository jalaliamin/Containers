FROM python:3.7-slim

RUN pip install jupyter numpy scipy pandas sklearn matplotlib && \
	jupyter notebook --generate-config && \
	echo "c.NotebookApp.ip = '0.0.0.0'" >> /root/.jupyter/jupyter_notebook_config.py && \
	echo "c.NotebookApp.port = 5000" >> /root/.jupyter/jupyter_notebook_config.py && \
	echo "c.NotebookApp.allow_root = True" >> /root/.jupyter/jupyter_notebook_config.py && \
	apt-get -y autoremove && \
	apt-get -y clean && \
	rm -r /root/.cache/pip

ENTRYPOINT jupyter notebook

