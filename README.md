# Kapps Mods for iRacing

A patch for the **Kapps** iRacing overlay that adds new widgets, improves the existing ones and fixes some bugs. Everything is changed inside Kapps itself: you keep using the normal Kapps settings, profiles and overlay.

> This is an unofficial community mod. It is not made or supported by the Kapps developer.

---

## Installation

1. Download **`atualizar-kapps.bat`** (just this one file).
2. Double-click it.
3. Press **1** (or wait 10 seconds). It downloads the latest mods and applies them.
4. Wait for **"Done! Mods applied."** and open Kapps again.

What the installer does:
- Downloads the latest version of the mods from this GitHub repository, so you always get the newest one.
- Finds the newest Kapps version installed on your PC.
- Closes Kapps if it is open.
- Saves a backup of the original Kapps the first time (`app.asar.original-backup`).
- Always applies the mods **on top of the original**, so you can run it as many times as you want.
- If something goes wrong, Kapps is left with the **original** file, so it never ends up broken.
- If there is no internet, it uses the last version it downloaded.

You don't need to install Node.js, WinRAR or anything else.

> The first time, Windows may show **"Windows protected your PC"** because the file came from the internet. Click **More info › Run anyway**.

### Updating the mods
When a new version comes out, Kapps shows a blue bar at the top: **"Kapps mods vX is available"**. Just run **`atualizar-kapps.bat`** again. It always downloads the newest version.

### After a Kapps update
When Kapps updates itself, the mods are removed. Run `atualizar-kapps.bat` again.

### Removing the mods
Run `atualizar-kapps.bat` and press **2 - Restore original Kapps**.

---

## Video tutorials

How to install the mods and where to get the **Twitch** and **YouTube** keys for the Chat and Counters:

