[README.md](https://github.com/user-attachments/files/28265763/README.md)
# Model Context Protocol (MCP) Project
[![Python 3.9](https://img.shields.io/badge/Python-3.9-blue)](https://www.python.org/downloads/release/python-390/)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](LICENSE)

## Project Description

The Model Context Protocol (MCP) project is a Python-based application that utilizes the MCP framework to interact with language models. The project's primary function is to handle callbacks from the MCP framework, specifically logging queries to the model and responses from the model. The architecture of the project is designed to be modular, allowing for easy extension and modification of its components.

The project consists of several key components:

* `callback_logging.py`: This module contains functions for logging queries to the model and responses from the model.
* `adk_utils`: This package contains utility functions for working with the MCP framework.

The project uses the MCP framework to interact with language models, and it relies on the `google.cloud.logging` library to log events.

## Key Features

The following are the key features of the project:

* Logging of queries to the model: The project logs queries to the model, including the user's input and the model's response.
* Logging of responses from the model: The project logs responses from the model, including the model's output and any function calls.
* Modular architecture: The project's architecture is designed to be modular, allowing for easy extension and modification of its components.
* Integration with Google Cloud Logging: The project uses the `google.cloud.logging` library to log events to Google Cloud Logging.

## Prerequisites

To use the project, you will need to have the following prerequisites:

* Python 3.9 or later
* Google Cloud account with the Cloud Logging API enabled
* `mcp` library version 1.10.1 or later
* `lxml` and `beautifulsoup4` libraries

## Installation

To install the project, follow these steps:

1. Install the required libraries by running `pip install -r requirements.txt`
2. Set up your Google Cloud account and enable the Cloud Logging API
3. Install the `google-cloud-logging` library by running `pip install google-cloud-logging`

## Configuration

To configure the project, you will need to set the following environment variables:

* `GOOGLE_CLOUD_PROJECT`: The ID of your Google Cloud project
* `GOOGLE_CLOUD_LOGGING_KEY`: The key for your Google Cloud Logging API

You can set these environment variables by running the following commands:
```bash
export GOOGLE_CLOUD_PROJECT=your_project_id
export GOOGLE_CLOUD_LOGGING_KEY=your_logging_key
```
## Usage

To use the project, you can import the `log_query_to_model` and `log_model_response` functions from the `callback_logging` module. Here is an example of how to use these functions:
```python
from callback_logging import log_query_to_model, log_model_response

# Create a CallbackContext object
callback_context = CallbackContext(agent_name="my_agent")

# Create an LlmRequest object
llm_request = LlmRequest(contents=[{"role": "user", "parts": [{"text": "Hello, world!"}]}])

# Log the query to the model
log_query_to_model(callback_context, llm_request)

# Create an LlmResponse object
llm_response = LlmResponse(content={"parts": [{"text": "Hello, world!"}]}])

# Log the response from the model
log_model_response(callback_context, llm_response)
```
## API Reference

The following are the functions and classes in the project, along with their parameters and return values:

* `log_query_to_model(callback_context: CallbackContext, llm_request: LlmRequest)`: Logs a query to the model.
	+ `callback_context`: The CallbackContext object.
	+ `llm_request`: The LlmRequest object.
	+ Returns: None
* `log_model_response(callback_context: CallbackContext, llm_response: LlmResponse)`: Logs a response from the model.
	+ `callback_context`: The CallbackContext object.
	+ `llm_response`: The LlmResponse object.
	+ Returns: None
* `CallbackContext`: A class representing the callback context.
	+ `agent_name`: The name of the agent.
* `LlmRequest`: A class representing an LLM request.
	+ `contents`: A list of content objects.
* `LlmResponse`: A class representing an LLM response.
	+ `content`: A content object.

## Project Structure

The project consists of the following files and folders:

* `callback_logging.py`: A module containing functions for logging queries to the model and responses from the model.
* `adk_utils`: A package containing utility functions for working with the MCP framework.
* `requirements.txt`: A file listing the required libraries.
* `README.md`: This file, containing information about the project.

## Contributing

To contribute to the project, please fork the repository and submit a pull request. Please ensure that your code is formatted according to the project's coding standards and that you have included tests for any new functionality.

## License

The project is licensed under the ISC license. See the `LICENSE` file for more information.
