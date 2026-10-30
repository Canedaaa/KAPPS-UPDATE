# Kapps Mods for iRacing

A patch for the **Kapps** iRacing overlay that adds new widgets, improves the existing ones and fixes some bugs. Everything is changed inside Kapps itself: you keep using the normal Kapps settings, profiles and overlay.

> This is an unofficial community mod. It is not made or supported by the Kapps developer.

---

## Installation

1. Download **`aplicar_atualizacao.bat`** and **`atualizacao.js`** and put them in the **same folder**.
   - Optional: a folder called **`wheels`** in that same folder, with your own steering wheel images for the Inputs Graph (see below).
2. Double-click **`aplicar_atualizacao.bat`**.
3. Press **1** (or wait 10 seconds) to apply the mods.
4. Wait for **"Done! Mods applied."** and open Kapps again.

What the installer does:
- Finds the newest Kapps version installed on your PC.
- Closes Kapps if it is open.
- Saves a backup of the original Kapps the first time (`app.asar.original-backup`).
- Always applies the mods **on top of the original**, so you can run it again after every update of the mod.
- If something goes wrong, Kapps is left with the **original** file, so it never ends up broken.

You don't need to install Node.js or anything else: the installer uses the Kapps program itself.

### Updating the mod
Download the new `atualizacao.js`, replace the old one and run `aplicar_atualizacao.bat` again.

### After a Kapps update
When Kapps updates itself, the mods are removed. Just run `aplicar_atualizacao.bat` again.

### Removing the mods
Run `aplicar_atualizacao.bat` and press **2 - Restore original Kapps** (or use `restaurar-kapps.bat`).

---

## New widgets

### Wind
- Your car seen from above in the middle (it never moves) and a dark disc around it.
- The **N / E / S / W** letters and the **blue arrow** turn around the car as you drive. The arrow always shows the side the wind is hitting you from.
- Top-right corner: where the wind comes from on the map (N, NE, E, SE, S, SW, W, NW).
- Below: wind speed and where it hits the car (Headwind, Crosswind R/L, Tailwind...).
- Options: **Português** labels, background color and opacity, hide in replay / when iRacing is not running.

### Pit Rejoin
"If I pit **now**, where do I come out?"
- Shows your class position now → after the stop (e.g. **P5 ▶ P8**), plus the car just ahead (▲) and just behind (▼) you at the pit exit, with the gaps.
- Turns red when you would rejoin in traffic (gap smaller than the **Traffic** setting, default 1.5 s).
- **Pit loss** (the time a stop costs you) is learned automatically by the Fuel Calculator every time you stop, saved per track and per series. With nothing learned yet, it uses the value from the settings (default 30 s).
- The Fuel Calculator must be open during a stop to learn the pit loss.
- Hides while you are in the pit lane or off track.
- Limitation: it assumes the other drivers don't pit at the same time.

### Rejoin Helper
- A bubble that shows up when you go off track, spin or stop on track, with the time (in seconds) to the closest car **behind** you.
- **Green / Clear**, **Yellow / Caution** or **Red / Danger**. The limits are set in the settings.
- Only shows if that car is close enough (**Show only if**, default 10 s), and disappears as soon as you are back on track and driving normally.

### PitBrake (replaces "Twitch Followers Notification")
- Pit entry helper: **WAIT → BRAKE → HOLD**, so you know when to brake for the pit lane speed limit.
- Everything comes from telemetry, no setup needed.

### Weather (replaces "MGU")
- Track temperature, air temperature, humidity, track usage and a wetness bar (with sun and drop icons).
- **Layout**: **Vertical** (grid) or **Horizontal** (one line).
- Rounded corners. The wind is in its own **Wind** widget.

### Radar (replaces "Car Left Right")
- Keeps the original Kapps lines and adds an optional **Radar style**: your car (green) in the middle, the car next to you (white) in its real position and a red glow on the side where there is a car.
- The red glow fades out at the top and bottom.

### Stream Chat (in the "Twitch Chat" tab)
- **Twitch and YouTube** chat in the same widget (**Show chat from**: one or both).
- **Chat style**: message bubbles or full background. Message spacing, background color and opacity.

### Counters (Twitch + YouTube)
- Viewer count for **Twitch and YouTube**, each with its own icon. Show one or both.
- Background color and opacity, corners, shadow, alignment and a debug mode.
- If a field is empty in the Counters settings, it uses the same one from the Chat settings.

---

## Improved widgets

### Standings
- New **Fastest Lap** column (add it with the column editor). The class-best lap is shown in purple.
- **Country Flag** column, with all flags in the same 4:3 size.
- **Column Titles** checkbox: a small tab with **LAST LAP / FASTEST LAP** above those columns, on the first car of each class, with the same color and opacity as the rows.
- **SOF** now also shows in endurance / team races (it uses the average iRating of the drivers of each car).
- Fixed: the Standings window was sometimes cut off and could not be resized in the overlay.
- Fixed: turning off the flag column now really hides it.

