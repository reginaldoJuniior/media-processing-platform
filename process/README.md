# Processing Service

Subscribes to an Amazon SQS queue, processes tasks (e.g., transcoding media), and updates the metadata in the database.


## **Features**
- Consumes media processing tasks from Amazon SQS.
- Simulates media processing (e.g., transcoding).
- Updates the processing status in the database.

---

## **Processing Flow**

1. Receive a task from Amazon SQS.
2. Simulate processing (e.g., video transcoding).
3. Update metadata to reflect the task status.

---

## **Running the Service**

1. Set up environment variables:
    - `AWS_SQS_QUEUE_URL`: URL of the SQS queue.
    - `DB_CONNECTION_STRING`: Database connection string.

2. Run the service:
```bash
go run cmd/process/main.go
```

## **Testing**

Run unit tests for the service:

```bash
go test ./pkg/process -v
```