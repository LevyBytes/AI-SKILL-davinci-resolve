# Signal Flow Diagrams

> Davinci Resolve reference. Original prose; identifiers preserved verbatim.

### Signal Flow Diagrams

Throughout this chapter, the diagrams lay out how the Fairlight audio processing signal flow behaves inside DaVinci Resolve. The material targets readers seeking a thorough grasp of the way audio gets handled.

### Signal Flow Overview

Shown below, this streamlined flow diagram captures Fairlight audio processing as a whole.

SOLO MULTI TRACK AUX SUB MAIN

2 24 24 24 8 Stereo Mono 24 24 24

### Bus Number Max Format

### DISK

### CHANNEL INPUT METER

### SIDE CHAIN INPUT

### INTERCHANGEABLE ORDER BETWEEN EQ, DYNAMICS AND INSERTS

### DYNAMICS EQ

### INSERTS AND PLUGINS

### AUX SENDS

### AUX

### CHANNEL FADER, PAN AND MUTE

### MAINS SUBS

### MULTI TRACK SOLO

### DIRECT

### OUTPUT

### MAIN BUS 1–8

### SUB BUS 1–24

### BUS ASSIGNMENT – SUB TO MAIN

### AUX BUS 1–24

### BUS ASSIGNMENT – AUX TO MAIN

### MULTI-TRACK

### BUS 1–24

### BUS

### SOLO BUS

### BUS

### TALK-BACK INPUTS EXTERNAL INPUTS

### TO BUSES

### SOLO

### BUS DIRECT

### SOLO

### BUS DIRECT

### SOLO

### BUS DIRECT

### Audio Processing Path

### OUTPUT

### OUTPUT

### OUTPUT

### OUTPUT

### OUTPUT

### CONTROL ROOM

### MAINS SUBS AUX SOLO EXT

### STUDIO

### MAINS SUBS AUX SOLO EXT

### OUTPUT OUTPUT

### OUTPUT

### SOLO MULTI TRACK AUX SUB MAIN

### PLAYBACK TO/FROM DISK RECORD

### RECORD GAIN CHANNEL INPUT

### METER SIDE CHAIN INPUT

### TALK-BACK INPUTS EXTERNAL INPUTS

Each Aux Sends tap can independently sit before or after the fade stage, ahead of or following the mute, and either side of the pan, with any mixture of those choices allowed.

Bus 2 24 24 24 8 Number Stereo Mono 24 24 24 Max Format

### SOLO

### INTERCHANGEABLE ORDER BETWEEN EQ, DYNAMICS AND INSERTS

### DYNAMICS

### EQ

### INSERTS AND PLUGINS

### GATE COMP LIM

### BAND BAND

### FILTER EQ

### UP TO 6 PLUGINS

### AUX SENDS

### FADER MUTE

### PAN

VCA GROUP 1-32

24 PAN 8 24 24

### After (Post) Fader

### AFL/PFL

### Pre Fader

### Post Pre

### DIRECT

### OUTPUT

### MAIN BUS 1–8

### TALK ENABLE

A/B

### 4 COMP LIM BAND

### EQ

### INSERTS AND PLUGINS UP TO 6 PLUGINS

### METER

### Post Pre

### SOLO

### SUB BUS 1–24

### TALK ENABLE

A/B

### 4 COMP LIM BAND

### EQ

### INSERTS AND PLUGINS UP TO 6 PLUGINS

### BUS ASSIGNMENT – SUB TO MAIN

### METER Post

### Pre

### SOLO

### AUX BUS 1–24

### TALK ENABLE

A/B

### 4 COMP LIM BAND

### EQ

### INSERTS AND PLUGINS UP TO 6 PLUGINS

### BUS ASSIGNMENT – AUX TO MAIN

### METER

### Post Pre

### FREQUENCY OSCILLATOR

### GAIN

### OSCILLATOR

### MULTI-TRACK BUS 1–24

### OUTPUT

### METER

### GAIN

### WHITE NOISE

### WHITE NOISE

### PINK NOISE

### GAIN

### OUTPUT

### PINK NOISE

### SOLO BUS

### OUTPUT

### METER

### TO BUSES A/B

### BUS DIRECT 8

### BUS DIRECT 24 BUS DIRECT

### BUS

### OUTPUT OUTPUT OUTPUT OUTPUT

### BUS

### MAINS SUBS AUX SOLO EXT

### OUTPUT LOUDNESS METER

### FIXED FOLD 24 DOWN/UP 24 FORMAT CHECK

### CONTROL ROOM

DIM MUTE

### 2 24

### METER

### MAINS SUBS AUX SOLO EXT

### FOLD 6 DOWN/UP 2

### FORMAT CHECK

### DIM

### MUTE 1

### STUDIO

### OUTPUT OUTPUT

### OUTPUT
