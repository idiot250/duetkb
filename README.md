# duetkb

**An open-source split stenography keyboard.**

duetkb is a DIY split stenography keyboard designed for fast, chord-based text input. It uses a compact two-piece layout, allowing both hands to operate independently while remaining connected to a single host computer.

i built this project for the idea of making dedicated stenographic hardware accessible, affordable, and customizable.

The first hardware revision is currently being designed. PCB design and firmware development are ongoing.

## Features

- Split keyboard architecture with independent left and right halves.
- 23-key stenographic layout.
- Wired USB-C connection to the host computer.
- Inter-half communication through a physical cable.
- ESP32-based hardware architecture.
- Designed for integration with [Plover](https://www.openstenoproject.org/plover/).
- Open-source hardware and firmware.

## Hardware

the keyboard is designed around two separate PCBs, one for each hand. it uses a row-and-column switch matrix with individual diodes to support simultaneous key presses and prevent unwanted electrical interactions.

| component | function |
|---|---|
| Microcontroller | ESP32 |
| Key switches | Mechanical switches |
| Diodes | Individual switch-matrix diodes |
| Host connection | USB-C |
| Inter-half connection | Wired |
| Layout | 23-key stenographic |

## repo structure

```text
duetkb/
├── hardware/
│   ├── left/
│   │   └── KiCad project files
│   └── right/
│       └── KiCad project files
├── firmware/
│   └── ESP-IDF project
├── JOURNAL.md
└── README.md
```

*Directory structure may change as development progresses.*

## Firmware

Firmware is being developed using **ESP-IDF**.

The intended firmware will handle:

- Switch matrix scanning.
- Simultaneous keypress detection.
- Communication between keyboard halves.
- Stenographic chord processing.
- USB HID output for compatibility with host computers and Plover.

## Software Compatibility

duetkb is intended to work with [Plover](https://www.openstenoproject.org/plover/), an open-source stenography engine.

The eventual goal is to translate simultaneous key combinations into stenographic input that Plover can interpret using a supported stenography dictionary and theory.

## Development

The hardware is designed in [KiCad](https://www.kicad.org/), while firmware development uses the ESP-IDF framework.

To work on the firmware, install ESP-IDF and its required toolchain.

```bash
git clone https://github.com/kurone741/duetkb.git
cd duetkb
```

Firmware build and flashing instructions will be added once the initial firmware implementation is ready.

## Roadmap

- [x] Establish project architecture.
- [x] Select initial hardware components.
- [x] Design left and right schematics.
- [x] Assign PCB footprints.
- [ ] Complete PCB component placement.
- [ ] Route both PCBs.
- [ ] Run PCB design-rule checks.
- [ ] Generate manufacturing files.
- [ ] Assemble hardware.
- [ ] Implement switch matrix scanning.
- [ ] Implement inter-half communication.
- [ ] Implement stenographic input processing.
- [ ] Test Plover compatibility.

## License

Licensing information will be added before the first public hardware and firmware release.