### Relatives
- **Country Flag** option.
- **Last Lap** option: a column with each driver's last lap (format **3:28.2**) and a small **LAST LAP** title above it. The top bar keeps equal spaces between the items and gets smaller by itself when everything does not fit.
- Flags by type instead of "F":

| Flag | Meaning |
|---|---|
| **DMG** | Damage (black flag with orange circle) |
| **PEN** | Penalty (black flag) |
| **DQ** | Disqualified |
| **XD** | Slowdown |
| **DT** | Driver with a penalty in the pit lane (drive-through) |
| **SG** | Driver with a penalty stopped in the pit (stop-and-go) |

- Driver Name Style **Joshua Rogers**: only first name and last name, without the middle names.

### Inputs Graph
- New look: gear, speed, steering wheel, pedal bars and ABS drawn over the brake line.
- **Layout Style**: Style 1 or Style 2 (wheel on the right).
- **Wheel Model**: choose the steering wheel. To add your own, put PNG, SVG, JPG or WEBP images (transparent background, wheel seen from the front) in a **`wheels`** folder next to the installer and run it again. Each file becomes an option with its file name.
- **Speed Unit**: Auto (same as iRacing), km/h or mph.
- Show or hide gear & speed, steering wheel, graph and clutch bar.
- **Speed Extremums**: top speed before braking and apex speed (this lap / previous lap), next to the pedal bars.
- **Fade the end of the lines** on the graph.
- **Data Rate**: 60, 30 or 20 updates per second (lower = lighter on your PC).
- Hide in replay / when iRacing is not running.

### Fuel Calculator
- Original Kapps layout.
- **+1 Lap**: the fuel per lap you need to use for the fuel in the tank to last **one more lap** (in green).
- +1 Lap sits in the top row next to Laps in Race, with **PIT** on the right. In multiclass, when Kapps shows **For Leader**, For Leader moves to the bottom row. With the clock on, +1 Lap goes to the bottom row.
- Learns the **pit loss** of each stop for the Pit Rejoin widget.

### Pit Stop Helper
- **Pit Limiter** is now its own option and shows at the top of the widget, above the pit lane and pedal bars.

---

## General

- **Driver names** (Settings › Racing Overlay): removes the numbers from driver names in Relatives and Standings (e.g. "John Smith2" → "John Smith").
- The Racing Overlay settings list shows the **enabled widgets first**.
- The old **Standings (Legacy)** and **Pedals** widgets were removed from the list.
- **Performance**: the overlay **FPS** field is always visible (in the original Kapps it is hidden and stuck at 30 with hardware acceleration on), and the controller / button box is read less often. Less overlay FPS = less FPS lost in iRacing.
- **Demo / edit mode**: Standings, Relatives, Weather, Wind and the new widgets show example values, so you can position them without being in a session.

---

## How to turn on the options

All options are in the Kapps settings (**Settings › Racing Overlay**). New options come **off** by default.

| Option | Where | What to do |
|---|---|---|
| Wind | Racing Overlay › **Wind** | Turn the widget on. **Language › Português** for Portuguese labels, **Background** for color and opacity. |
| Pit Rejoin | Racing Overlay › **Pit Rejoin** | Turn the widget on. Set **Pit loss** and **Traffic** if you want. |
| Rejoin Helper | Racing Overlay › **Rejoin Helper** | Turn the widget on. Set the **Green / Red** limits and **Show only if**. |
| PitBrake | Racing Overlay › **PitBrake** | Turn the widget on. |
| Weather layout | Racing Overlay › **Weather** › **Layout** | Choose **Vertical** or **Horizontal**. |
| Radar style | Racing Overlay › **Radar** | Check **Radar style**. |
| Stream Chat | Racing Overlay › **Twitch Chat** | Fill in your Twitch / YouTube info and choose **Show chat from** and **Chat style**. |
| Counters | Racing Overlay › **Counters** | Turn the widget on and choose Twitch / YouTube in **Show Counters**. |
| Fastest Lap column | Racing Overlay › **Standings** › column editor | Drag **Fastest Lap** into the columns. |
| Column Titles | Racing Overlay › **Standings** › **Column Titles** | Check it. Only shows with **Show Headers** on and the Last Lap or Fastest Lap column in use. |
| Last Lap | Racing Overlay › **Relatives** › **Last Lap** | Check it. |
| Country Flag | Racing Overlay › **Relatives** › **Country Flag** | Check it. |
| Name style | Racing Overlay › **Relatives** › Driver Name Style |
