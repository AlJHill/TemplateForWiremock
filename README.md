# Wiremock.net Deployment Example [WIP]

This provides one example of how a wiremock service can be packaged for deployment as an azure web app.

Whether you use a deployed app, a standalone instance running locally, or start an instance of wiremock directly from your code is a matter of choosing the best design for the purpose at hand.

See https://github.com/WireMock-Net/WireMock.Net/wiki for an outline of the different use cases (unit tesing, standalone and deployed)

## 

## Using this app you will get:
- A web application hosting a wiremock instance with configurable responses as defined by the json files in the `__admin\mappings` folder in the repo
- Automatic recording of requests received by the mock. Records of requests can be accessed from the `http://localhost:5161/__admin/requests` endpoint
- A starting point for using more advanced features of wiremock.

## Other considerations
- Consider attaching a blob storage container to the web app at the path `__admin\mappings` where the mappings are held, so that mock behavior can be changed in-flight 

## Example mappings

- The example mappings in this template are set so that:
    - At the endpoint `/my_stub_endpoint`, POST requests not matching other rules should be given a 200 OK response. 
    - To demonstrate request matching, If the POST request to `/my_stub_mapping` contained an XML body:
        `<PRODUCTNAME>000XX5</PRODUCTNAME>` with `XX5` in `<PRODUCTNAME>`, the server is set to return a 500 Server Error.  With `XX0` in the product name, the server is set to delay a 200 OK response by 10 seconds.
