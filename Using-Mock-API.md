# Using a Mock API

The API docs use the [OpenAPI format](https://swagger.io/docs/specification/about/) and contain both sample requests and response definitions. This means that you can use the docs as a Mock API, which is useful to simulate requests when developing API-related features.

We suggest the following three ways to consume a mocked version of the ViruSafe API:

1. SwaggerHub ViruSafe Mock API*
2. SwaggerHub self-maintained Mock API
3. Postman Mock API

> 🚧 ***SwaggerHub's API Auto Mocking** has a rate limit of **10 requests per minute** per API version, though sometimes, you may experience a higher throughput. After the limit is reached, you will receive a 429 (Too Many Requests) response to subsequent requests. Consider following the *2. SwaggerHub self-maintained Mock API* approach if this happens (shown below).

If you are still struggling to mock your requests after trying those suggestions, there are a lot of other options to create a Mock API from the source documentation, such as installing Swagger locally or using another OpenAPI mocking tool altogether.

## 1. SwaggerHub ViruSafe Mock API

This is the easiest way and comes out of the box when using SwaggerHub, as they offer an [API Auto Mocking functionality](https://app.swaggerhub.com/help/integrations/api-auto-mocking) that you can use to mock your requests. This is enabled by default, so you only have to call the virtual server generated by SwaggerHub when making requests, for example:

    https://virtserver.swaggerhub.com/ViruSafe/viru-safe_backend_rest_api/1.0.0/personalinfo

*This is the Mock URL for the `POST @ /personalinfo` call.*

As described above, the only downside of this method is that requests are throttled, so in general we suggest adding the collection to your own SwaggerHub account (show below).

## 2. SwaggerHub self-maintained Mock API

When the SwaggerHub ViruSafe Mock API is experiencing heavy load, or when you'd like to modify the mocked API, we suggest that you create an account on SwaggerHub and host your own copy of the API docs there.

Here are the steps:

1. Create a SwaggerHub account
2. Select **Create New** > **Create New API** and create a blank API (make sure Auto Mock remains enabled).
3. Remove the sample code from your new API. To do this, hit `ctrl+a` on the Code Editor *(black window with code)* and delete everything, leaving the Code Editor blank.
4. Copy the [ViruSafe Swagger API Docs](https://api.swaggerhub.com/apis/ViruSafe/viru-safe_backend_rest_api/1.0.0/swagger.yaml) to your clipboard.
5. Paste what you've copied in the Code Editor window *(where you deleted the sample code in step 2)*.
6. Hit the blue **Save** button above the editor. Your API should update and your new Base URL should be visible on the right panel (UI Docs) in the following format: `https://virtserver.swaggerhub.com/{owner}/{api}/{version}`. Copy this new URL and use it in your app. 
7. Consume your newly created ViruSafe Mock API.

## 3. Postman Mock API

[Postman](https://www.postman.com) is yet another great way to get a Mock API for local development - it contains example requests/responses for the endpoints and can also be used as a Mock server:

1. Install Postman
2. Download the ViruSafe Swagger API Docs as `virusafe-swagger.json`
3. Import `virusafe-swagger.json` in Postman - Learn more about [importing in Postman](https://learning.postman.com/docs/postman/collections/data-formats/#importing-postman-data). You only need a collection, so make sure to deselct `Import as an API` when you are importing.
4. Create your Mock API - Learn more about [Mocking with Postman](https://learning.postman.com/docs/postman/mock-servers/mock-with-api/). *There is no need to create it as a private mock, but if you do, you'll need to add an `x-api-key header` to your requests, [see how to generate it here](https://learning.postman.com/docs/postman/postman-api/intro-api/)*.
5. Copy your mock URL (*for example: `https://0f91dec8-a451-40f6-b1d1-6ef802ffbb32.mock.pstmn.io`)*.
6. Update the `baseUrl` variable of your new collection with the value of **your mock URL** from step 4. (go to **Collection Settings** > **Edit** > **Variables**) - Learn More about [Collection Variables in Postman](https://learning.postman.com/docs/postman/variables-and-environments/variables/#defining-collection-variables).
7. Postman doesn't automatically default to response codes in the 2** range, so you'll have to add the `x-mock-response-code` header to every request you want to mock in the mobile apps. The value for the header depends on the request you're mocking - either 200 or 201 (or any other response code that you would like to mock).
8. Consume your newly created ViruSafe Mock API.

For more info on how Mock Examples work with Postman, you can [read this guide](https://learning.postman.com/docs/postman/mock-servers/mocking-with-examples/).