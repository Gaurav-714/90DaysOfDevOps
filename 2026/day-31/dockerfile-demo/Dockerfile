# Get the base image
FROM ubuntu

# Execute commands during build
RUN apt update && apt install -y curl

# Set working directory
WORKDIR /app

# Copy files from host to image
COPY . .

# Document the port exposed
EXPOSE 8080

# Default command
CMD ["echo", "Dockerfile Demo Running"]