| English | Português |
|---|---|
| [![English tutorial](https://img.youtube.com/vi/IFQjkRxbYRI/hqdefault.jpg)](https://www.youtube.com/watch?v=IFQjkRxbYRI) | [![Tutorial em português](https://img.youtube.com/vi/oR5qG2OAmy8/hqdefault.jpg)](https://www.youtube.com/watch?v=oR5qG2OAmy8) |
| [Watch on YouTube](https://www.youtube.com/watch?v=IFQjkRxbYRI) | [Assistir no YouTube](https://www.youtube.com/watch?v=oR5qG2OAmy8) |

---

## New widgets

### Wind
- Your car seen from above in the middle (it never moves) and a dark disc around it.
- The **N / E / S / W** letters and the **blue arrow** turn around the car as you drive. The arrow always shows the side the wind is hitting you from.
- Top-right corner: where the wind comes from on the map (N, NE, E, SE, S, SW, W, NW).
- Below: wind speed and where it hits the car (Headwind, Crosswind R/L, Tailwind...).
- Options: **Português** labels, background color and opacity, hide in replay / when iRacing is not running.

### Tyre Status
- The 4 tyres, each one split in 3 parts: **outside · middle · inside** (the outside is always the side facing out of the car).
- In each part: the **big white number is the wear** (% of rubber left) and the **colored stripe + small number is the temperature** of that part (**blue** = cold, **green** = ideal, **orange/red** = hot). The most worn part of each tyre is shown in red.
- iRacing only measures temperature and wear when you **stop in your pit box** (even just for fuel). The values stay **locked** from one stop to the next, and the lap of the last measurement is shown in the middle of the car (**LAP 12**; before the first stop, **START**).
- Options: **Cold below** / **Hot above** (°C) to set the colors, background color and opacity, hide in replay.

### Rejoin Helper
- A bubble that shows up when you go off track, spin or stop on track, with the time (in seconds) to the closest car **behind** you.
- **Green / Clear**, **Yellow / Caution** or **Red / Danger**. The limits are set in the settings.
- Only shows if that car is close enough (**Show only if**, default 10 s), and disappears as soon as you are back on track and driving normally.

### PitBrake (replaces "Twitch Followers Notification")
- Pit entry helper: **WAIT → BRAKE → HOLD**, so you know when to brake for the pit lane speed limit.
- Everything comes from telemetry, no setup needed.

### Weather (in the "MGU" slot)
- Track temperature, air temperature, humidity, track usage and a wetness bar (with sun and drop icons).
- **Layout**: **Vertical** (grid) or **Horizontal** (one line).
- Rounded corners. The wind is in its own **Wind** widget.
- The original Kapps **MGU** widget is still available as its own widget (Racing Overlay › **MGU**).

### Radar (replaces "Car Left Right")
- Keeps the original Kapps lines and adds an optional **Radar style**: your car (green) in the middle, the car next to you (white) in its real position and a red glow on the side where there is a car.
- The red glow fades out at the top and bottom.

### Stream Chat (in the "Twitch Chat" tab)
- **Twitch and YouTube** chat in the same widget (**Show chat from**: one or both).
- How to get the Twitch / YouTube keys: see the [video tutorials](#video-tutorials).
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

### Standings (Legacy)
- The old Kapps standings widget is back, with a new **Country Flag** column (after the car number). It's on by default and can be turned off in its settings.

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
- **Wheel Model**: choose the steering wheel. To add your own, put PNG, SVG, JPG or WEBP images (transparent background, wheel seen from the front) in a **`wheels`** folder next to `atualizar-kapps.bat` and run it again. Each file becomes an option with its file name.
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
- In timed races, learns the time lost in each pit stop (per track and series) so the laps left are counted correctly.

### Pit Stop Helper
- **Pit Limiter** is now its own option and shows at the top of the widget, above the pit lane and pedal bars.

---

## General

- **New Kapps look:** dark theme with a **sun / moon** button next to minimize to switch between dark and light (remembered). In Racing Overlay › Settings, each widget has its own **tab** at the top (green dot = enabled) and only the selected one is shown. Sliders now show the filled part in blue.
- **Driver names** (Settings › Racing Overlay): removes the numbers from driver names in Relatives and Standings (e.g. "John Smith2" → "John Smith").
- The Racing Overlay settings list shows the **enabled widgets first**.
- The old **Pedals** widget was removed from the list.
- **Performance**: the overlay **FPS** field is always visible (in the original Kapps it is hidden and stuck at 30 with hardware acceleration on), and the controller / button box is read less often. Less overlay FPS = less FPS lost in iRacing.
- **Demo / edit mode**: Standings, Relatives, Weather, Wind and the new widgets show example values, so you can position them without being in a session.

---

## How to turn on the options

All options are in the Kapps settings (**Settings › Racing Overlay**). New options come **off** by default.

| Option | Where | What to do |
|---|---|---|
| Wind | Racing Overlay › **Wind** | Turn the widget on. **Language › Português** for Portuguese labels, **Background** for color and opacity. |
| Tyre Status | Racing Overlay › **Tyre Status** | Turn the widget on. Set **Cold below** / **Hot above** for your car. |
| Rejoin Helper | Racing Overlay › **Rejoin Helper** | Turn the widget on. Set the **Green / Red** limits and **Show only if**. |
| PitBrake | Racing Overlay › **PitBrake** | Turn the widget on. |
| Weather layout | Racing Overlay › **Weather** › **Layout** | Choose **Vertical** or **Horizontal**. |
| MGU (original) | Racing Overlay › **MGU** | Turn the widget on. Same options as the original Kapps MGU. |
| Radar style | Racing Overlay › **Radar** | Check **Radar style**. |
| Stream Chat | Racing Overlay › **Twitch Chat** | Fill in your Twitch / YouTube info and choose **Show chat from** and **Chat style**. |
| Counters | Racing Overlay › **Counters** | Turn the widget on and choose Twitch / YouTube in **Show Counters**. |
| Fastest Lap column | Racing Overlay › **Standings** › column editor | Drag **Fastest Lap** into the columns. |
| Column Titles | Racing Overlay › **Standings** › **Column Titles** | Check it. Only shows with **Show Headers** on and the Last Lap or Fastest Lap column in use. |
| Last Lap | Racing Overlay › **Relatives** › **Last Lap** | Check it. |
| Country Flag | Racing Overlay › **Relatives** › **Country Flag** | Check it. |
| Standings (Legacy) | Racing Overlay › **Standings (Legacy)** | Turn the widget on. **Country Flag** shows or hides the flags. |
| Name style | Racing Overlay › **Relatives** › Driver Name Style | Choose **Joshua Rogers**. |
| Relatives flags | Relatives | Nothing to do: they show automatically. |
| Speed Extremums | Racing Overlay › **Inputs Graph** › **Speed Extremums** | Check it. |
| Line fade | Racing Overlay › **Inputs Graph** › **Graph** | Check **Fade the end of the lines**. |
| +1 Lap | Racing Overlay › **Fuel Calculator** › **+1 Lap** | Check it. |
| Pit Limiter | Racing Overlay › **Pit Stop Helper** | Turn on the pit limiter option. It no longer needs the pit lane bars. |
| Driver names | Racing Overlay › **Driver names** | Check **Remove numbers from driver names in Relatives and Standings**. |

---

## Troubleshooting

- **"app.asar is locked"**: close Kapps from the tray icon (**Quit Kapps**) and any program that may be using it (antivirus scan, etc.), or restart the PC, then run the installer again.
- **"ERROR while applying"**: your Kapps version is probably newer than the mod. Kapps was left with the original file. Wait for an update of the mods and run `atualizar-kapps.bat` again.
- **Mods disappeared**: Kapps updated itself. Run `atualizar-kapps.bat` again.

---

## Credits / Agradecimentos

**English:** Special thanks to **ssg22** for the help with this update: testing, ideas and feedback. 🙏

**Português:** Um agradecimento especial ao **ssg22** pela ajuda nessa atualização: testes, ideias e sugestões. 🙏
