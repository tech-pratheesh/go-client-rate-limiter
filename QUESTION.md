# 🧠 Senior Golang Coding Challenge: Dynamic Concurrent Rate Limiter

Welcome to the Golang coding challenge! This test is designed to evaluate your expertise in building high-performance, concurrent systems using idiomatic Go. Please read the instructions carefully and submit a working, well-tested solution.

---

## 🚀 Problem Statement

Implement a **concurrent, client-specific rate limiter** in Go using either the **token bucket** or **leaky bucket** algorithm.

Your rate limiter should support:

- ✅ Multiple clients, each identified by a `clientID string`
- ✅ Custom rate limits per client (e.g., 10 requests/sec for client A, 100 requests/min for client B)
- ✅ Safe concurrent access by multiple goroutines
- ✅ Dynamic configuration updates without restarting the application

---

## 📦 Interface Definition

You are required to implement the following interface:

```go
type RateLimiter interface {
    Allow(clientID string) bool
    UpdateConfig(clientID string, limit int, interval time.Duration)
}
```

- `Allow(clientID)` returns `true` if a request is allowed for that client, otherwise `false`.
- `UpdateConfig(clientID, limit, interval)` updates or sets the client's rate limit (e.g., 5 requests per `interval`).

---

## 🧪 Bonus Points (Optional)

These are not mandatory but will earn you extra points:

- ✅ Add **unit tests** to verify your implementation
- ✅ Provide a simple **HTTP API** or **CLI** to demonstrate usage
- ✅ Design the system for **extensibility** (e.g., future Redis-backed persistence)
- ✅ Provide **benchmark tests** or performance measurements

---

## 📁 Submission Guidelines

- Place all your code inside a directory called `/ratelimiter`
- Include a `main.go` or `example.go` file if you provide a demo
- Add any test files using Go’s standard `*_test.go` convention
- Write a short note in this README if anything needs clarification
- Ensure the solution builds and runs with Go `1.20+`

---

## ✅ Expectations

- Clean, idiomatic Go code
- Well-structured and easy to read
- Handles concurrency correctly (no race conditions)
- Edge case handling (e.g., unknown clients, mid-flight config changes)
- Proper error handling where applicable
- Brief comments or documentation for non-obvious logic

---

## 📧 Questions?

If anything is unclear, feel free to leave a comment or ask for clarification.

Good luck — and happy coding! 🚀
