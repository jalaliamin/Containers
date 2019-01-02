FROM python:3.7-slim

RUN \
	pip install jupyter numpy scipy pandas sklearn matplotlib pyspark pandoc pyarrow findspark && \
	jupyter notebook --generate-config  && \
	echo "c.NotebookApp.ip = '0.0.0.0'" >> /root/.jupyter/jupyter_notebook_config.py  && \
	echo "c.NotebookApp.port = 5000" >> /root/.jupyter/jupyter_notebook_config.py  && \
	echo "c.NotebookApp.allow_root = True" >> /root/.jupyter/jupyter_notebook_config.py && \ 
	apt-get update && \
	apt-get install sudo && \
	sudo apt install openjdk-8-jdk -y && \
	echo "JAVA_HOME='/usr/lib/jvm/java-1.8.0-openjdk-amd64'" >> /etc/environment  && \
	echo "JRE_HOME=/usr/lib/jvm/java-8-openjdk-amd64/jre" >> /etc/environment && \
	source /etc/environment && \
	cd /usr/local && \
	apt-get install wget -y && \
	wget http://apache.mirrors.spacedump.net/spark/spark-2.4.0/spark-2.4.0-bin-hadoop2.7.tgz && \
	sudo tar -xzf spark-2.4.0-bin-hadoop2.7.tgz && \
	sudo mv spark-2.4.0-bin-hadoop2.7 /opt/spark-2.4.0 && \
	ln -s /opt/spark-2.4.0 /opt/spark && \
	echo "PATH=$PATH:~/.local/bin" >> /etc/environment && \
	source /etc/environment && \
	echo $PATH && \
	apt-get -y autoremove  && \
	apt-get -y clean && \
	rm -r /root/.cache/pip && \
	mkdir -p /usr/share/man/man1 && \
	sudo apt-get install scala -y  && \
	echo "export SPARK_HOME=/opt/spark-2.4.0" >> ~/.bashrc && \
	echo "export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH" >> ~/.bashrc && \
	echo "export PYSPARK_DRIVER_PYTHON='jupyter'" >> ~/.bashrc && \
	echo "export PYSPARK_DRIVER_PYTHON_OPTS='notebook'" >> ~/.bashrc && \
	echo "export PYSPARK_PYTHON=python" >> ~/.bashrc && \
	echo "export PATH=$SPARK_HOME:$PATH:~/.local/bin:$JAVA_HOME/bin:$JAVA_HOME/jre/bin" >> ~/.bashrc && \
	source ~/.bashrc && \
	sudo apt-get install cifs-utils -y 

ENTRYPOINT pyspark