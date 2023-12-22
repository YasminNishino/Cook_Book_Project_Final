# Smart Cook Book Project
# 	What the project does
This document describes a Python code serving as potential Recipe Finder Application. The application is designed to interact with the Spoonacular API to fetch recipes based on user-provided ingredients and to output detailed recipes including nutrition data, if required. Overall, it demonstrates the functions of an Application Programming interface, and the basic interac-tions with it, such as the authentication of HTTP requests, and the definition of parameters to retrieve desired information. 
The Spoonacular API provides various information about “food ontology”, including the indi-vidual recipes ingredients, significant nutritional data, preparation process and dietary needs or relevant intolerances.
# 	Why is this project useful
Most people, especially students that are new to the game of living by their own, may struggle to plan groceries in advance and end up surrendering to impulsive purchases that only result in a filled refrigerator, often with mismatched random ingredients that are hard to combine into one appealing recipe. Meanwhile, those who do put effort in grocery planning may lack inspiration after some time or would like to minimize time efforts. Also, individuals with special dietary needs and allergies face significant obstacles in following a healthy customized diet, they might need to seek professional nutritionist advice which can be costly.
This program, aims to tackle all these problems by promoting healthy customized practices which minimize trips to the grocery shop, decrease food waste, foster cooking creativity, and enable free educational insights on nutritional contents. By offering an extensive selection of various recipes fitting every need, it facilitates meal planning and saves valuable time and mon-ey.
# 	Checklist for users to get started with the project
To make use of the code, the following prerequisites must be checked out:
-	Access to a Python distribution package with interactive Jupyter Python Notebook
-	Open file:
o	Cookbook_project_FINAL_VERSION.ipynb –Jupyter notebooks
-	Valid API secret key provided separately:
o	Spoonacular enables free access to API keys which have limited request capacity. 
# Running the code
This project interacts with an API accessed via a Web resource through Hypertext Transfer Pro-tocol, the latter enables to query data through GET method and it returns a response from the specified URL based on the provided parameters.
# HTTP Library
To send GET HTTP requests the “request” library must be imported which facilitates the usage of multiple methods, like get, post, delete, requests and head from the specified URL.
When interacting with an API through HTTP GET requests the delivered responses might not always be successful, therefore the .exceptions module contains several classes to handle these unsuccessful responses. 
-	HTTPError is raised when the request reaches the server, but the server is not able to smoothly process it and returns an error which could be due to several issues. Exam-ples, include Client Error responses or Server Error responses. 
-	ConnectionError is raised when there are problems related to connecting with the server. 
-	Timeout is raised whenever the response is not processed within a certain time frame.
# 	API & API key
The Spoonacular API provides an encrypted key which enables user authentication, to prevent misuse and control the number of interactions with the API. Coder’s best practice is not to disclose the secret key within the hardcode, therefore the key is provided separately for security reasons, and it must be copied and pasted into the code line with api_key='' variable.
# 	HTTP GET request & API documentation
The function get_recipe_information(), is at the heart of the program. It enables interaction with the API, which normally starts from a client sending a GET request to the server, with cer-tain specifications. This server-client communication only works with pre-defined rules and protocols and usually most APIs provide a specific unique documentation which illustrates possible requests and parameters that can be queried.The Spoonacular API’s documentation provides numerous query possibilities and customizable specifications, such as nutritional information about the recipes. It further provides clear and detailed instructions on the functions, endpoints, and responses, enabling a smooth and easier usage of the API 
# Response 
The code block within the get_recipe_information() function, executes and processes a re-sponse from the server. Responses are the result of a correct communication process, which needs to be designed to be understood by the server API and require a correctly formulated specification. For this purpose, the URL, known as the endpoint, specified in the API’s docu-mentation, is stored in info_url variable which inserts the queried parameters for the search into the placeholders, and functions as address in which to look for the parameters. The response will be stored in the variable response which calls the get method of the request’s library to send a get request to the specified endpoint and parameters stored in info_url.
If the response is successfully processed by the server it will conventionally result in JavaScript Object Notation, i.e .JSON response. Its compatibility with web services, and human readability, enables JSON data to be interpreted and generated in any programming language.
# error handling
The responses for the queries might not always be successful as several errors may occur in the process. The try and except are used to handle these possible errors which may occur during a client-server communication such as network connection errors, protocol communication er-rors, impossibility to retrieve the queried data and other errors which will return None to the function’s call.
# Second Get request by ingredients
The second formulated get request is fundamentally structured in the same manner, but it dif-fers in its query, to the extent that it communicates with a different endpoint, with different pa-rameters, to retrieve a maximum number of recipes based on ingredients.
# input from the user
This part of the code is meant to give flexibility to the user, letting him decide if the nutrition data should be inserted in the recipe search. Finally enabling to retrieve the detailed recipe info with nutritional data and disclose missing ingredients as well.
