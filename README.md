# MeshCore 101 at The Maker's Space

This repository contains the guides and presentation for a two-hour beginner workshop introducing MeshCore and building a Bluetooth companion node.

No previous MeshCore, LoRa, firmware, or soldering experience is required.

## Class materials

### Student guide

[Open the MeshCore 101 Student Guide](meshcore-student-guide.md)

The student guide contains:

- a beginner-friendly MeshCore overview;
- safety information;
- companion assembly instructions;
- firmware flashing steps;
- Bluetooth identification and app setup;
- the private-channel message exercise;
- charging guidance;
- troubleshooting steps;
- companion and repeater hardware examples; and
- local and official resources.

### Presenter guide

[Open the MeshCore 101 Presenter Guide](meshcore-presenter-guide.md)

The presenter guide contains:

- the two-hour class schedule;
- instructor preparation checklists;
- presenter notes for each section;
- assembly and safety checkpoints;
- flashing and Bluetooth recovery procedures;
- guidance for the private-channel exercise;
- time-recovery options;
- an equipment checklist; and
- a student success tracker.

### Presentation

[Download the MeshCore 101 PowerPoint presentation](meshcore-101-makers-space-v8.pptx)

The presentation covers:

- what MeshCore is and why it exists;
- realistic capabilities and limitations;
- how channel and direct messages travel through the mesh;
- companion, repeater, room-server, and Observer roles;
- DIY and commercially packaged hardware options;
- repeater-placement guidance;
- Indiana Mesh, NEI Mesh, and OKI Mesh resources;
- the class companion components and assembly sequence;
- antenna, battery, and enclosure safety;
- firmware flashing and app setup; and
- The Maker's Space private-channel test.

## Workshop companion

The class companion uses:

- Seeed Studio XIAO nRF52840
- Wio-SX1262 LoRa board
- Antenna pigtail and external antenna
- Protected TP4056 USB-C charging module
- One 18650 battery and holder
- Power switch
- 3D-printed enclosure with six cover screws

All soldering and internal wiring are completed before class. Students finish the no-solder assembly, flash Companion Bluetooth firmware, configure the app, and send a test message.

## Private-channel invitation

The QR code and secret for **The Maker's Space** private channel are distributed separately during class. They are intentionally excluded from this repository.

## Important safety reminders

- Attach the complete antenna path before powering or transmitting.
- Verify battery direction using the holder's `+` and `−` markings.
- Use the XIAO USB-C port for flashing.
- Use the TP4056 USB-C port for charging.
- Do not connect both USB ports simultaneously unless that condition has been tested and validated.
- Monitor the device while charging.
- Apply downward pressure while tightening the six screws so the printed case closes without a gap.

See the student and presenter guides for the complete procedures.

## Official and regional resources

- [MeshCore](https://meshcore.io/)
- [MeshCore documentation](https://docs.meshcore.io/)
- [MeshCore Web Flasher](https://flasher.meshcore.io/)
- [Indiana Mesh](https://www.cimesh.net/)
- [Indiana Mesh Discord](https://discord.gg/tm7wh7RjD7)
- [NEI Mesh](https://neimesh.net/)
- [OKI Mesh](https://okimesh.org/)
- [OKI Mesh Discord](https://discord.okimesh.org/)
- [MeshMapper](https://meshmapper.net/)
- [OKI Mesh live map](https://map.okimesh.org/)

## Keeping the materials current

MeshCore changes quickly. Before presenting the workshop, verify the current flasher device name, stable firmware version, app menus, radio preset, path-hash recommendation, and local community guidance.
