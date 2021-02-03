## Parcel Bundler Test

Currently the API doesn't work when built with Parcel.

Error in build file is:

```
parcel-arcgis.e31bb0bc.js:37 Uncaught (in promise) Error: Cannot find module 'PortalUser.98913075.js,node_modules/@arcgis/core/portal/PortalUser.js,PortalUser.98913075.js.map,node_modules/@arcgis/core/portal/PortalUser.js'
    at newRequire (parcel-arcgis.e31bb0bc.js:37)
    at newRequire (request.ae17d849.js:29)
    at newRequire (PortalItem.1552a7d1.js:29)
    at newRequire (parcel-arcgis.e31bb0bc.js:21)
    at localRequire (parcel-arcgis.e31bb0bc.js:53)
    at Object.parcelRequire.node_modules/@arcgis/core/portal/Portal.js.../chunks/tslib.es6.js (Portal.js:5)
    at newRequire (parcel-arcgis.e31bb0bc.js:47)
    at newRequire (request.ae17d849.js:29)
    at newRequire (PortalItem.1552a7d1.js:29)
    at newRequire (PortalItem.1552a7d1.js:21)
```

Not sure what could be causing the error.

There's a line of code in the entry file that looks like this.

```js
"./PortalQueryResult.js":"XSRi","./PortalUser.js":[["PortalUser.ad7103ec.js","D2K1"],"PortalUser.ad7103ec.js.map","D2K1"]
```

I can verify the file it's looking for exists, so not sure what the problem is.

## App

This app uses [`parcel-plugin-static-files-copy`](https://www.npmjs.com/package/parcel-plugin-static-files-copy) to copy the `@arcgis/core/assets` folder to the build directory.
