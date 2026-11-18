# CST8915 Lab 7:Full-stack Cloud-native Development: Introduction to Kubernetes Basics

- **Student Name:** Tao Lu
- **Student ID:** 41284860
- **Course:** CST8915 Full-stack Cloud-native Development
- **Semester:** Fall 2026

## Demo Video

[demo video](https://youtu.be/nGxF_HrhJBo)

## RabbitMQ Configuration Analysis

### 1. Stateless or Stateful?

RabbitMQ is a stateful application because it stores data, such as queues and messages.

### 2. Running Without Persistent Storage

In this lab, RabbitMQ has no persistent storage. Its data is saved only inside the Pod. If the Pod stops, the data is lost.

### 3. When the Pod Is Deleted or Restarted

All messages in the queue (such as unprocessed orders) are lost. As I demonstrated in the video, when I deleted the RabbitMQ Pod, it was recreated, but the messages in the queue were lost.

### 4. Possible Solutions

 Use a managed service such as **Azure Service Bus**.

### 5. Does Azure Service Bus Solve This?

Azure Service Bus stores the data for us, so we do not need to worry about data loss. It is managed by Azure.
