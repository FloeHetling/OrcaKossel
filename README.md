![cover](graphics/Anycubic%20Kossel%20Linear%20Plus_cover.png)

# OrcaKossel  
**Anycubic Kossel Linear Plus — Klipper × OrcaSlicer Reference Pack**

> Drop‑in profiles, bed model and graphics so you can start slicing for the Kossel **in minutes**.  
> Works with **Orca Slicer ≥ 1.7.0** (Bambu/PrusaSlicer fork) and a Klipper‑tuned Kossel Linear Plus fitted with a **0.4 mm nozzle**.


---

## 📦 What’s inside?

```
OrcaKossel/
├─ bed-model/
│  └─ Anycubic Kossel Linear Plus_buildplate_model.stl
├─ dist/
│  └─ Anycubic_KosselLinearPlus_ImportMe.zip   ← one‑click import bundle
├─ graphics/
│  ├─ Anycubic Kossel Linear Plus_buildplate_texture.png
│  └─ Anycubic Kossel Linear Plus_cover.png
├─ misc/printer_data/config/
│  └─ printer.cfg                              ← example Klipper config
└─ orca-profiles/
   └─ Anycubic/
      ├─ filament/
      │  └─ Generic unbranded PLA.json
      ├─ machine/
      │  ├─ Anycubic Kossel Linear Plus 0.4 nozzle.json
      │  └─ Anycubic Kossel Linear Plus.json
      └─ process/
          ├─ 0.12 mm Extra‑fine.json
          ├─ 0.20 mm Normal.json
          ├─ 0.30 mm Draft.json
          └─ 0.32 mm Rough Draft.json
```

| Category | File(s) | Description |
|----------|---------|-------------|
| **Bed model** | `bed-model/*.stl` `graphics/*texture.png` | Gives you a nice textured Kossel build plate in the preview window. |
| **Orca profiles** | Printer, Filament, five Process JSONs | Tuned for 0.4 mm nozzle, PLA, 1000 mm/s² accel, pressure‑advance 0.02 s. |
| **Klipper** | `printer.cfg` | Example config that matches the slicer’s assumptions (speed limits, PA, etc.). |
| **Import bundle** | `dist/Anycubic_KosselLinearPlus_ImportMe.zip` | All of the above zipped the way Orca expects—just drag and drop. |

---

## 🚀 Quick start

1. **Download** the repo or grab only `dist/Anycubic_KosselLinearPlus_ImportMe.zip`.
2. Open **File ▸ Import ▸ Import configs...** and select downloaded ZIP.
   Orca will add:
   * **Printer** → *Anycubic Kossel Linear Plus 0.4 nozzle*  
   * **Filament** → *Generic unbranded PLA*  
   * **Processes** → *0.12 mm Extra‑fine* … *0.32 mm Rough Draft*
3. (Optional) Go to **Printer (settings) ▸ Printable space ▸ Printable area ▸ Set...** and pick  
   *Model*: `bed-model/Anycubic Kossel Linear Plus_buildplate_model.stl`  
   *Texture*: `graphics/Anycubic Kossel Linear Plus_buildplate_texture.png`
4. Select the new printer/filament/process in the **Prepare** window and slice away!

---

## 🛠️ Profile details

| Process | Layer height | Infill | Perimeter speed | Use‑case |
|---------|-------------|--------|-----------------|----------|
| **0.12 mm Extra‑fine** | 0.12 mm | 15 % crosshatch | 30 mm/s | Display models, threads |
| **0.20 mm Normal** | 0.20 mm | 15 % crosshatch | 40 mm/s | Everyday prints |
| **0.30 mm Draft** | 0.30 mm | 18 % crosshatch | 45 mm/s | Fast prototyping |
| **0.32 mm Rough Draft** | 0.32 mm | 20 % cubic | 50 mm/s | Very large parts |
| *(0.16 mm Fine & 0.28 mm Draft can be recreated via interpolation—see docs.)* |

All profiles share:

* **Nozzle/bed**: 200 / 60 °C first layer, 195 / 60 °C afterwards  
* **Retraction**: 4 mm @ 40 mm/s + 0.4 mm Z‑hop  
* **Acceleration limit**: 1000 mm/s²; **Junction deviation** handled in firmware  
* **Pressure advance**: 0.312 s (for bowden extruders, that are separated from printhead with filament hose. Set to 0.02 if you have direct-drive)  
* Skirt 2 loops, no supports by default.

---

## ⚙️ Klipper notes

*The provided `printer.cfg` is just a reference.*  
Flash your own MCU firmware and merge sections as needed. Most important bits:

```ini
# Excerpt
max_velocity:                   200       # X/Y
max_accel:                      1000
pressure_advance:               0.312
```

Match these to Orca so your printed speeds & PA are consistent.
You may want to calibrate Pressure advance. **Calibration ▸ Pressure advance** is a good starting point

## 🤝 Contributing

PRs & issues are welcome - especially:

* Testing on other Kossel variants (mini, Plus with 0.6 mm nozzle, etc.)
* PETG/ABS filament presets
* Additional bed textures

---

## 📜 License

This project is released under the **GNU GENERAL PUBLIC LICENSE** (see [`LICENSE`](LICENSE)).  
STL and PNG assets are distributed under the same terms unless noted otherwise.

---

**Happy printing!**  
*— Dominik Efremov*