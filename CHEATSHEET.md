# Core System Design Cheatsheet

## The "Zero to Ten Million" Scale Path

### 1-100 Users
- Single EC2/Droplet.
- Web app and DB hosted on the same box.

### 1,000 Users
- Separated Web Tier and DB Tier.
- Vertical scaling (larger EC2 instances).

### 10,000 Users
- Load Balancer introduced (ALB/Nginx).
- Horizontal Web scaling (ASG).
- Managed Database (RDS).

### 100,000 Users
- Redis/Memcached introduced to offload DB reads.
- CDN (Cloudflare/CloudFront) for static assets.
- Worker servers (Celery/Sidekiq) + Message Queue (RabbitMQ/SQS) for async tasks.

### 1M+ Users
- Database Replication (Master-Slave/Multi-AZ).
- Database Sharding.
- Microservice decomposition begins.

## Key Acronyms
- **CDN**: Content Delivery Network 
- **LB**: Load Balancer
- **MQ**: Message Queue
- **API-GW**: API Gateway
- **KVS**: Key-Value Store
