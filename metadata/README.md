# Metadata Service

Provides metadata and file URLs via a GraphQL API.

---

## **Features**
- Query metadata for uploaded and processed files.
- Generate signed URLs for secure file downloads from Amazon S3.

---

## **Endpoints**

### **GraphQL Query: `getFileMetadata`**
Fetch metadata for a given file.

#### Request
```graphql
query {
  getFileMetadata(id: "12345") {
    id
    fileName
    fileSize
    uploadedAt
    processedAt
    downloadUrl
  }
}
```

#### Response
```json
{
  "data": {
    "getFileMetadata": {
      "id": "12345",
      "fileName": "example.mp4",
      "fileSize": 10485760,
      "uploadedAt": "2024-12-21T10:00:00Z",
      "processedAt": "2024-12-21T11:00:00Z",
      "downloadUrl": "https://s3.amazonaws.com/bucket-name/example.mp4?signature=xyz"
    }
  }
}
```

---

## **Running the Service**

1. Set up environment variables:
    - `DB_CONNECTION_STRING`: Database connection string.
    - `AWS_S3_BUCKET`: S3 bucket name.

2. Run the service:
```bash
go run cmd/metadata/main.go
```

## **Testing**

Run unit tests for the service:

```bash
go test ./pkg/metadata -v
```