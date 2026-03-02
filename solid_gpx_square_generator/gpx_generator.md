
# 📘 README — GPX Square Coverage Generator

This script generates a **GPX track** that simulates walking a rectangular area in a **lawn‑mower pattern** using **giant vertical steps** and small adjustable east‑step increments.  
Useful for simulating coverage scans, route sweeping, or synthetic GNSS movement.

***

## 🚀 How It Works

1.  You provide:
    *   A **starting GPS coordinate** (`start_lat`, `start_lon`)
    *   Distances (in **meters**) to shift from that point:
        *   `west_m`, `north_m` → gives the **upper‑left corner**
        *   `east_m`, `south_m` → gives the **lower‑right corner**
2.  The script converts your meter offsets into latitude/longitude.
3.  It generates a sweep pattern:
    *   Start at the **upper‑left** corner
    *   Move **straight south** to the southern boundary
    *   Step **east** by a small adjustable distance (`horizontal_step_m`)
    *   Move **straight north** back to the top
    *   Repeat until reaching (or slightly exceeding) the eastern boundary
4.  A GPX 1.1 file is saved with time‑stamped trackpoints.

***

## 📌 Example Usage

### Minimal test (uses Macau as start point by default)

```python
generate_square_gpx_fast_vertical(
    west_m=20, north_m=20,
    east_m=20, south_m=20,
    horizontal_step_m=2.0,
    filename="square_fast_40x40.gpx"
)
```

### Using a custom starting coordinate

```python
generate_square_gpx_fast_vertical(
    start_lat=30.0,
    start_lon=120.0,
    west_m=1000,
    north_m=500,
    east_m=2000,
    south_m=500,
    horizontal_step_m=1.0,
    filename="custom_area.gpx"
)
```

***

## ⚙️ Key Parameters

| Parameter                | Meaning                                              |
| ------------------------ | ---------------------------------------------------- |
| `start_lat`, `start_lon` | Starting reference coordinate (default = Macau).     |
| `west_m`, `north_m`      | Offset REACHING the upper‑left corner.               |
| `east_m`, `south_m`      | Offset REACHING the lower‑right corner.              |
| `horizontal_step_m`      | X‑axis step between sweeps (1–5 m recommended).      |
| `secs_per_meter`         | Controls timestamp speed.                            |
| `allow_exceed_east`      | Allow final east step to pass the boundary slightly. |
| `max_columns`            | Safety cap to prevent huge GPX files.                |

***

## 🗂 Output

The script produces:

*   A **GPX 1.1 file** containing:
    *   Track name
    *   Timestamps (UTC)
    *   Latitude/longitude points forming the sweep pattern

*   A summary printed to console:
    *   UL/LR corner coordinates
    *   Approx area width/height
    *   Estimated columns
    *   Total trackpoints
    *   Total simulated walking distance

***

## 📝 Notes

*   No external libraries required — only Python standard library.
*   Avoid extremely small east steps on large areas (e.g., 1 m step for 50 km width) unless you accept very large files.
*   GPX is compatible with apps like:
    *   GPXSee
    *   Garmin BaseCamp
    *   QGIS
    *   Google Earth (after conversion)

***
