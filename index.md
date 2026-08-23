# Privacy Policy — Mockation

**Last updated:** 23 August 2026

Mockation is an Android location-mocking utility for developers and QA testers. This policy
explains what the app does with your data. It is short because the app does very little: it has
no accounts, no analytics, no advertising, and no server of its own.

## What Mockation stores

Everything below is written to a private `SharedPreferences` file inside the app's own sandbox
on your device. Nothing is uploaded to us, and we operate no servers.

| Data | Why | Where it lives |
| --- | --- | --- |
| Saved places — name, category, colour, latitude, longitude | So you can re-apply a location with one tap | On your device only |
| Category names you create | The tag vocabulary shown on saved places | On your device only |
| App settings — theme, dynamic colour, jitter, default timer | To restore your preferences | On your device only |
| Which saved places you mocked most recently | To fill the three shortcuts on the app icon's long-press menu | On your device only |

Uninstalling the app deletes all of it. You can also delete individual saved places from the
Saved screen at any time.

## Place names on your home screen

If you add a Mockation widget, or use the app icon's long-press menu, your launcher draws the
saved place names — and, while a mock is running, its coordinates — outside the app. That text
is then visible to anyone looking at the phone, including on the lock screen if your launcher
shows widgets there. Remove the widget to stop it. Nothing is transmitted either way.

## What Mockation does **not** do

- It does not collect or transmit your device's **real** location. The app reads your real
  position in exactly one place — when you tap the "my location" button on the map screen, to
  centre the map on you. That reading is used to draw the map and nothing else: it is not
  saved, not logged, and not sent anywhere. Everywhere else the app only *writes* to the
  Android test-location providers.
- It contains no analytics, crash-reporting, advertising, or tracking SDKs.
- It has no user accounts and asks for no personal information.
- It does not share or sell any data, because it never receives any.

## The network requests the app makes

### Map tiles

The "Pick on a map" screen draws [OpenStreetMap](https://www.openstreetmap.org/) tiles, which
are downloaded from the OpenStreetMap Foundation's tile servers as you pan and zoom. Like any
map, this means the servers see your device's IP address and which part of the world you are
looking at — including, if you use the "my location" button, the area around you. No account,
identifier or coordinate of yours is attached to those requests. The Foundation's handling of
them is covered by the
[OSMF Privacy Policy](https://wiki.osmfoundation.org/wiki/Privacy_Policy). Tiles are cached
inside the app's own sandbox and are deleted with the app.

### Shortened Google Maps links

If you paste a shortened Google Maps link (`goo.gl` or `maps.app.goo.gl`) into the "Add from
link" screen, Mockation follows that link's redirects in order to read the coordinates out of the
full URL. This sends the link you pasted to Google's servers, exactly as opening it in a browser
would; Google's handling of that request is covered by
[Google's Privacy Policy](https://policies.google.com/privacy).

No other network request is made. Coordinates you type, paste, or pin on the map never leave
the device.

## Backups

Saved places are **excluded from Android cloud backup**, so your coordinates are not copied to
Google Drive. They are included in direct device-to-device transfer, so they survive moving to a
new phone without passing through any server.

## Permissions

| Permission | Why it is needed |
| --- | --- |
| `ACCESS_FINE_LOCATION` / `ACCESS_COARSE_LOCATION` | Two things: Android requires a location permission before an app may run a foreground service of type `location`, which is what keeps mocking alive; and the map screen's "my location" button uses it to centre the map on you, when you tap it. |
| `ACCESS_MOCK_LOCATION` | Not grantable to a normal app. Its only effect is to list Mockation under *Developer options → Select mock location app*. Mocking does nothing until you choose Mockation there yourself. |
| `FOREGROUND_SERVICE` / `FOREGROUND_SERVICE_LOCATION` | Keeps the mocked fix being re-applied while you use other apps. Android requires a visible, non-dismissable notification for the whole time this runs. |
| `POST_NOTIFICATIONS` | To show that required notification on Android 13 and newer. |
| `INTERNET` | To download map tiles and to resolve shortened Google Maps links, as described above. |
| `ACCESS_NETWORK_STATE` | The map checks whether the device is online before asking for a tile. |

## Children

Mockation is a developer tool and is not directed at children. We do not knowingly collect
information from anyone, of any age.

## Responsible use

Mock locations are for testing software you are authorised to test. Misrepresenting your location
to a third-party service may breach that service's terms and, in some places, the law. You are
responsible for how you use the app.

## Changes to this policy

If this policy changes, the "Last updated" date above changes with it, and the new version
replaces this one at the same URL.

## Contact

Questions about this policy: `android8giga@gmail.com`
