function sendGraphQLMutation() {
  var headers = {};
  headers['Content-Type'] = 'application/json';
  headers['Authorization'] = 'Bearer <YOUR_API_KEY>';

  var body = JSON.stringify({
    query: "mutation DeviceRxChannelsSubscriptionSet($input: DeviceRxChannelsSubscriptionSetInput!) {\n  DeviceRxChannelsSubscriptionSet(input: $input) {\n    ok\n  }\n}",
    variables: {
      input: {
        deviceId: "<YOUR_DEVICE_ID>",
        subscriptions: [
          {rxChannelId: 1, rxChannelIndex: 1, subscribedDevice: "<SUB_DEVICE_1>", subscribedChannel: "<CHANNEL_1>"},
          // ...more subscription objects as needed
        ]
      }
    }
  });

  ogscript.asyncHTTP(
    "http://localhost:8080/graphql",   // Proxy endpoint for mitmproxy
    "POST",
    headers,
    body,
    function(response) {
      ogscript.log("Status: " + response.status);
      ogscript.log("Body: " + response.body);
    }
  );
}
thisIsTheDashBoardReservedFunctionName();
