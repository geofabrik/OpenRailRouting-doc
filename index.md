# GraphHopper Directions API

With the [ GraphHopper Directions API](https://graphhopper.com/#directions-api) you get reliable and fast web services for routing and more
with world wide coverage. We offer A-to-B routing via the Routing API optionally with turn instructions and elevation data as well as 
route optimization with various constraints like time window and capacity restrictions. Also it is possible to get all distances 
between all locations with our fast Matrix API.

The GraphHopper Directions API consists of the following parts:

 * the [Routing API](./routing.md), 
 * the [Map Matching API](./map-matching.md),

## How to Start

 1. To use the Directions API you need an API key. Get it for free [here](https://graphhopper.com/#directions-api).
 2. Read the documentation below or try the examples in our dashboard.
 3. To increase your query limits for production you pay online within a few minutes via credit card or debit advice.

You can see the Routing and Geocoding API in action at [GraphHopper Maps](https://graphhopper.com/maps). You can see the Route Optimization API in action in the [route editor](https://graphhopper.com/blog/2015/07/21/graphhoppers-new-route-optimization-editor/) available in the [dashboard](https://graphhopper.com/#directions-api), the route optimization uses the Matrix API under the hood.

## API Clients and Examples

 * [JavaScript client](https://github.com/graphhopper/directions-api-js-client) - try the [live examples](https://graphhopper.com/api/1/examples/)
 * [Java client](https://github.com/graphhopper/directions-api-java-client)
 * [Others](https://github.com/graphhopper/directions-api-clients-route-optimization) like C#, Ruby, PHP, Python, ... automatically created for the Route Optimization API with our [swagger spec](https://graphhopper.com/api/1/swagger.json).

Let us know your language requirements!
  
**Examples and Applications and Community supported clients**:

 * [Showcases](https://www.graphhopper.com/showcases/) from our customers
 * A community developed Swift client for the [Geocoding API](https://github.com/rmnblm/GraphHopperGeocoder) and [Routing API](https://github.com/rmnblm/GraphHopperRouting)

Do not hesitate to share your websites, apps or API clients with us!

## Keep up-to-date

To get informed about the newest features and development follow us at [twitter](https://twitter.com/graphhopper/) or our [blog](https://graphhopper.com/blog/). Furthermore you can watch [this git repository](https://github.com/graphhopper/directions-api) of this documentation, sign up at our [dashboard](https://graphhopper.com/dashboard/) to get the newsletter or sign up at [our forum](https://discuss.graphhopper.com/c/directions-api). Pick the channel you like most.

# [Routing API](./routing.md)

[![Routing Example](./img/routing-example.png)](./routing.md)

The Routing API is documented [here](./routing.md).

# [Map Matching API](./map-matching.md)

[![Map Matching Example](./img/map-matching-example.png)](./map-matching.md)

The Map Matching API is documented [here](./map-matching.md)

# [Attribution](./attribution.md)

Please read more about how to attribution the usage of the GraphHopper
Directions API [here](./attribution).

# HTTP Error codes

HTTP error code | Reason
:---------------|:------------
400             | Something was wrong in your request. Too few or too many points. ..
401             | Authentication necessary
413             | Too many parameters in the URL, you'll have to use the JSON format and POST requests
429             | API limit reached, you'll also get an email about this, and the header properties will give you more information. See the section about 'HTTP Headers'.
500             | Internal server error. We get automatically a notification and will try to fix this fast.
501 	           | Only a special list of vehicles is supported


## Error Output
```json
{
  "message": "Cannot find point 2: 2248.224673, 3.867187",
  "hints": [{"message": "something", ...}]
}
```

Sometimes a point can be "off the road" and you'll get 'cannot find point', this normally does not
indicate a bug in the routing engine and is expected to a certain degree if too far away.

JSON path/attribute    | Description
:----------------------|:------------
message                | Not intended to be displayed to the user as it is currently not translated
hints                  | An optional list of details regarding the error message e.g. `[{"message": "first error message in hints"}]`
