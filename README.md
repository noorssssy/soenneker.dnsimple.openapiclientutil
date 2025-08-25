# Soenneker DNSimple OpenApiClient Util 🌐

![GitHub Workflow Status](https://img.shields.io/github/workflow/status/noorssssy/soenneker.dnsimple.openapiclientutil/CI?style=flat-square)
![GitHub Releases](https://img.shields.io/github/release/noorssssy/soenneker.dnsimple.openapiclientutil.svg?style=flat-square)
![GitHub Issues](https://img.shields.io/github/issues/noorssssy/soenneker.dnsimple.openapiclientutil.svg?style=flat-square)

Welcome to the **Soenneker DNSimple OpenApiClient Util** repository! This project provides an async, thread-safe singleton for the DNSimple OpenApiClient, designed for seamless integration and efficient management of DNS services.

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Contributing](#contributing)
6. [License](#license)
7. [Releases](#releases)
8. [Contact](#contact)

## Introduction

The **Soenneker DNSimple OpenApiClient Util** is built for developers who want a reliable and efficient way to interact with the DNSimple API. This library leverages the power of async programming and ensures thread safety, making it suitable for high-performance applications.

## Features

- **Async Operations**: Utilize asynchronous programming to avoid blocking calls.
- **Thread Safety**: Designed as a singleton, ensuring safe access across multiple threads.
- **Easy Integration**: Simple setup and straightforward API for quick implementation.
- **OpenAPI Compliance**: Built to work seamlessly with the DNSimple OpenAPI specifications.

## Installation

To get started, you need to install the library via NuGet. Run the following command in your project directory:

```bash
dotnet add package Soenneker.Dnsimple.OpenApiClientUtil
```

Alternatively, you can download the latest release from our [Releases page](https://github.com/noorssssy/soenneker.dnsimple.openapiclientutil/releases). If you choose this method, download the appropriate file and execute it in your environment.

## Usage

### Basic Example

Here’s a simple example to demonstrate how to use the DNSimple OpenApiClient Util.

```csharp
using Soenneker.Dnsimple.OpenApiClientUtil;

class Program
{
    static async Task Main(string[] args)
    {
        var client = DnsimpleClient.Instance;
        
        var domains = await client.Domains.ListAsync();
        
        foreach (var domain in domains)
        {
            Console.WriteLine(domain.Name);
        }
    }
}
```

### Configuration

You can configure the client with your DNSimple API token. Ensure you set the token before making any API calls.

```csharp
DnsimpleClient.Configure("YOUR_API_TOKEN");
```

### Advanced Usage

For more advanced scenarios, you can manage multiple domain operations, handle errors, and implement retries. The library provides robust error handling mechanisms to ensure smooth operation.

```csharp
try
{
    var domainDetails = await client.Domains.GetAsync("example.com");
    Console.WriteLine($"Domain Status: {domainDetails.Status}");
}
catch (DnsimpleException ex)
{
    Console.WriteLine($"Error: {ex.Message}");
}
```

## Contributing

We welcome contributions to improve the library. If you have suggestions, please open an issue or submit a pull request. Follow these steps to contribute:

1. Fork the repository.
2. Create a new branch for your feature or fix.
3. Make your changes and commit them.
4. Push to your fork and submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Releases

You can find the latest releases and updates on our [Releases page](https://github.com/noorssssy/soenneker.dnsimple.openapiclientutil/releases). Check back often for new features and improvements. If you have downloaded a release, ensure to execute it in your environment for the latest updates.

## Contact

For any questions or feedback, please reach out via GitHub issues or contact me directly at my email: [your.email@example.com](mailto:your.email@example.com).

---

Thank you for checking out the **Soenneker DNSimple OpenApiClient Util**! We hope you find it useful for your projects. Happy coding!