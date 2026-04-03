# Network Service Proxy Application Exercise

In this exercise, you will implement a Proxy Design Pattern to manage access to a network service that retrieves data from a remote server. The objective is to create a proxy that can control access to the network service and cache responses to optimize performance.


**Requirements**:

1. Create a NetworkService interface with the following method:
   * fetchData(): This method will be responsible for fetching data from a network service.

2. Implement a RealNetworkService class that:
   * Represents the actual network service and implements the NetworkService interface.
   * Simulates fetching data from a remote server.

3. Implement a NetworkServiceProxy class that:
   * Also implements the NetworkService interface.
   * Manages access to the RealNetworkService.
   * Checks if the data is already cached; if not, fetch it from the real service and cache it for future use.

4. Create a client class that demonstrates the use of the proxy. This class should:
   * Fetch data through the NetworkServiceProxy.
   * Display the results.


**Output**:

After executing the code, it will simulate the following sequence of operations:

* Display a message indicating that the data is being fetched from the remote server on the first call.

* Display a message indicating that the data is retrieved from the cache on subsequent calls.

Each operation should be clearly reflected in the output, confirming that the proxy is effectively managing access and caching data, thus optimizing performance.
