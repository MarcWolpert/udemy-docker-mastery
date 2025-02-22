# use the README.md file for requirements to build this image
# If you get stuck, the answer/ directory has the solution
FROM ubuntu:24.04

RUN apt-get update && \
	apt-get install -y apache2-utils && \
	rm -rf /var/lib/apt/lists/* 

#runs the apache benchmark tool with the following parameters
ENTRYPOINT ["ab"]

#-n 10: number of requests to perform
#-c 2: number of multiple requests to make at a time
#https://www.bretfisher.com/: the URL to perform the requests on

CMD ["-n", "10", "-c", "2", "https://www.bretfisher.com/"]

#then run this with docker build -t ab .
#and then run it with docker run ab

#it tags it with the 'ab' tag and then runs it