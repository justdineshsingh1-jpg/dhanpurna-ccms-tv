Dhanpurna CCMS — Live Field Tracking

Files
- index.html: the web app
- data.csv: the shared survey inventory (39,883 coordinate rows)
- data-embedded.js: an included fallback copy for direct/local page opening
- vendor/: bundled Leaflet and Papa Parse libraries

Automatic loading and sharing
1. Extract the entire ZIP and keep all files, including data-embedded.js and
   vendor/, together.
2. You can open index.html directly from the extracted folder. If the browser
   blocks reading a sibling CSV, the app automatically loads the included
   fallback survey data; no manual upload is needed.
3. For sharing, deploy index.html, data.csv, data-embedded.js, and vendor/ to
   the same location on an approved HTTPS web host. The app loads the hosted
   data.csv automatically and uses the included data as a fallback.
4. Use “Share TV link” to copy a link with the current filters, map layer, and
   presentation settings. The receiving device loads the survey data on open.
5. To publish new survey data, replace the hosted data.csv, then use “Refresh
   CSV” in the app. “Replace CSV” is only a local preview in this browser; it
   does not publish or sync the update to other devices.

The fallback copy is a backup of this ZIP's data.csv. Regenerate the ZIP to
refresh the fallback when packaging a new survey export. Map tiles still need
internet access.

The map starts with light and panel locations visible. Light points use a clean
glowing bulb marker. Click a panel or choose one from search to trace its feeder:
the road-aligned route follows the survey order and animates a moving electric
pulse. Click any visible point for details. Use Map/Satellite to switch imagery.

Restrict the hosted app to the intended audience. The CSV contains precise
locations, surveyor names, and photo links. Anyone with access to the host may
be able to access the data.

CSV columns recognized include Lat, Long; Item (Light Fitting/Panel);
Panel No. / Location; Name of Bye Lane/Road; Light Status; Photo Link; and
survey timestamp. CSV parsing runs in a background worker, and points are drawn
on an interactive canvas rather than as one DOM marker per point.