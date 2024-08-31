ForEach Example
Overview
This MuleSoft project demonstrates the use of the ForEach and Parallel ForEach components within Mule applications. The project consists of two flows that showcase how to process collections of data sequentially and in parallel.

Flows
1. ForEach Flow (forEachParallelForEachFlow)
Endpoint: /foreach

This flow iterates over an array of values, processing each element sequentially and adding 2 to each numeric value.

Key Components:

HTTP Listener: Triggers the flow on an HTTP request to /foreach.
Logger: Logs the start and end of the ForEach iteration.
Set Payload: Initializes the payload with an array [1, 2, 3, "Mule", 5].
ForEach: Iterates over each element in the array.
Try Scope: Catches any errors during iteration.
Transformation: Adds 2 to numeric elements.
Logger: Logs the transformed payload.
2. Parallel ForEach Flow (ParallelForEach)
Endpoint: /paralleleach

This flow processes a range of numbers [25, 26, 27, 28, 29, 30] in parallel, applying a transformation that adds 2 to each element.

Key Components:

HTTP Listener: Triggers the flow on an HTTP request to /paralleleach.
Logger: Logs the start and end of the Parallel ForEach iteration.
Set Payload: Initializes the payload with a range [25 to 30].
Parallel ForEach: Processes each element in the range simultaneously.
Transformation: Adds 2 to each element.
Logger: Logs the transformed payload for each parallel process.
How to Run
Deploy the Mule application using Anypoint Studio or any Mule runtime.
Use an HTTP client like Postman to send GET requests to the following endpoints:
For sequential processing: http://localhost:8081/foreach
For parallel processing: http://localhost:8081/paralleleach
Check the logs to see the processing of each element in the collection.
Expected Output
ForEach Flow: The numbers in the array will have 2 added to them, while non-numeric elements remain unchanged.

Parallel ForEach Flow: Each number in the range [25 to 30] will be processed in parallel, with 2 added to each element.

Error Handling
The ForEach flow includes a Try scope that captures and logs any errors encountered during the iteration.
