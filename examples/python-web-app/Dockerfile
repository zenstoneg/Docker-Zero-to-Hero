FROM ubuntu

WORKDIR /app

# Update and install Python, pip
RUN apt-get update && \
    apt-get install -y python3 python3-pipx

# Copy requirements.txt and install dependencies
COPY requirements.txt /tmp/requirements.txt
RUN pipx install -r /tmp/requirements.txt

# Verify directory exists (and/or create if necessary)
RUN mkdir -p /devops
WORKDIR /devops

ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]








