<!-- markdownlint-disable MD033 MD041 -->
<p align="center">
  <img src="./assets/round_reboslime.png" style="border-radius: 100px;" width="200" height="200" alt="ReboSlime">
</p>


<div align="center">

# ReboSlime

<!-- prettier-ignore-start -->
<!-- markdownlint-disable-next-line MD036 -->
<div>Use ReboCap with SlimeVR Server</div>

<!-- prettier-ignore-end -->

</div>

<p align="center">
  <a href="https://raw.githubusercontent.com/colasama/reboslime/master/LICENSE">
    <img src="https://img.shields.io/github/license/colasama/reboslime" alt="license">
  </a>
  <img src="https://img.shields.io/badge/python-3.11.x | 3.12.x-blue?logo=python&logoColor=edb641" alt="python">
</p>



## Usage

- Download the executable from `Releases`. The latest `v0.4.2` supports ReboCap v40 and later. For the older version that works with VMT, download `v0.31`.
- Open the SlimeVR Server.
- Open the ReboCap client and click **Motion Calibration 1**.
- Run `run.bat` or `reboslime.exe`.
- You should now see trackers appearing in SlimeVR! Follow the normal SlimeVR setup from here.

## Development

- This project uses `Poetry` for dependency management. Install Python 3.11.x or 3.12.x, then run `pip install poetry`.
- Run `poetry install` to install dependencies, then `poetry run python reboslime.py` to start the program.

## Building

To package the project as an executable, install `pyinstaller` and run:

```bash
pyinstaller -F -i .\assets\reboslime.ico reboslime.py
```

After building, place `config.json` in the same directory as the executable.

## Notes

- Due to limitations in the ReboCap client, you must wear the trackers in the standard VR configuration. A minimum of 6 points is required. Supported configurations are 6 / 8 / 10 / 12 / 15 points:
  - 6 points: Chest + Hips + Upper Legs + Lower Legs
  - 8 points: Chest + Waist + Upper Legs + Lower Legs + Feet
  - 10 points: Chest + Waist + Upper Legs + Lower Legs + Feet + Upper Arms
  - 12 points: Chest + Waist + Upper Legs + Lower Legs + Feet + Upper Arms + Lower Arms
  - 15 points: Full body
- **Note**: Each configuration produces a node 0 (Pelvis). You can leave it unassigned or assign it to the hip in SlimeVR.

## ToDo

- [x] Add tracker count selection.
- [ ] Investigate head node appearing non-functional in 15-point mode.

## Credits

- https://github.com/lmore377/moslime — SlimeVR network transport reference; much of the packet structure is based on this project.
