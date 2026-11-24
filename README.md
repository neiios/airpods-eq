# airpods-eq

Set the built-in EQ on AirPods from Linux.

Recent AirPods firmware has a three-band equalizer (low, mid, high) that is stored on the AirPods, so the setting follows them to every device they connect to. Apple only lets you change it from its own Settings app. This script sends the same command over Bluetooth.

Tested on AirPods Pro 3. Other models that show the Equalizer option on an iPhone should work too.

## Usage

```
airpods-eq get
airpods-eq set 60 50 70    # low mid high, 0-100, 50 is flat
airpods-eq off             # back to Apple's default tuning
airpods-eq on              # custom again, with the bands you set before
```

The connected AirPods are found automatically. If that picks the wrong device, pass `--device AA:BB:CC:DD:EE:FF`.

## Requirements

- Python 3.10 or newer, no extra packages
- BlueZ with `bluetoothctl`
- AirPods paired and connected, on firmware that has Custom EQ

## Install

It is a single file. Run it from the clone or copy it somewhere on your `PATH`:

```
install -Dm755 airpods-eq ~/.local/bin/airpods-eq
```

## Credits

The packet format comes from the reverse engineering done by [LibrePods](https://github.com/librepods-org/librepods).
