# Media Processing Platform

A scalable backend system built with Golang for uploading, processing, and streaming media files. This project showcases modern backend technologies, including Amazon SQS, gRPC, GraphQL, and Amazon S3, within a microservices architecture.

---

## **Features**

- **Media Upload**: Upload files via a GraphQL API with validation, and store them in Amazon S3.  
- **Processing Pipeline**: Queue media processing tasks using Amazon SQS and simulate operations like transcoding.  
- **Real-Time Updates**: Use gRPC to stream progress updates for media processing tasks.  
- **Metadata Querying**: Query file metadata and generate secure download URLs via a GraphQL API.  
- **Microservices Architecture**: Clean separation of concerns across multiple services.  
- **Observability**: Monitor system performance and behavior with OpenTelemetry.

---

## **Architecture**

### **High-Level Design**
The system is designed as a collection of microservices:
1. **Upload Service**: Handles file uploads and metadata storage.  
2. **Processing Service**: Processes tasks from SQS and updates metadata.  
3. **Streaming Service**: Streams real-time updates via gRPC.  
4. **Metadata Service**: Serves metadata and signed download URLs.  

### **Tech Stack**
- **Language**: Golang  
- **Queue**: Amazon SQS  
- **File Storage**: Amazon S3  
- **Database**: PostgreSQL or DynamoDB  
- **API**: GraphQL (using `gqlgen`)  
- **Streaming**: gRPC  
- **Observability**: OpenTelemetry  

---

## **Getting Started**

### **Prerequisites**
- Go 1.20+  
- AWS account with access to S3 and SQS  
- PostgreSQL or DynamoDB instance  
- Protobuf compiler for gRPC  

### **Setup**
1. Clone the repository:  
   ```bash
   git clone https://github.com/<your-username>/media-processing-platform.git
   cd media-processing-platform
