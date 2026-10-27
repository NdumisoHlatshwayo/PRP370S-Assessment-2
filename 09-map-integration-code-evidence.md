# RideConnect Map Integration — Source-Code Evidence

**Student:** Ndumiso Hlatshwayo · **Project:** RideConnect

The RideConnect source-code archive supplied for the portfolio contains the following implementations.

## Native mobile map

**File:** `src/components/RideMap.native.tsx`

- Imports `MapView`, `Marker`, and `PROVIDER_GOOGLE` from `react-native-maps`.
- Imports `expo-location` and requests foreground location permission.
- Reads the device's current location with high accuracy.
- Centres the map on the current location and displays a user-location marker.
- Uses Cape Town (`-33.9249, 18.4241`) as the initial map region.
- Handles denied permissions and location errors.

## Shared map component

**File:** `src/components/RideMap.tsx`

- Renders a `react-native-maps` MapView with a Cape Town initial region.

## Web map and driving directions

**File:** `src/components/RideMap.web.tsx`

- Uses `@react-google-maps/api` components `GoogleMap`, `Marker`, `DirectionsRenderer` and `useJsApiLoader`.
- Reads the Google Maps API key from the `EXPO_PUBLIC_GOOGLE_MAPS_API_KEY` environment variable; **the key value is not published here**.
- Requests browser geolocation and falls back to Cape Town if location retrieval fails.
- Displays a current-location marker and a selected destination marker.
- Provides a test destination and a button to request driving directions via Google Maps DirectionsService.
- Renders returned directions when the service reports success.

## What this establishes

**Confirmed:** Map display, location permission handling, location markers and web route-calculation logic are implemented in the source archive.

**Not established by the source alone:** Whether an API key is configured in a deployed environment, whether routing works on a particular device, or whether live tracking is fully implemented and tested.

## Reflection

Map integration added a location-based feature to the RideConnect codebase and shows the relationship between user-interface design, permissions, mapping services and platform differences. The native and web implementations use different APIs, making it important for the team to test both platforms separately.

The code is summarized rather than uploaded wholesale because the supplied archive includes private configuration files that should not be committed to a public repository.
