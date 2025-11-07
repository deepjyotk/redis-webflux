# Redis WebFlux

A comprehensive collection of code samples and practical demonstrations for integrating Redis with Spring WebFlux. This repository is designed to help developers understand and implement reactive programming patterns with Redis in modern Spring applications.

## Project Overview

This repository contains multiple modules and sample projects that showcase how to use Redis in reactive (non-blocking) applications using Spring WebFlux. The code samples are structured to demonstrate various Redis features, performance testing, and integration patterns, making it a valuable resource for both beginners and experienced developers.

## Features

- **Reactive Redis Integration**: Learn how to use Redis as a reactive data store with Spring WebFlux.
- **Performance Testing**: Includes scripts and modules to benchmark Redis performance in different scenarios.
- **Redisson Playground**: Explore advanced Redis features using the Redisson client.
- **Modular Structure**: Organized into focused directories for easy navigation and learning.
- **Production-Ready Patterns**: Demonstrates best practices for building scalable, non-blocking applications.

## Repository Structure

- `redis-spring/` - Main Spring WebFlux + Redis integration samples (Java, Maven).
- `redis-performance/` - Scripts and code for benchmarking and performance testing Redis.
- `redisson-playground/` - Experiments and advanced usage with the Redisson client.

## Setup Instructions

### Prerequisites

- Java 11 or higher
- Maven 3.6+
- Redis server (local or remote)
- (Optional) Docker, for running Redis locally

### Clone the Repository

```bash
git clone https://github.com/deepjyotk/redis-webflux.git
cd redis-webflux
```

### Running Redis Locally (with Docker)

```bash
docker run --name redis -p 6379:6379 -d redis
```

### Build and Run the Spring WebFlux Sample

```bash
cd redis-spring
mvn clean install
mvn spring-boot:run
```

The application will start on [http://localhost:8080](http://localhost:8080).

## Usage Examples

### Basic Reactive Redis Operations

The `redis-spring` module demonstrates how to:

- Store and retrieve data reactively using `ReactiveRedisTemplate`
- Work with Redis data structures (String, Hash, List, Set, etc.)
- Publish and subscribe to Redis channels in a non-blocking way

#### Example: Saving and Retrieving a Value

```java
@Autowired
private ReactiveRedisTemplate<String, String> reactiveRedisTemplate;

public Mono<Boolean> saveValue(String key, String value) {
    return reactiveRedisTemplate.opsForValue().set(key, value);
}

public Mono<String> getValue(String key) {
    return reactiveRedisTemplate.opsForValue().get(key);
}
```

### Performance Testing

Navigate to the `redis-performance` directory for scripts and instructions on running Redis benchmarks. This can help you understand the throughput and latency characteristics of your Redis setup.

### Advanced Redisson Usage

The `redisson-playground` module contains code samples for:

- Distributed locks
- Reactive data structures
- Pub/Sub with Redisson

## Contribution Guidelines

We welcome contributions! To contribute:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Make your changes and commit them (`git commit -am 'Add new feature'`)
4. Push to your branch (`git push origin feature/your-feature`)
5. Create a Pull Request

Please ensure your code follows the existing style and includes relevant tests or documentation.

## License

This repository is licensed under the MIT License.

## Acknowledgements

- [Spring WebFlux Documentation](https://docs.spring.io/spring-framework/docs/current/reference/html/web-reactive.html)
- [Redis Documentation](https://redis.io/documentation)
- [Redisson Documentation](https://github.com/redisson/redisson)
