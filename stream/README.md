# Streaming Service

Streams real-time updates on processing tasks via gRPC.

---

## **Features**
- Streams progress updates for media processing tasks.
- Implements a gRPC server for real-time communication.

---

## **Endpoints**

### **gRPC: `StreamProgress`**
Streams progress updates for a given task.

#### Request
```protobuf
message StreamRequest {
  string taskId = 1;
}
```
#### Response
```protobuf
message StreamResponse {
  string taskId = 1;
  string status = 2;
  int32 progress = 3; // Percentage completed
}
```
---

## **Running the Service**

1. Set up environment variables:
    - `DB_CONNECTION_STRING`: Database connection string.
2. Run the service:
```bash
go run cmd/stream/main.go
```
## **Testing**

Run unit tests for the service:

```bash
go test ./pkg/stream -v
```

