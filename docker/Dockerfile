FROM ubuntu:20.04

# Update apt-get and install dependencies
RUN apt-get update -y \
    && apt-get install -y python3-pip \
    && apt-get install -y mysql-client 

# Set working directory
COPY . /app
WORKDIR /app

# Install the specific version of Werkzeug
RUN pip install --upgrade pip \
    && pip install Werkzeug==2.0.3

# Install other dependencies
RUN pip install -r requirements.txt

# Expose port 8080
EXPOSE 8080

# Set the entry point to run the Flask app
ENTRYPOINT [ "python3" ]
CMD [ "app.py" ]
