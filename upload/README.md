# Upload Service

Handles file uploads and stores metadata in the database. Files are uploaded to Amazon S3, and metadata is saved for further processing.

---

## **Features**
- Accepts file uploads via a GraphQL API.
- Validates file types and sizes.
- Stores files in Amazon S3.
- Saves metadata (e.g., file name, size, type, upload timestamp) in the database.

---

## **Endpoints**

### **GraphQL Mutation: `uploadFile`**
Upload a file to the system.

#### Request
```graphql
mutation {
  uploadFile(file: Upload!) {
    id
    fileName
    uploadedAt
  }
}
```

#### Response
```json
{
  "data": {
    "uploadFile": {
      "id": "12345",
      "fileName": "example.mp4",
      "uploadedAt": "2024-12-21T10:00:00Z"
    }
  }
}
```

### Running the Service
1.	Set up environment variables:
   - AWS_S3_BUCKET: Name of the S3 bucket.
   - DB_CONNECTION_STRING: Database connection string.
2.  Run the service:

```bash
go run cmd/upload/main.go
```
### Testing

Run unit tests for the service:

```bash
go test ./pkg/upload -v
```