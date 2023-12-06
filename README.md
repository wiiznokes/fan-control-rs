# fan-control

[![license](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](#license)
![ci_status](https://github.com/wiiznokes/light_enum/actions/workflows/test.yml/badge.svg)

## Steps

- [x] finish hardware crate
    - [x] impl windows code
    - [x] impl linux code
    - [x] test on real hardware
- [x] Windows optimization
- [ ] End to End testing
- [ ] package multiple format with [cargo-bundle](https://github.com/burtonageo/cargo-bundle)
    - [ ] Msi
    - [x] Deb
    - [ ] ARM support
    - [ ] RPM (not yet available)
    - [ ] EXE (not yet available)
    - [ ] Flatpak (not yet available)
    - [ ] Snap (not yet available)
    - [ ] CI for packaging
- [x] change iced to libcosmic (this will enable new widgets, like dropdown) (libcosmic must be ported to Windows before)
    - [x] theme (from Cosmic)
    - [x] impl UI for managing configs
    - [x] impl UI for removing nodes
    - [x] impl UI settings page
    - [x] impl UI for adding nodes
    - [ ] impl UI for removing config
    - [ ] CustomDropDown widget
    - [x] FloatingElement witget
- [ ] impl UI graph behavior
- [x] icons
- [ ] tray icon support (not yet available on [Iced](https://whimsical.com/roadmap-iced-7vhq6R35Lp3TmYH4WeYwLM))
- [ ] i18n support ([example](https://github.com/pop-os/cosmic-edit/blob/master_jammy/Cargo.toml))
    - [x] init file structure
    - [ ] add all string to ftl files


## Installation
#### Linux
To have the maximum number of sensors detected by the application, you must install lm-sensor and run the hardware detection script:
```
sudo apt install lm-sensors
sudo sensors-detect
```
Also, make sure to execute the program in sudo mode.

## Repo structure
- [hardware](./hardware/README.md): define an abstraction around the hardware.
- [data](./data/README.md): define structures used in the app (Node, Config), and there logic. Depend on [hardware](./hardware/README.md)
- [ui](./ui/README.md): implement the UI. Depend on [data](./data/README.md) and [hardware](./hardware/README.md)
- the app: integrate all this crates in one executable

## Config files
- Windows: `C:\Users\wiiz\AppData\Roaming\wiiznokes\fan-control\config`
- Linux: `/home/wiiz/.config/fan-control`

## Build
See instructions [here](./BUILD.md).

## Contributing
Contributions are welcome, do not hesitate to open an issue, a pull request, etc...
