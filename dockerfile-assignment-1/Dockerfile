# use this empty Dockerfile to build your assignment
FROM node:6-alpine
# NOTE: The instructions are now in the README.md file in this directory.

#typical web server runs on port 3000
EXPOSE 3000

RUN apk add --no-cache tini

#change the working directory 
WORKDIR /usr/src/app

COPY package.json package.json

RUN npm install && npm cache clean --force
COPY . .

CMD [ "/sbin/tini", "--", "node", "./bin/www" ]

#after this you do
# docker built -t <image_name> .
#to test it locally:
# docker run -p 3000:3000 <image_name>
#to push it to dockerhub:
# docker tag <image_id> <dockerhub_username>/<image_name>:<tag>
# docker login
# docker push <dockerhub_username>/<image_name>:<tag>