# Earthquakes around Japan

Every earthquake of magnitude 4.0 and above around Japan between 2016 and 2026 —
**14,568 of them** — on one map, in one file.

### → **https://kreativitea.github.io/kg-class-demo/**

Or download `index.html` and double-click it. There is no build step, no server
and nothing to install.

## The two encodings

**Size is magnitude.** The radius grows 2.45× per magnitude step, so the rare
large quakes are unmissable rather than merely a bit bigger:

| M4 | M5 | M6 | M7 | M7.6 |
|---|---|---|---|---|
| 1 px | 2.5 px | 6 px | 15 px | 25 px |

That is about 630× the area between an M4 and the M7.6. It has to be that steep:
90% of this catalogue is under M5, so a gentle curve loses the big ones in the
crowd. Anything past 6 px is drawn as a ring rather than a solid disc, so a large
circle doesn't hide what sits underneath it.

**Colour is depth**, as a full rainbow from red through green and blue to
magenta. The colour stops are deliberately *not* evenly spaced in kilometres —
they sit at 0, 15, 30, 50, 80, 130, 250, 450 and 700 km. Two thirds of these
quakes are shallower than 50 km, so a scale that was linear in depth spent its
whole range on the empty deep end and painted the map a single shade of red.
Crowding the stops where the data actually is spends the rainbow where it can
be seen.

Together the two make the subduction zone readable without a word of
explanation: hot colours along the trench to the east, cooling and then
shifting through blue to magenta as the Pacific plate dives westward under the
arc.

## Play it

**Play** — or the space bar — runs a clock through the decade and lets each
quake strike at the moment it actually did, building the map up as it goes.
1× covers the ten years in about 50 seconds; 2× and 4× sit next to it.

Only M5.5 and up throw an expanding ring. Japan gets roughly 1,150 M4+
earthquakes a year, so at any watchable speed ringing every one of them is just
noise — about 8 rings a second is punctuation you can follow, over a field of
smaller quakes that flash as they land.

The catalogue is stored to the **hour**, so aftershock sequences arrive in their
real order. Watch 1 January 2024: the Noto Peninsula M7.5 is still ringing while
its M6.5, M6.2, M6.1, M5.9 and M5.8 aftershocks fire around it.

## Cross-section

**Cross-section** slices the region and shows the same earthquakes *from the
side*. It shares the map's horizontal scale, so a feature on the map sits
directly above its own depth profile — which is where the slab stops being a
colour gradient and becomes a line running from the trench down to 500 km.

Drag the pale band on the map to move the slice. The grey bar at the top of the
section marks where the slice crosses land.

## Other things to try

- Set **depth** to 200–700 km. The shallow noise vanishes and the subducting
  slab is left on its own — the clearest single view in the file.
- Scroll to zoom, drag to pan, hover any circle for magnitude, depth, place
  and date.

## 日本語

Press **`j`**, or use the EN / 日本語 switch, and the page changes language in
place. The choice is remembered.

English is the source. Prose is translated; the attribution line and the USGS
place names stay English in both, which is the convention the course repo this
came from uses throughout.

## One file, no network

A single `index.html`: no libraries, no map tiles, no build step, and no
requests at run time. The earthquake catalogue and the coastlines are written
into the file as data, so it works with the wifi off and looks identical every
time. That costs about 680 KB, of which three lines are data and the rest is
readable source.

## Data

- **Earthquakes** — the [USGS Earthquake Hazards Program](https://earthquake.usgs.gov),
  M4.0+, 22–48°N and 121–151°E, 2016-01-01 to 2026-09-04. A work of the US
  federal government, so not subject to copyright. The exact query is in a
  comment at the top of `index.html`; re-run it with a later end date to refresh
  the snapshot.
- **Coastlines** — [Natural Earth](https://www.naturalearthdata.com) 10m land,
  public domain, clipped to the map's box and simplified to about 1 km.

Neither source carries terms that restrict this. Worth remembering that the file
*embeds* the data rather than fetching it, which is a stronger act than linking —
so check the terms again if either source is ever swapped for one that has them.

## Licence

Not chosen yet for the code, which means all rights reserved by default. The two
data sources above carry their own terms and are unaffected.
