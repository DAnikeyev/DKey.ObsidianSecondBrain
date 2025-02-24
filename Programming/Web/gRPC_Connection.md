---
date_added: 2025-02-24
tags:
  - web
---
Up: [gRPC](gRPC.md)
___
# Features
### Deadline (TImeout)
- Deadlines in gRPC are used to specify the maximum amount of time a client is willing to wait for an RPC to complete. This helps in preventing indefinite waits and managing resource usage effectively.
- **Implementation**: When a client sets a deadline, it is propagated to the server, which can then use this information to optimize its processing. If the deadline is exceeded, the operation is terminated with a status indicating a timeout.
### Metadata
- **Purpose**: Metadata in gRPC is used to send additional information with RPC calls. It can be used for authentication, tracing, or passing custom information between client and server.
- **Types**: Metadata can be divided into two categories:
    - **Request Metadata**: Sent from client to server with the request.
    - **Response Metadata**: Sent from server to client with the response.
- **Implementation**: Metadata is essentially a collection of key-value pairs. It can be set and accessed using gRPC's API on both client and server sides.

### Channels
- **Purpose**: Channels in gRPC are used to manage connections to a server. They abstract the underlying connection details and provide a way to perform RPCs.
- **Features**:
    - **Load Balancing**: Channels can be configured to use different load balancing strategies to distribute requests across multiple server instances.
    - **Connection Management**: Channels handle connection pooling, reconnections, and other aspects of connection management.
    - **Security**: Channels can be configured with security credentials to ensure secure communication between client and server.
## Example
```cs
using System;
using System.Threading.Tasks;
using Grpc.Core;
using Grpc.Net.Client;
using YourNamespace; // Replace with your actual namespace

class Program
{
    static async Task Main(string[] args)
    {
        // Create a channel
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");

        // Create a client (stub) from the generated code
        var client = new YourService.YourServiceClient(channel);

        // Set a deadline (timeout)
        var deadline = DateTime.UtcNow.AddSeconds(5); // 5 seconds from now

        // Create metadata
        var headers = new Metadata
        {
            { "authorization", "Bearer your-token" },
            { "custom-header", "custom-value" }
        };

        try
        {
            // Make a call with deadline and metadata
            var response = await client.YourRpcMethodAsync(
                new YourRequest { /* set request fields */ },
                new CallOptions(headers: headers, deadline: deadline)
            );

            Console.WriteLine("Response: " + response.YourResponseField);
        }
        catch (RpcException ex) when (ex.StatusCode == StatusCode.DeadlineExceeded)
        {
            Console.WriteLine("The call timed out.");
        }
        catch (RpcException ex)
        {
            Console.WriteLine($"RPC failed: {ex.Status.Detail}");
        }
    }
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
