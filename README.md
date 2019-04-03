# Ackee API documentation renderer / uploader

This Docker image contains a few tools we use for the rendering of API blueprints 
and subsequent uploading to object storage. 

## Supported object storage providers

### Minio

[Minio](https://github.com/minio/minio) is s3-compatible object storage you can 
run anywhere you want. Uploading script `rclone-upload-minio` is configurable 
with following environment variables.

**`MINIO_ACCESS_KEY`** obvious one, Minio instance prints this key after startup
**`MINIO_SECRET_KEY`** obvious one, Minio instance prints this key after startup 
**`MINIO_ENDPOINT`** full URL of your Minio instance e.g. `http://localhost:9000`
**`MINIO_BUCKET`** name of your Minio bucket e.g. `documentation`
**`MINIO_PREFIX`** directory prefix e.g. `project-name`, note it does not start with `/`
**`DOCS_OUTPUT_DIRECTORY`** directory you want to upload to Minio bucket



