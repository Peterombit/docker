# Set the base image
FROM node

# Define working directory
WORKDIR /var/www/app

# Install yarn
RUN apt-get update && apt-get install -y apt-transport-https
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt-get update && apt-get install yarn

# Copy app
COPY app /var/www/app

# Install node_modules with yarn
RUN yarn

# Expose port
EXPOSE 3000

# Run app
CMD ["node","index.js"]

#docker build -t rizkyario/42-docker-1-bonus-yarn .
#docker run -it --rm -p 3000:3000 rizkyario/42-docker-1-bonus-yarn