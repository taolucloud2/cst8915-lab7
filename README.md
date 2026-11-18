# CST8915 Lab 7:Full-stack Cloud-native Development: Introduction to Kubernetes Basics

- **Student Name:** Tao Lu
- **Student ID:** 41284860
- **Course:** CST8915 Full-stack Cloud-native Development
- **Semester:** Fall 2026

## Demo Video

[demo video](https://youtu.be/nGxF_HrhJBo)

## RabbitMQ Configuration Analysis

### 1. Stateless or Stateful?

RabbitMQ is **stateful**. It stores data such as queues and messages.

### 2. Running Without Persistent Storage

In this lab, RabbitMQ has no persistent storage. Its data is saved only inside the Pod. If the Pod stops, the data is lost.

### 3. When the Pod Is Deleted or Restarted

Kubernetes creates a new RabbitMQ Pod automatically, but it starts empty. All messages in the queue (such as unprocessed orders) are lost.

### 4. Possible Solutions

- Use a **PersistentVolumeClaim (PVC)** to save data on an Azure Disk.
- Use a **StatefulSet** instead of a Deployment.
- Use a managed service such as **Azure Service Bus**.

### 5. Does Azure Service Bus Solve This?

Yes. Azure Service Bus is managed by Azure, so messages are stored safely and are not lost when Pods restart. However, the order service code must be changed to use Service Bus, and it costs money.
