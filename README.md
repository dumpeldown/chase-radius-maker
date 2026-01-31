# Chase Radius Maker

Use the webapp here: https://dumpeldown.github.io/chase-radius-maker

A specialized mapping utility designed to calculate and display expanding circular boundaries based on the CHASE adventure format popularized by German adventurer [Roofless Cat](https://www.youtube.com/@RooflessCat).

**Files**
- `index.html` — application UI and logic
- `styles.css` — UI styling

**Features**
- Drag the marker to set the center location.
- Define multiple radii (km) with per-row inputs. Changes apply immediately when the input loses focus.
- Use the per-radius + / − buttons to insert or remove radii; additions default to +150 km above the selected ring.
- Save named presets (stored in `localStorage`) and restore or delete them from the Saved Presets list.
- A code-defined `chasePreset` object in `index.html` is used as the default CHASE PRESET on startup — edit it to set precise center and radii.
- Share the current preset via a URL (`?preset=`) — the app updates the URL automatically when the center or radii change. Use "Copy Share Link" to copy it.
- Non-blocking toast notifications for actions (copy/delete).

**Keyboard / Accessibility Notes**
- Tab focuses the numeric radius inputs only; the +/− buttons are excluded from the tab order but are reachable with the mouse.

**Developer / Local run**
From the project root run a simple static server and open the page in your browser:

```bash
python -m http.server 8000
# then open http://localhost:8000 in your browser
```

**Where to edit the default preset**
Open `index.html` and edit the `chasePreset` object near the top of the script, e.g.:

```js
const chasePreset = {
  center: [48.147738, 11.588859],
  radiiKm: [185, 335, 535, 735, 935]
};
```
