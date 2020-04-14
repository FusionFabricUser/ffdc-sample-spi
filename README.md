# Welcome

This sample application demonstrates the implementation of a FusionFabric.cloud SPI. To learn more about SPIs, see [FusionCreator Documentation](https://developer.fusionfabric.cloud/documentation/spi-implementation). 

**To run this sample**

> You must have a recent installation of [Java](https://www.java.com/en/) on your machine. Also, an OAuth2 client is required, such as [Postman](https://www.postman.com/). 


1. Clone the current project.
2. Run this sample app with Maven:

```sh
mvn spring-boot:run
```
3. (Optional) If you don't have Maven installed on your machine, run this sample with **mvnw**, 
```sh
mvnw spring-boot:run
```
The sample application is running on http://localhost:9000

**To call the endpoint implemented by this sample**

1. Register an application on [**Fusion**Fabric.cloud Developer Portal](https://developer.fusionfabric.cloud), and include the [SPI Sample](https://developer.fusionfabric.cloud/api/spi-sample-v1-0504c686-15d4-4002-bc11-8c1791807fa4/docs) SPI. Use any valid URLs for the reply URL and the base URL, as you will not use them during working with this sample.
2. Generate a secret key for the B2B channel. See [FusionCreator Documentation](https://developer.fusionfabric.cloud/documentation/join-my-dashboard.html#secret-key) for details.
3. In Postman, import the environment file and the collection provided in the **postman** directory.
4. Edit the Postman environment and provide the values for:
   + `client_id` and `client_secret` - the client ID and the secret key generated at step 2
   + `spi-sample-url` - use http://localhost:9000. This is the base URL of this sample application running locally on your machine.  
5. Call the `POST` **APIM fetch token** endpoint. This will request the access token and store it in the `APIM_token` environment variable.
6. Call the `POST` **Call spi-sample with token** endpoint. Alternatively, edit the request body and update the `date` to any valid date. This will call the implementation of the [`POST` `/day-of-week`](https://developer.fusionfabric.cloud/api/spi-sample-v1-0504c686-15d4-4002-bc11-8c1791807fa4/docs#operation/dayOfWeek) endpoint.  


Ths sample application is released under the MIT License. See [LICENSE](LICENSE) for details.