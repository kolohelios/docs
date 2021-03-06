# Cloud Functions

Cloud Functions allow you to run custom app logic on your Parse Server. This is especially useful for running complex app logic in the cloud so that you can reduce the memory footprint of your code on the IoT device. In a Cloud Function, you can query/save Parse data, send push notifications, and log analytics events.

You write your Cloud Code in JavaScript using the Parse JavaScript SDK. We provide a command-line tool to help you deploy your Cloud Code. See our [Cloud Code guide]({{ site.baseUrl }}/cloudcode/guide) for details.

For example, you define a Cloud Function as below.

```javascript
Parse.Cloud.define("hello", function(request, response) {
	response.success(request.body);
});
```

Then you can invoke this Cloud Function from your device:

```cpp
ParseCloudFunction cloudFunction;
cloudFunction.setFunctionName("hello");
cloudFunction.add("value", "echo from hello");
ParseResponse response = cloudFunction.send();
```
