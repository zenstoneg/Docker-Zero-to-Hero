FROM ubuntu

WORKDIR /app

# Update and install Python, pip
RUN apt-get update && \
    apt-get install -y python3-dev build-essential libssl-dev libffi-dev libblas-dev python3-venv && \
    apt-get clean

# Copy requirements.txt and install dependencies
COPY requirements.txt /tmp/requirements.txt
COPY devops /app

# Create a virtual environment inside the container
RUN python3 -m venv /env
# Install pip packages inside the virtual environment
RUN /env/bin/pip install --upgrade pip && \
    /env/bin/pip install -r /tmp/requirements.txt 


# Set the virtual environment's python and pip as the default for future commands
ENV PATH="/env/bin:$PATH"
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]








