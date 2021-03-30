# OpenRailRouting REST API

With the OpenRailRouting REST API you get reliable and fast web services for routing and more
with world wide coverage. We offer A-to-B routing via the Routing API optionally with turn instructions and elevation data as well as 
route optimization with various constraints like time window and capacity restrictions.

The OpenRailRouting REST API consists of the following parts:

 * the [Routing API](./routing.md), 
 * the [Map Matching API](./map-matching.md),

## API Clients and Examples

 * [JavaScript client](https://github.com/graphhopper/directions-api-js-client) - try the [live examples](https://graphhopper.com/api/1/examples/)
 * [Java client](https://github.com/graphhopper/directions-api-java-client)
 * [Others](https://github.com/graphhopper/directions-api-clients-route-optimization) like C#, Ruby, PHP, Python, ... automatically created for the Route Optimization API with our [swagger spec](https://graphhopper.com/api/1/swagger.json).

Let us know your language requirements!
  
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
