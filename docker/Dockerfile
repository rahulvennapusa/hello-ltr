FROM python:3.7-stretch

# Install openjdk
RUN apt-get update && \
    apt-get install -y openjdk-8-jdk && \
    apt-get clean;

# Setup a user 
RUN useradd -ms /bin/bash ltr 
WORKDIR /home/ltr

# Clone repo and pull requirements
RUN git clone https://github.com/o19s/hello-ltr
RUN chown -R ltr.ltr hello-ltr
WORKDIR /home/ltr/hello-ltr

RUN pip install -r requirements.txt
USER ltr

CMD jupyter notebook --ip=0.0.0.0 --no-browser --NotebookApp.token='' 
