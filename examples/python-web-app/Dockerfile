# Use Ubuntu as the base image
FROM ubuntu

# Set the working directory
WORKDIR /app

# Copy requirements and application files
COPY requirements.txt /app/
COPY devops /app/

# Install necessary dependencies
RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

# Create a virtual environment and install dependencies
RUN python3 -m venv /app/venv && \
    /app/venv/bin/pip install --no-cache-dir -r requirements.txt

# Expose the application port
EXPOSE 8000

# Run the application using the virtual environment's Python interpreter
CMD ["/app/venv/bin/python3", "manage.py", "runserver", "0.0.0.0:8000"]
