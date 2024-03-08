# Use an official Python runtime as the base image
FROM python:3.9.18-alpine3.19

# Create a non-root user and group
RUN addgroup -S appuser && adduser -S appuser -G appuser

# Set the working directory
WORKDIR /app

# Copy the requirements file
COPY requirements.txt .

# Install the required libraries
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code
COPY . .

# Change ownership of the application directory to the non-root user
RUN chown -R appuser:appuser /app

# Switch to the non-root user
USER appuser

# Run the command to start the application
CMD ["python", "app.py"]
