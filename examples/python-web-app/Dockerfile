FROM ubuntu

# Set the working directory
WORKDIR /app

# Copy requirements and application files
COPY requirements.txt /app/
COPY devops /app/

# Install necessary dependencies
RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

# Create a virtual environment and install dependencies
RUN python3 -m venv venv1 && \
    venv1/bin/pip install --no-cache-dir -r requirements.txt

# Expose the application port
EXPOSE 8000

# Use the full path to activate the virtual environment and run the application
CMD ["venv1/bin/python3", "manage.py", "runserver", "0.0.0.0:8000"]
