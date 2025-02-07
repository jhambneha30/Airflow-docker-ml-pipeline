# Use an official Python runtime as a parent image
FROM python:3.10

# Set environment variables for AWS credentials (replace with your credentials)
ENV MINIO_ACCESS_KEY_ID=your_access_key
ENV MINIO_SECRET_ACCESS_KEY=your_secret_key
ENV MINIO_ENDPOINT=your_minio_endpoint
ENV MINIO_BUCKET_NAME=your_bucket_name

# ENV MINIO_ACCESS_KEY_ID=4BURGezVwSWhSLG9iDSu
# ENV MINIO_SECRET_ACCESS_KEY=GLgvClBrXkOYEs5o45C083b940Fcvu59hjwSywMA
# #ENV MINIO_ENDPOINT="https://play.min.io:9000"
# ENV MINIO_ENDPOINT=host.docker.internal:9000
# ENV MINIO_BUCKET_NAME=airflow123

## Command to build the docker image in src folder: 
    ## docker build --tag training-image:v1.0 .
## Command to run the docker container: 
    ## docker run -e MINIO_ACCESS_KEY_ID=4BURGezVwSWhSLG9iDSu -e MINIO_SECRET_ACCESS_KEY=GLgvClBrXkOYEs5o45C083b940Fcvu59hjwSywMA -e MINIO_ENDPOINT=host.docker.internal:9000 -e MINIO_BUCKET_NAME=airflow123 training-image:v1.0
# Set the working directory in the container
WORKDIR /app

# Copy the requirements file into the container
COPY requirements.txt .

# Install any needed packages specified in requirements.txt
RUN pip install -r requirements.txt

# Copy the rest of the application code into the container
COPY . .

# Command to run the training and model publishing script
CMD ["python", "train_and_publish.py"]
