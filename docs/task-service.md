# Task Service

- [Service (EC2)](https://walletfm.wtlltech.com/service)
- [Service (K8s)](http://k8s-prod-financia-48f4c3f817-1169813628.sa-east-1.elb.amazonaws.com/service/)

## Overview

The task-service is a FastApi-based microsservice reponsible for managing and executing background tasks on demand.

It allows others service or users to offload time-consuming or non-blocking operations, such as data processing, API calls, or notifications, to be performed asynchoronously in the background;
This service is optimized for scalability and efficiency, handling tasks without interrupting the main flow of an application or request. It Leverages FastAPI's async capabilities and integrates with background task queues (e.g, Celery or FastAPI's native BackgroundTasks feature) to ensure smooth tasks management.
Key Features:

- **Task Submission**: Clients can submit tasks via API requests, specifying the type of task and necessary parameters.
- **Task Status Tracking**: The service provides endpoints for tracking the status of submitted tasks (e.g., pending, in-progress, completed, failed).
- **Task Management**: It supports managing task priorities, cancellation, retries, and scheduling.
- **On-Demand Execution**: Tasks are executed in real-time as they are submitted, or can be scheduled for execution at a future time.
- **Asynchronous Processing**: Non-blocking task execution ensures that requests are processed efficiently, and the service remains responsive.

## API Endpoints

- `POST /tasks`: Submit a new background task.
- `GET /tasks/{task_id}`: Retrieve the status and result of a specific task.
- `DELETE /tasks/{task_id}`: Cancel a pending or in-progress task.
- `GET /tasks`: List all tasks with filtering options (e.g., by status or date).
- `/scheduler/jobs`: List all scheduled tasks and manage scheduling options.

## Technology Stack:

- FastAPI for the web framework, enabling fast and efficient API development.
- Celery or native FastAPI BackgroundTasks for task queue management and execution.
- Redis or RabbitMQ for message brokering (if using Celery).

Use Cases:

- Processing large data batches.
- Offloading time-consuming operations (e.g., file uploads, API requests).
- Executing scheduled jobs like sending notifications or periodic clean-ups.
