FROM node:10
WORKDIR /usr/src/app

# copy app source code 
COPY . .

# Install packages or Copy sources code 
RUN npm install 

ENV PORT=8060
EXPOSE 8060

CMD [ "npm", "start" ]
