# obs-cli

[![Latest Release](https://img.shields.io/github/release/muesli/obs-cli.svg)](https://github.com/muesli/obs-cli/releases)
[![Build Status](https://github.com/muesli/obs-cli/workflows/build/badge.svg)](https://github.com/muesli/obs-cli/actions)
[![Go ReportCard](https://goreportcard.com/badge/muesli/obs-cli)](https://goreportcard.com/report/muesli/obs-cli)
[![GoDoc](https://godoc.org/github.com/golang/gddo?status.svg)](https://pkg.go.dev/github.com/muesli/obs-cli)

OBS-cli is a command-line remote control for OBS. As of OBS v28 obs-websocket v5 is included by default.

## Installation

### Build From Source

Alternatively you can also build `obs-cli` from source. Make sure you have a
working Go environment (Go 1.12 or higher is required). See the
[install instructions](https://golang.org/doc/install.html).

To install obs-cli, simply run:

```
git clone https://github.com/onyx-and-iris/obs-cli.git
cd obs-cli
go install
```

## Usage

Load connection info from toml config. A valid `config.toml` might look like this:

```toml
[connection]
Host="localhost"
Port=4455
Password="mystrongpass"
```

It should be placed in `home directory / .obs_cli /`

Otherwise, all commands support the following flags:

-   `--host`: which OBS instance to connect to
-   `--port`: port to connect to
-   `--password`: password used for authentication

### Streams

Change the streaming state:

```
obs-cli stream start
obs-cli stream stop
obs-cli stream toggle
```

Display streaming status:

```
obs-cli stream status
```

### Recordings

Change the recording state:

```
obs-cli recording start
obs-cli recording stop
obs-cli recording toggle
```

Pause or resume a recording:

```
obs-cli recording pause enable
obs-cli recording pause resume
obs-cli recording pause toggle
```

Display recording status:

```
obs-cli recording status
```

### Scenes

List all scene names:

```
obs-cli scene list
```

Show the current scene name:

```
obs-cli scene get
```

Switch program to a scene:

```
obs-cli scene current <scene>
```

Switch preview to a scene (studio mode must be enabled):

```
obs-cli scene preview <scene>
```

Switch program (studio mode disabled) or preview (studio mode enabled) to a scene:

```
obs-cli scene switch <scene>
```

### Scene Collections

List all scene collections:

```
obs-cli scenecollection list
```

Show the current scene collection:

```
obs-cli scenecollection get
```

Switch to a scene collection:

```
obs-cli scenecollection set <scenecollection>
```

### Scene Items

List all items of a scene:

```
obs-cli sceneitem list <scene>
```

Change the visibility of a scene-item:

```
obs-cli sceneitem show <scene> <item>
obs-cli sceneitem hide <scene> <item>
obs-cli sceneitem toggle <scene> <item>
```

Display the visibility of a scene-item:

```
obs-cli sceneitem visible <scene> <item>
```

Center a scene-item horizontally:

```
obs-cli sceneitem center <scene> <item>
```

### Labels

Change a FreeType text label:

```
obs-cli label text <label> <text>
```

Trigger a countdown and continuously update a label with the remaining time:

```
obs-cli label countdown <label> <duration>
```

### Sources

List special sources:

```
obs-cli source list
```

Toggle mute status of a source:

```
obs-cli source toggle-mute <source>
```

### Studio Mode

Enable or disable Studio Mode:

```
obs-cli studiomode enable
obs-cli studiomode disable
obs-cli studiomode toggle
```

Display studio mode status:

```
obs-cli studiomode status
```

Transition to program (when the studio mode is enabled):

```
obs-cli studiomode transition
```

### Profiles

List all profiles:

```
obs-cli profile list
```

Show the current profile:

```
obs-cli profile get
```

Switch to a profile:

```
obs-cli profile set <profile>
```

### Replay Buffer

Change the replay buffer state:

```
obs-cli replaybuffer start
obs-cli replaybuffer stop
```

Save the replay buffer:

```
obs-cli replaybuffer save
```

Display replay buffer status:

```
obs-cli replaybuffer status
```

### Virtual Camera

Change the virtual camera state:

```
obs-cli virtualcam start
obs-cli virtualcam stop
obs-cli virtualcam toggle
```

Display virtual camera status:

```
obs-cli virtualcam status
```
