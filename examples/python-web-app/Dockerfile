//FROM ubuntu

//WORKDIR /app

//COPY requirements.txt /app
//COPY devops /app

//RUN apt-get update && \
//    apt-get install -y python3 python3-pip && \
//    pip install -r requirements.txt && \
 //   cd devops

//ENTRYPOINT ["python3"]
//CMD ["manage.py", "runserver", "0.0.0.0:8000"]

FROM ubuntu

# Update and install Python, pip
RUN apt-get update && \
    apt-get install -y python3 python3-pip

# Copy requirements.txt and install dependencies
COPY requirements.txt /tmp/requirements.txt
RUN pip3 install -r /tmp/requirements.txt

# Verify directory exists (and/or create if necessary)
RUN mkdir -p /devops
WORKDIR /devops




