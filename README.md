# REST connector - POST request

This example demonstrate how to perform a REST API POST call using Bonita REST connector.
The answer is parsed and stored in an temporary object by Bonita. Example demonstrate how to use this object to store some information received in the POST request answer in a business variable.
Information can then be used later in the process execution for example to define gateway outgoing transitions conditions.

Note that if you don't need to use the data as part of process execution maybe performing the REST API directly from Bonita form is a better alternative. You can take a look at [another example](https://github.com/Bonitasoft-Community/rest-api-call-from-bonita-form) to understand how to do REST call from Bonia forms.

If you need to process the result of the REST API call as part of your process execution (for example use it in gateway condition or as input for a connector) you should rather use the REST connector. [Another example](https://github.com/Bonitasoft-Community/rest-connector-to-business-data) is available to demonstrate this alternative. 

## Use this example
You can download the .bos file from the release section and import this file in your own Studio workspace.

## More details about the example

Connector that performs the REST POST API call is configured to be executed when process instance is created (i.e. after user submit the instantiation form).
The HTTP response will be a JSON payload: `{"id": 101}` (example use a public REST API). This payload is parsed and a Java object (`bodyAsObject`) is created to make it's manipulation easier. Output of the connector use `bodyAsObject.id` to access the information and store it in a business variable (`storageForRESTAnswer`). 
