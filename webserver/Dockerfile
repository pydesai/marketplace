FROM ubuntu
RUN apt-get update
RUN apt-get -y install python
RUN apt-get clean
EXPOSE 8000
CMD [ "python", "-m", "SimpleHTTPServer" ]