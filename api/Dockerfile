
#This line allows the agent to run without a configuration file.
ENV NEW_RELIC_DISTRIBUTED_TRACING_ENABLED=true \
#send the logs
NEW_RELIC_LOG=stdout


# specify a parent image (node17 and linnux alpine)
FROM node:17-alpine

# install nodemon to restart the server when files are changed
RUN npm install -g nodemon

# specify a working directoory of image
WORKDIR /app

# copy the package.json to the folder to be able to install the nodes modules
COPY package.json .

# RUn the npm instaall at build time to add all the dependencies to the image
RUN npm install

# copy all the sources files
COPY . .

# expose the working Port
EXPOSE 3000

# command run only whe container of this iage is run
# run de dev to run nodemon "dev": "nodemon -L app.js" (very important to add the flag -L in windows to use with docker)
CMD [ "npm", "run", "dev" ]

# to build image container
# t is to add tag
#  the  . is a relative path for the image
# docker build -t nameTag .