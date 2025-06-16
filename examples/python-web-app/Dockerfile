# Use a specific base image version
FROM ubuntu:22.04

# Set environment variables to avoid interactive prompts during package install
ENV DEBIAN_FRONTEND=noninteractive

# Set working directory
WORKDIR /app

# Install system dependencies and Python
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv python3-dev build-essential && \
    apt-get clean

# Copy application code
COPY . /app/

# Install Python dependencies
RUN pip3 install --upgrade pip && \
    pip3 install -r requirements.txt

# Expose port (for documentation; not strictly required)
EXPOSE 8000

# Set entry point and default command
ENTRYPOINT ["python3", "manage.py"]
CMD ["runserver", "0.0.0.0:8000"]
