# gRPC Basics ⚡

**gRPC** (Remote Procedure Call) is a high-performance API framework developed by Google.

## Key Differences from REST

### 1. Protocol Buffers (Protobuf) vs. JSON
-   **REST** uses **JSON** (text-based). It's easy for humans to read but slow for computers to parse.
-   **gRPC** uses **Protobuf** (binary). It's not human-readable but is **extremely fast** and lightweight.

### 2. HTTP/2
gRPC strictly uses **HTTP/2**, which allows:
-   **Multiplexing**: Multiple requests over a single connection.
-   **Streaming**: Client and Server can send data streams simultaneously.

## When to use gRPC?
-   **Microservices**: Low latency communication between internal services.
-   **Mobile Apps**: Bandwidth-efficient communication.
-   **Real-time**: Video streaming or gaming.

**Note**: Browsers don't support gRPC directly well yet, so it's mostly used for server-to-server communication.
