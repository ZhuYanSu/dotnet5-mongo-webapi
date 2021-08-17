# dotnet5-mongo-webapi

## Goal

- Use TDD style
- Build a simple .net 5 WebAPI
  - With microservice architecture
- Use mongodb as persistent storage
- Dockerize everything

> Ref:
>
> - [Deploy a .NET Core API with Docker (Step-by-Step)](https://www.youtube.com/watch?v=f0lMGPB10bM)
> - [Creating a .NET 5 Microservice](https://www.youtube.com/watch?v=MIJJCR3ndQQ)

## Steps

1. Create `.gitignore`
   `dotnet new gitignore`

## Notes

- microservices architecture

  - Deal with transient errors on external services

  - Exponential backoff
    - Exponent the sleep time between retires
      - e.g., retries 1 time => wait 2\*\*1 seconds
  - Circuit breaker

    - Once the circuit is broken, the subsequence requests will fail early (i.e., w/o retries)

  - Machine readable logging
    - e.g., JSON format
  - Healthy check endpoint

- TDD test naming convention
  - `UnitOfWork_StateUnderTest_ExpectedBehavior`
  - e.g., `GetItemAsync_WithUnexistinIetm_RetrnNotFound`
- Mock vs. Stub
  - We won't verify anything in stub after running test
  - We will verify things in mock after running tests
