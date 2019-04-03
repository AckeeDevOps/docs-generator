# Ackee API documentation renderer / uploader

This Docker image contains a few tools we use for the rendering of API blueprints 
and subsequent uploading to object storage. 

## Supported object storage providers

### Minio

[Minio](https://github.com/minio/minio) is s3-compatible object storage you can 
run anywhere you want. Uploading script `rclone-upload-minio` is configurable 
with following environment variables.

| Variable                    | Description                                                           |
| --------------------------- | --------------------------------------------------------------------- |
| **`MINIO_ACCESS_KEY`**      | obvious one, Minio instance prints this key after startup             |
| **`MINIO_SECRET_KEY`**      | obvious one, Minio instance prints this key after startup             |
| **`MINIO_ENDPOINT`**        | full URL of your Minio instance e.g. `http://localhost:9000`          |
| **`MINIO_BUCKET`**          | name of your Minio bucket e.g. `documentation`                        |
| **`MINIO_PREFIX`**          | directory prefix e.g. `project-name`, note it does not start with `/` |
| **`DOCS_OUTPUT_DIRECTORY`** | directory you want to upload to Minio bucket                          |

### Google Cloud Storage (GCS)

Google Cloud Storage is object storage from the Google Cloud Plarform portfolio. 
Uploading script `rclone-upload-gcs` is configurable with following environment variables.

**`GCLOUD_SA_KEY`** Base64-encoded Service Account key (JSON format)

**`GCLOUD_PROJECT_ID`** GCP project ID, note that project name is not the same as project ID (not always)

**`DOCS_OUTPUT_DIRECTORY`** directory you want to upload to GCS bucket

**`GCS_BUCKET`** name of your GCS bucket e.g. `documentation`

**`GCS_PREFIX`** directory prefix e.g. `project-name`, note it does not start with `/`





