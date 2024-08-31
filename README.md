📂 MuleSoft Project: ForEach and Parallel ForEach Example
📋 Overview
This MuleSoft project demonstrates the use of the ForEach and Parallel ForEach components within Mule applications. The project consists of two flows that showcase how to process collections of data sequentially and in parallel.

🛠️ Flows
1. ForEach Flow (forEachParallelForEachFlow)
Endpoint: /foreach

Description: This flow iterates over an array of values, processing each element sequentially and adding 2 to each numeric value.

🔑 Key Components:
HTTP Listener:
🟢 Purpose: Triggers the flow on an HTTP request to /foreach.
🟢 Configuration: HTTP_Listener_config
Logger:
🟢 Purpose: Logs the start of the ForEach iteration with the message "Start Each".
Set Payload:
🟢 Purpose: Initializes the payload with an array [1, 2, 3, "Mule", 5].
ForEach:
🟢 Purpose: Iterates over each element in the array.
🟢 Internal Flow:
Try Scope: Catches any errors during iteration.
Transformation: Adds 2 to numeric elements.
Logger: Logs the transformed payload.
Final Logger:
🟢 Purpose: Logs the end of the ForEach iteration with the message "End for each".
2. Parallel ForEach Flow (ParallelForEach)
Endpoint: /paralleleach

Description: This flow processes a range of numbers [25, 26, 27, 28, 29, 30] in parallel, applying a transformation that adds 2 to each element.

🔑 Key Components:
HTTP Listener:
🟢 Purpose: Triggers the flow on an HTTP request to /paralleleach.
🟢 Configuration: HTTP_Listener_config
Logger:
🟢 Purpose: Logs the start of the Parallel ForEach iteration with the message "Start Foreach".
Set Payload:
🟢 Purpose: Initializes the payload with a range [25 to 30].
Parallel ForEach:
🟢 Purpose: Processes each element in the range simultaneously.
🟢 Internal Flow:
Transformation: Adds 2 to each element.
Logger: Logs the transformed payload for each parallel process.
Final Logger:
🟢 Purpose: Logs the end of the Parallel ForEach iteration with the message "End Foreach".
🚀 How to Run
Deploy the Mule application using Anypoint Studio or any Mule runtime.
Test the flows using an HTTP client (e.g., Postman):
For sequential processing: GET http://localhost:8081/foreach
For parallel processing: GET http://localhost:8081/paralleleach
Observe the logs to see the flow execution and payload transformations.
📊 Expected Output
ForEach Flow:
The numbers in the array will have 2 added to them, while non-numeric elements remain unchanged.
Parallel ForEach Flow:
Each number in the range [25 to 30] will be processed in parallel, with 2 added to each element.
⚠️ Error Handling
The ForEach flow includes a Try scope that captures and logs any errors encountered during the iteration.
