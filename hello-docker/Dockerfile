# start from a node image
FROM node:alpine
# copy all the files in this directory into a new directory to b created in the container named 'app'
COPY . /app
# Command to run our app
# CMD node /app/app.js
# OR
# We can set the working directory where the command sud b executed from so we wont need /app/app.js
# all the instructions after the WORKDIR instructions assumes we are working from the /app directory
WORKDIR /app
CMD node app.js