# module: "location"

`location` module provides device location APIs.

# location.available()

Check whether location service is available:

```js
const location = require("location");
if (location.available()) {

}
```

# location.fetch() -> Promise

Get the current location:

```js
const location = require("location");
location.fetch().then(result => {
  const latitude = result.lat;
  const longitude = result.lng;
  const altitude = result.alt;
});
```

It returns latitude, longitude, and altitude.

# location.startUpdates(object)

Start observing the location updates:

```js
const location = require("location");
location.startUpdates({
  once: false
}，result => {
  // lat, lng, alt
});
```

`once` indicates whether stop after the first result is returned.

# location.trackHeading(object)

Track heading changes:

```js
const location = require("location");
location.trackHeading(result => {
  const magneticHeading = result.magneticHeading;
  const trueHeading = result.trueHeading;
  const headingAccuracy = result.headingAccuracy;
  const x = result.x;
  const y = result.y;
  const z = result.z;
});
```

# location.stopUpdates()

Stop location updates:

```js
const location = require("location");
location.stopUpdates();
```

# location.select() -> Promise

Select a location using the JSBox built-in map component:

```js
const location = require("location");
location.select().then(result => {
  const latitude = result.lat;
  const longitude = result.lng;
});
```