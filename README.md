# Earthquakes around Japan

Every earthquake of magnitude 4.0 and above around Japan from 2016 to 2026 —
**14,568 of them** — on one map.

**[Open the map](https://kreativitea.github.io/kg-class-demo/)** · or download
`index.html` and double-click it.

## The two encodings

| | |
|---|---|
| **Size** | magnitude — the radius grows about 1.78× per magnitude step, so an M7 reads as *much* bigger than an M5, not slightly bigger |
| **Colour** | depth — shallow is hot, deep is cool. This is the convention the USGS and the JMA use |

Together they make the subduction zone readable without a word of explanation:
red along the trench to the east, cooling westward as the Pacific plate dives
under the arc.

## Cross-section

The **Cross-section** button slices the region and shows the same earthquakes
*from the side*. It shares the map's horizontal scale, so a feature on the map
sits directly above its own depth profile — which is where the slab stops being
a colour gradient and becomes a line running from the trench down to 500 km.

Drag the pale band on the map to move the slice. The grey bar at the top of the
section marks where the slice crosses land.

## Other things to try

- Set **depth** to 200–700 km. The shallow noise disappears and the slab is left
  on its own — the clearest single view in the file.
- **Play years** sweeps a one-year window through the decade.
- Scroll to zoom, drag to pan, hover any circle for magnitude, depth, place and date.

## One file, no network

This is a single `index.html` with no libraries, no map tiles, no build step and
no requests at run time. The earthquake catalogue and the coastlines are written
into the file as data, so it works with the wifi off and looks identical every
time. That costs 676 KB, of which three lines are data and the rest is readable
source.

## Data

- **Earthquakes** — the [USGS Earthquake Hazards Program](https://earthquake.usgs.gov).
  A work of the US federal government, so not subject to copyright. The exact
  query is in a comment at the top of `index.html`; re-run it with a later end
  date to refresh the snapshot.
- **Coastlines** — [Natural Earth](https://www.naturalearthdata.com) 10m land,
  released into the public domain, clipped to the map's box and simplified to
  about 1 km.

Both are free of terms. Note that this file *embeds* the data rather than
fetching it, which is a stronger act than linking — worth remembering if either
source is ever swapped for one that has real terms.

## Licence

Not yet chosen for the code in this file. Until one is added, it is
"all rights reserved" by default. The two data sources above carry their own
terms and are unaffected.
