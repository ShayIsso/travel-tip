# TravelTip
#### The app that gets you somewhere


## Description
TravelTip is an app that keeps a list of favorite locations

## Main Features
- The app allows the user to keep and manage locations
- The user can also search for an address and pan the map to that point
- The User can pan the map to his own geo-location
- Shows distance to locations when user position is known
- Modern dialog modal for adding and updating locations
- Advanced grouping by last update time (today, past, never)
- Text filtering that includes location address
- Enhanced sorting capabilities including creation time

## Locations CRUDL 
- Create – Use a modern dialog modal to add new locations with name and rate
- Read – Selected location details including distance from user (when available)
- Update – Update location details using a dialog modal
- Delete – Remove locations with confirmation prompt
- List - Including filtering, sorting (by creation time/rate) and grouping (by last update)

## Selected Location
- Displayed in the header
- Location is active in the list (gold color)
- Marker on the map
- Shows distance from user's position when available
- Reflected in query params 
- Copy url to clipboard
- Share via Web-Share API

## Location
Here is the format of the location object:
```js
{
    id: 'GEouN',
    name: 'Dahab, Egypt',
    rate: 5,
    geo: {
      address: 'Dahab, South Sinai, Egypt',
      lat: 28.5096676,
      lng: 34.5165187,
      zoom: 11
    },
    createdAt: 1706562160181,
    updatedAt: 1706562160181
  }
  ```
## Services
```js
export const locService = {
    query,
    getById,
    remove,
    save,
    setFilterBy,
    setSortBy,
    getLocCountByRateMap,
    getLocCountByLastUpdateMap
}

export const mapService = {
    initMap,
    getPosition,
    setMarker,
    panTo,
    lookupAddressGeo,
    addClickListener
}
```

## Controller
```js
// To make things easier in this project structure 
// functions that are called from DOM are defined on a global app object

window.app = {
    onRemoveLoc,
    onUpdateLoc,
    onSelectLoc,
    onPanToUserPos,
    onSearchAddress,
    onCopyLoc,
    onShareLoc,
    onSetSortBy,
    onSetFilterBy,
    onSaveLoc
}
```

Here is a sample usage:
```html
<button onclick="app.onCopyLoc()">Copy location</button>
<button onclick="app.onShareLoc()">Share location</button>
```


