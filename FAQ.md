## Where can I get help?

Post your issue to the public [OSM-Dev mailing list](https://lists.openstreetmap.org/listinfo/dev) (subscription of the mailing list required). Paid support is available by [Geofabrik](https://www.geofabrik.de/).

If it is a GraphHopper issue, you might consider asking at the public [GraphHopper forum](https://discuss.graphhopper.com/c/directions-api).

## What happens if I go over the location limit?

Location limits are hard limits and you'll get an error e.g. for the Routing API (max. via points) or for the Map Matching API (max. measurements).

## What are the usage fees and the rate limits?

They depend on the operator of the API instance you use. Please get in toch with them.

## Where can I find the documentation or some demos?

Our documentation is available [here](./index.md) and some demos are available for [every client](./index.md#api-clients-and-examples).

## A route is wrong or takes too long. How can I fix this?

We are using [OpenStreetMap](https://www.openstreetmap.org) data and rely on the provided information there.
The nice thing is: if there is a railway track missing, you can edit this data when you have local knowledge at
openstreetmap.org or put a note there so that others fix or investigate it for you. Please mind not to use internal or proprietary data!

## How long does it take after I updated the data on OpenStreetMap.org?

This depends how often the operator of the API instance you use updates their data but likely at least one day.

## Do I need to link or mention the use of the OpenRailRouting API

Yes, please see [here](./attribution.md) for more details about it. Attribution to OpenStreetMap is always mandatory, exceptions are not possible.
