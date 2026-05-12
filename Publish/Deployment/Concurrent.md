# 200–500 Concurrent Users — What Does It Actually Mean?

You put "supports 200–500 concurrent users" on your resume. Then the interviewer asks: how?

It's not one line of code. It's a combination of techniques.

## Who Controls Concurrency?

| Layer | Technology | Role |
|-------|-------------|------|
| App | Go + Gin | 100–200 concurrent requests per Pod |
| Connection Pool | MySQL (100 conns) | Limits DB load |
| Cache | Redis | Session storage, reduces DB hits |
| Async | RabbitMQ | Handles exam submissions, prevents spikes |
| Scaling | K8s HPA | 2 → 6 Pods during peak |

## Key Code Examples

```go
// Connection pool directly limits concurrency
db.SetMaxOpenConns(100)

// Async queue for peak smoothing
queue.Publish(examSubmission)