# Weather Service Application Exercise
You are developing a weather application that needs to fetch weather data from multiple sources. The legacy weather service provides weather data in XML format through a getWeatherData() method. However, you also want to incorporate a new third-party weather service that provides data in JSON format using a fetchWeather() method.



**Task**:

* Implement the Adapter Design Pattern to create a system that allows users to:
* Use the existing legacy weather service with its getWeatherData() method.
* Adapt the new third-party weather service with its fetchWeather()  method for seamless integration.
* Retrieve weather data from both services without modifying the existing codebase that relies on the getWeatherData() method.



**Output**:

After executing the code, it will simulate the following sequence of weather data retrievals:

* Retrieve and display weather data from the legacy weather service using XML.
* Retrieve and display weather data from the adapted third-party weather service using JSON.

Ensure that both weather services can be used interchangeably while maintaining a consistent interface for the user.
