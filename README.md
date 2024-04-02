# Wiremock Deployment Example

This provides one example of how a wiremock service can be packaged for deployment to an azure web app.

Whether you use a deployed app, a standalone instance running locally, or run an instance of wiremock directly in your code is a matter of choosing the best design for the purpose at hand.

See https://github.com/WireMock-Net/WireMock.Net/wiki for an outline of the different use cases (unit tesing, standalone and deployed)

Using this app you will get:
- A web application with configurable responses as defined by the json files in the `__admin\mappings` folder in the repo
- Automatic recording of requests recieved at the stub, which can be accessed from the `http://localhost:5161/__admin/requests` endpoint
- A starting point for using more advanced features of wiremock.
