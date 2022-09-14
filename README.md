# Welcome

This sample application demonstrates the implementation of a FusionFabric.cloud SPI. To learn more about SPIs, see [FusionCreator Documentation](https://developer.fusionfabric.cloud/documentation/spi-implementation).

**To run this sample**

> You must have a recent installation of [Java](https://www.java.com/en/) on your machine. Also, an OAuth2 client is required, such as [Postman](https://www.postman.com/).

1. Clone the current project.
2. Run this sample app with Maven:

```sh
mvn spring-boot:run
```

3. (Optional) If you don't have Maven installed on your machine, run this sample with **mvnw**:

```sh
mvnw spring-boot:run
```

The sample application is running on http://localhost:9000

**To call the endpoint implemented by this sample**

1. Register an application on [**Fusion**Fabric.cloud Developer Portal](https://developer.fusionfabric.cloud), and include the [Sample SPI](https://developer.fusionfabric.cloud/api/sample-spi-v1-0504c686-15d4-4002-bc11-8c1791807fa4/docs) SPI in the **SPIs** tab. Use any valid URLs for the _SPI Base URL_, as you will not use them during working with this sample.
2. Generate a secret key for the B2B channel. See [Documentation](https://developer.fusionfabric.cloud/documentation/get-started/postman-client-credentials) for details.
3. Download the Sample SPI Postman collection from the **Actions** menu on [Sample SPI reference documentation page](https://developer.fusionfabric.cloud/api/sample-spi-v1-0504c686-15d4-4002-bc11-8c1791807fa4/docs).
4. In Postman, import the collection file previously downloaded.
5. Edit the Postman collection **Variables** and provide the values for:
   - `client_id` and `client_secret` - the client ID and the secret key generated at step 2
   - `sample-spi-url` - use http://localhost:9000. This is the base URL of this sample application running locally on your machine.
6. Generate an access token to authorize the call using Oauth2 - Client Credentials. Refer [Documentation](https://developer.fusionfabric.cloud/documentation/get-started/postman-client-credentials).
7. Call the implementation of the [`POST` `/day-of-week`](https://developer.fusionfabric.cloud/api/sample-spi-v1-0504c686-15d4-4002-bc11-8c1791807fa4/docs#operation/dayOfWeek) endpoint. Edit the request body and update the date to any valid/invalid date and test the response.

Please note,

- Use SPI structure as below while testing the implementation hosted at your end:  
  `https://{base-url}/sample/spi/v1/day-of-week`<br/>
  For example: https://**localhost:9000**/sample/spi/v1/day-of-week
- The requests made through this sample SPI project with URL structure as above will not go through FusionFabric.cloud server. The purpose of this sample project is to provide a simulation of the workflow. As mentioned in the steps above, the token retrieved through FusionFabric.cloud server will be sent to localhost:9000 while making a call for verifying access token claims. You can check the sample code for access token validation in “Security” folder at path:<br/>
  https://github.com/fusionfabric/ffdc-sample-spi/tree/master/src/main/java/com/finastra/spi/dayofweek/security
- In real-time integration with financial institution client, fintech SPI application won’t need to retrieve the token, but access token claims validation would be necessary.
- For more details on SPI, understanding validation of access token and summary of the process, click [here](https://developer.fusionfabric.cloud/documentation/platform-deep-dive/spi-implementation).

This sample application is released under the MIT License. See [LICENSE](LICENSE) for details.