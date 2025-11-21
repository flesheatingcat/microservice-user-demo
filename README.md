# User Service (Demo)

## Overview

"User Service" is a microservice for a social network aimed at connecting startuppers with potential future colleagues for joint ventures.
It handles user-related information such as careers, education, goals, and skills, allowing users to manage and search for relevant profiles efficiently.
This repository contains a work-in-progress demo version showcasing features and contributions, built with a clean architecture and tested using modern tools.

---

## Technologies

- Language & Framework: Java 17, Spring Boot 3  
- Database: PostgreSQL  
- Cache: Redis  
- Object Storage: MinIO  
- ORM & Mapping: Spring Data JPA, MapStruct  
- Background Jobs: Spring Async, Scheduled Tasks  
- Testing: JUnit 5, Testcontainers, AssertJ  
- Other: Liquibase (DB migrations), Lombok, Feign clients

## Features Implemented by Me:

Functionality to submit, update, and delete recommendations/recommendation requests:

- Implemented controllers: RecommendationController, RecommendationRequestController
- Services: RecommendationService, RecommendationServiceImpl, RecommendationRequestService, RecommendationRequestServiceImpl
- Repositories: RecommendationRepository, RecommendationRequestRepository
- DTO layers for all recommendation-related classes
- Input validation on controllers/DTOs and unit tests (RecommendationServiceImplTest, RecommendationRequestServiceImplTest)
  
Event Cleanup Job

Automatically removes completed events from the system:
- EventService
- ChunkDeletionService for transactional deletion to ensure operation isolation and safety
- Methods for extracting relevant event IDs and deleting them
- AsyncExecutor with customized ThreadPoolTaskExecutor
- ExpiredEventCleanupScheduler and corresponding configuration in application.yaml
- Unit tests for EventService
