# Offline-LLMs

![Architectural Diagram](https://github.com/panc0050/Offline-LLMs/assets/144128284/17f7c287-517c-4ff7-9bcd-aa127d3c3cab)

1.	User Interface:

-	User: It is the first step where user will initiates the interaction by just sending and submitting the query, user wanted to ask. This is the representation where the process ‘start’ starts after the user input is captured.

-	Frontend: This is the frontend application where it behaves as a middleware for the user and the backend systems. It will capture and record the queries or I can say prompts that user sends to the backend server for the further processing.  

2.	Backend Server:

-	API Gateway: For the backend server, the API Gateway will become an entry point for the requests that arrive from the frontend application. This will happen when it directs the incoming requests to the appropriate backend services for the further processing of the data and its requests.

-	Authentication Service: Next service is authentication service that will check the identity of the user who will request the access, making sure that the request is sent from the verified user. The interaction will happen in the flow like API gateway will send the authentication request to the authentication service of the model and that will respond with some return status to the API gateway.

-	Request Validator: This will ensure that the request will be in a proper format and that it contains all the required and necessary information within. Moreover, it will check the validity of the directed request. When the API Gateway will send the validate request interaction and then will respond with the return validation.

-	Load Balancer: The load balancer will distribute the incoming and validated requests to the multiple inference engines to make the best use of all resources and ensure that the service is always available. It will work like that, when any request comes, the API Gateway will send it to the load balancer, when then will route the request to the appropriate and proper inference engine of the processing of that particular request.


3.	Model Serving:

-	Inference Engine: This engine processes the user’s query by using the loaded model for it. Then it will generate the response which will be based on the input query or prompt. It will work in a way that the load balancer will send the route for the inference to the inference engine.

-	Model Manager: The model manager of this model will manage and retrieves the files needed for making the prediction based on the query. It works besides the model repository to get the required model files. Here, the model manager will provide the response when the inference engine requests it.

-	Optimization Service: This service will improve the model to make it work properly and in a better way by using less power consumption. It will use the different methods to make the model a better decision-maker. It works in a way that when a model manager asks for the optimization service to optimize the model, this service will give the improved model to the inference engine.


4.	Data Storage:

-	Model Repository: This repository will store all the model files required for the inference. It is known as a central location for retrieving the model files. When the model manager needs any model file, it requests them from the model repository by saying retrieve files and the model repository responds by saying return files to them.

-	Inference Results Database: The database will save the results of the inference process, while assuring that the results are stored properly and available for later use. Here the inference engine will interact with the inference results database by sending the command store results.


5.	Monitoring & Logging:

-	Monitoring Services: The service will track how well the inference engine is performing in the model. It will collect the data on how fast it will respond to the query and uses its resources. It will work when the inference engine sends the message like send metrics, then the monitoring service will get the data it requires.

-	Logging Service: The logging service will record the detailed information about each of the requests and their responses which is made by the inference engine. This will assure that the all activities are documented properly for auditing and debugging purposes.


6.	Response Handling:

-	API Gateway: The response that is sent by the inference engines is processed by the API Gateway for its queries or prompts. Afterwards, the API Gateway will forward the inference results back to the frontend application. Then, when the inference engine will send the response, the API Gateway will return the results to the Frontend.

-	Frontend Application: Finally, after all the processes, the frontend application will receive the inference results from the API Gateway and then displays them to the user when they request for showing the results.

