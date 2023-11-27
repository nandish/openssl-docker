# openssl-docker

# To Generate the Docker Image 

```
# Change directory to project folder
cd docker-openssl

# Build Docker image
docker build -t docker-openssl:latest .

# Run Docker container in interactive mode
# Make sure you replace `<your_path>` with your target folder, this is where files will be created.

# For Docker Desktop (Windows Pro)
docker run -it --rm -v "C:\your_path\docker-openssl:/openssl-certs" docker-openssl

# For Docker Toolbox (Windows Home)
docker run -it --rm -v "/c/your_path:/openssl-certs" docker-openssl

```

# To Generate Certificate
```
# Create cert.pem and key.pem files for SSL encryption
openssl req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365

# Generate private key
openssl genrsa -out rsa.private 1024

# Generate corresponding public key
openssl rsa -in rsa.private -out rsa.public -pubout -outform PEM
```
