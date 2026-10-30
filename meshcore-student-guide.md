# MeshCore 101 Student Guide

## The Maker's Space Companion Workshop

**Class length:** 2 hours  
**Experience level:** Beginner  
**Class project:** Assemble, flash, configure, and test a MeshCore Bluetooth companion

Use this guide during the workshop and keep it as a reference afterward. Follow the instructor's directions when the live app or firmware screens differ from the examples in this guide.

---

## What you will accomplish

By the end of class, you should have a companion that:

- has its antenna and internal radio connection installed;
- contains the XIAO nRF52840 and Wio-SX1262 boards;
- has an 18650 battery installed in the correct direction;
- is closed with all six case screws;
- runs MeshCore Companion Bluetooth firmware;
- connects to the MeshCore app;
- uses the class radio settings; and
- can send and receive a message in The Maker's Space private channel.

## Record your device information

Fill this in during class:

| Item | Your information |
|---|---|
| Kit number | |
| Node name | |
| Firmware version | |
| Radio preset | USA/Canada (Recommended) |
| Path hash size | 2 byte |

---

## MeshCore in one minute

MeshCore is an open-source system for sending short text messages and small data packets over LoRa radio. It does not require cellular service, Wi-Fi, or internet access for radio-to-radio communication.

Your phone does not contain the LoRa radio used by MeshCore. Instead:

```text
Phone ──Bluetooth── Companion ──LoRa── Mesh ──LoRa── Companion ──Bluetooth── Phone
```

- **Bluetooth** connects your phone to your nearby companion.
- **LoRa** carries messages between MeshCore radios.
- **Repeaters** can extend useful coverage by forwarding eligible traffic.
- **MeshCore** manages identities, contacts, channels, routing, and messages.

MeshCore works well for short text messages, local groups, and low-power community communication. It is not intended for voice, video, high-speed internet, guaranteed delivery, or automatic emergency response.

### Common MeshCore roles

| Role | Purpose |
|---|---|
| Companion | Connects to a phone or computer and sends the user's messages |
| Repeater | Forwards eligible mesh traffic to extend coverage |
| Room server | Provides shared-room and message-storage features |
| Observer | Reports packets it hears to a mapping or analysis service |

Today we are building a **Bluetooth companion**.

---

## Safety rules

### 1. Attach the antenna before power

> [!CAUTION]
> Never turn on or transmit with the radio unless the antenna and pigtail are attached correctly.

Before moving the power switch to `ON`, confirm:

- the tiny pigtail connector is seated on the Wio-SX1262;
- the external antenna is attached to the case connector; and
- the antenna cable is not pinched or sharply bent.

### 2. Check battery polarity

An 18650 lithium-ion cell can cause damage or become hazardous if inserted backward, shorted, crushed, or used with a damaged wrapper.

- Inspect the wrapper before installation.
- Find the `+` and `−` markings on the holder.
- Match the battery ends to the holder markings.
- Do not determine polarity from the spring position alone.
- Ask an instructor to verify the battery before turning on the device.

If the battery or electronics become hot, swell, smell unusual, or make noise, stop and notify an instructor immediately.

### 3. Know the two USB-C ports

| Port | Purpose |
|---|---|
| XIAO USB-C | Flashing firmware, USB data, and controller power |
| TP4056 USB-C | Charging the installed 18650 battery |

Use the **XIAO port** during the firmware portion of class. Use the **TP4056 port** only for charging. Follow the instructor's directions for the power-switch position.

### 4. Protect the printed case

- Keep the six screws in a parts cup or tray.
- Check that no wires cross the case edge or screw holes.
- Start all six screws before fully tightening any one screw.
- Press the cover toward the case while tightening so the screws grip the printed plastic.
- Stop when the cover is seated without a gap. Do not crush the case or strip the holes.

---

## Your companion hardware

| Component | What it does |
|---|---|
| Seeed Studio XIAO nRF52840 | Runs the firmware and provides Bluetooth and USB |
| Wio-SX1262 | Provides the LoRa radio |
| Antenna pigtail | Connects the Wio-SX1262 to the external antenna connector |
| External antenna | Transmits and receives LoRa signals |
| 18650 battery and holder | Provides portable power |
| Protected TP4056 module | Charges the battery and provides battery protection |
| Power switch | Controls battery power to the companion |
| Printed enclosure | Holds and protects the parts |

---

## Part 1: Assemble the companion

Keep the power switch `OFF` throughout assembly.

### Step 1: Connect the antenna pigtail

1. Locate the tiny antenna socket on the Wio-SX1262.
2. Hold the pigtail connector directly above the socket.
3. Align it carefully.
4. Press straight down until it seats.
5. Do not pry sideways or pull on the cable.

If the connector does not seat with gentle, even pressure, stop and ask for help.

### Step 2: Attach the Wio-SX1262 to the XIAO

1. Check the header alignment before pressing the boards together.
2. Confirm that every row starts on the correct pin.
3. Support both boards.
4. Press evenly until the boards are fully seated.

Do not force a board that appears offset or tilted.

### Step 3: Place the board assembly in the case

1. Place the stacked boards in their assigned position.
2. Keep the pigtail away from sharp bends.
3. Confirm that the XIAO USB-C connector lines up with its case opening.
4. Check that the boards and installed wiring remain seated.

### Step 4: Attach the external antenna

1. Verify that the internal pigtail is still connected.
2. Thread the external antenna onto the case connector.
3. Tighten it finger-snug.
4. Do not use pliers or overtighten it.

The antenna must remain attached whenever the radio is powered or may transmit.

### Step 5: Install the 18650 battery

1. Inspect the battery wrapper.
2. Find the `+` and `−` markings on the holder.
3. Identify the positive and negative ends of the battery.
4. Insert the battery in the direction shown by the holder markings.
5. Ask an instructor or assistant to check it.

Do not turn on the switch yet.

### Step 6: Attach the front cover

1. Check for pinched wires and displaced components.
2. Position the cover without forcing it.
3. Place all six hex screws in their holes.
4. Start each screw loosely.
5. Apply steady downward pressure while tightening.
6. Tighten the screws evenly around the cover.
7. Stop when there is no visible gap between the case bottom and cover.

If a screw spins without gripping, stop and ask for help.

### Assembly checkpoint

Before continuing, verify:

- [ ] Pigtail connected
- [ ] External antenna attached
- [ ] Boards aligned and seated
- [ ] Battery wrapper undamaged
- [ ] Battery polarity checked
- [ ] No wires pinched
- [ ] Six screws seated evenly
- [ ] Power switch off

---

## Part 2: Flash Companion Bluetooth firmware

Use a known-good USB **data cable**. Some USB cables provide power but cannot transfer data.

1. Confirm that the antenna is attached.
2. Confirm that the power switch is `OFF`.
3. Connect the cable to the **XIAO USB-C** port.
4. Open [flasher.meshcore.io](https://flasher.meshcore.io/) in a supported browser.
5. Select the device named **Seeed Studio XIAO nRF52 WIO**.
6. Select **Companion Bluetooth** firmware.
7. Select the current stable firmware version.
8. Follow the browser prompt to choose your USB device.
9. Start the flash.
10. Do not unplug the cable until the flasher reports success.

> [!NOTE]
> App labels and flasher screens can change. Follow the instructor's projected example if the live interface differs from this guide.

### Do not erase routinely

A full erase can remove a device's MeshCore identity and saved settings. Use it only when the instructor or official recovery directions call for it.

### Flashing checkpoint

- [ ] Correct hardware selected
- [ ] Companion Bluetooth selected
- [ ] Flash completed successfully
- [ ] Device restarted

---

## Part 3: Connect to your companion

For this class, the initial companion setup uses **Bluetooth**. The XIAO USB connection is used for firmware flashing.

1. Open the MeshCore app.
2. Allow Bluetooth permissions when prompted.
3. Turn on your companion when the instructor directs you to do so.
4. Open the app's device connection screen.
5. Select your companion.

### Finding your device in a room full of companions

Do not guess if several Bluetooth devices appear.

1. Keep your kit number visible.
2. Flash and connect one table or small group at a time.
3. Watch the Bluetooth list while your device is switched off and on. Your entry should disappear and reappear.
4. Ask nearby students to leave their devices off until their turn when necessary.
5. After connecting, immediately assign your unique class node name.

Use the instructor's naming pattern, such as `MS-FirstName` or `MS-KitNumber`. Avoid including a home address, precise location, or other sensitive personal information.

### Apply the class settings

Set every class device to the same radio configuration:

- **Preset:** USA/Canada (Recommended)
- **Path hash:** 2 byte for the OKI regional network

Save the settings and reboot if the app requests it.

### Connection checkpoint

Show an instructor or assistant:

- [ ] Your connected node name
- [ ] USA/Canada (Recommended) preset
- [ ] 2-byte path hash setting
- [ ] Connected status in the app

---

## Part 4: Join the class channel and test messaging

The Maker's Space channel is a **private channel**. Everyone must join using the same invitation so every device receives the same channel secret.

1. Open the app menu.
2. Choose **Add Channel**.
3. Choose **Scan QR Code**.
4. Scan the private-channel QR code on the separate handout provided by the instructor.
5. Continue to **The Maker's Space** channel.
6. Send the exact message:

```text
test
```

An instructor or co-leader will reply to acknowledge your test.

> [!IMPORTANT]
> Anyone with the private-channel QR code or secret key can send and receive messages in the channel. Keep the separate invitation handout within the intended class group.

### Messaging checkpoint

- [ ] Joined The Maker's Space private channel
- [ ] Sent `test`
- [ ] Received an acknowledgment

---

## How messages travel

### Channel messages

Channel text messages use flood routing. Eligible repeaters may forward the message through several possible paths. Companions receive messages but do not act as repeaters.

### Direct messages

The first direct message can use flood routing to find the recipient. The mesh can learn the successful repeater path. Later messages can use that learned route so only repeaters on the selected path retransmit the message. If the route stops working, the system can try flooding again to find another path.

Delivery still depends on radio conditions, compatible settings, and available nodes. MeshCore cannot guarantee that every message will arrive.

---

## Companion and repeater hardware choices

The class companion is a DIY design using the XIAO nRF52840 and Wio-SX1262. MeshCore also supports other DIY boards and commercially packaged devices. Support and availability change, so check the [official MeshCore flasher](https://flasher.meshcore.io/) before buying.

### Companion examples

| DIY or modular | Ready-built or packaged |
|---|---|
| XIAO nRF52840 with Wio-SX1262 | Wio Tracker L1 Pro |
| RAK4631 WisBlock | SenseCAP T1000-E |
| Supported Heltec LoRa boards | WisMesh Pocket or WisMesh Tag |

Choose a companion based on how you plan to carry and power it, whether you want a display or GPS, and how much assembly you want to do.

### Repeater examples

| DIY or modular | Ready-built or packaged hardware |
|---|---|
| RAK4631 WisBlock | SenseCAP Solar Node P1 Pro |
| Supported Heltec v3 or v4 boards | RAK WisMesh repeater hardware |
| XIAO nRF52 with Wio-SX1262 | Vendor-built outdoor nodes using supported boards |

Commercial LoRa hardware may ship with firmware other than MeshCore. Verify the exact board, radio band, and MeshCore repeater target before purchasing or flashing.

### Repeater placement tips

- Place a repeater where it fills a real coverage gap.
- Height and a clear horizon often help more than additional transmit power.
- Keep the antenna vertical and away from metal, walls, and noisy electronics.
- Provide enough power reserve for poor weather if the site uses solar power.
- Weatherproof the enclosure, cable entries, and antenna connection.
- Test the radio settings and useful links before permanent mounting.
- Obtain site permission and plan safe maintenance access.

Use [MeshMapper](https://meshmapper.net/) and local community maps as planning tools, not guarantees of coverage.

---

## Charging after class

The class battery may not arrive fully charged.

1. Disconnect the XIAO USB cable.
2. Confirm the antenna remains attached.
3. Choose the switch position:
   - `OFF` charges the battery without powering the companion.
   - `ON` allows the tested class companion to operate while charging; keep the antenna attached.
4. Connect a suitable cable to the **TP4056 USB-C** charging port.
5. Observe the charging and completed-charge indications.
6. Place the device on a nonflammable surface where it can be monitored.
7. Disconnect it if the battery or electronics become hot or behave abnormally.

Never leave a charging lithium-ion battery unattended.

---

## Troubleshooting

### The computer does not detect the XIAO

1. Confirm that the cable is connected to the XIAO port, not the TP4056 port.
2. Try a known-good USB data cable.
3. Try another USB port or adapter.
4. Close other programs or browser tabs that may be using the device.
5. Reload the flasher.
6. Follow the reset or DFU directions shown by the flasher.

### Flashing fails

- Verify **Seeed Studio XIAO nRF52 WIO** is selected.
- Verify **Companion Bluetooth** is selected.
- Re-enter DFU mode if the flasher directs you to do so.
- Try another data cable.
- Ask to use the instructor's known-good flashing station.

### The companion does not appear in the app

- Confirm Bluetooth is enabled and permission is granted.
- Confirm Companion Bluetooth firmware was installed.
- Restart the companion.
- Watch which Bluetooth entry disappears and reappears when you switch your device off and on.
- Ask an instructor to test the companion with another phone.

### The app connects, but messages do not travel

- Confirm the antenna is attached.
- Confirm the devices use the same regional preset.
- Confirm the 2-byte path hash setting used by the local network.
- Send a fresh advertisement.
- Move the devices several feet apart.
- Test against the instructor's known-good node.

### The companion works on USB but not on battery

- The battery may need charging.
- Recheck battery polarity.
- Confirm the power switch position.
- Ask an instructor to inspect the battery and power circuit.
- Do not bypass the charger or protection circuitry.

### The cover will not close

- Do not force it.
- Check for a pinched wire or displaced board.
- Confirm the battery is fully seated.
- Confirm connectors and the switch align with their openings.
- Loosen all six screws, press the cover into place, and tighten evenly.

---

## Local communities and resources

### Official MeshCore resources

- [MeshCore official site](https://meshcore.io/)
- [MeshCore documentation](https://docs.meshcore.io/)
- [MeshCore Web Flasher](https://flasher.meshcore.io/)
- [MeshCore firmware on GitHub](https://github.com/meshcore-dev/MeshCore)

### Indiana and regional communities

- [Indiana Mesh](https://www.cimesh.net/) — Central Indiana information and community support
- [Indiana Mesh Discord](https://discord.gg/tm7wh7RjD7) — includes the `#northeast` channel for Northeast Indiana
- [NEI Mesh](https://neimesh.net/) — Northeast Indiana
- [OKI Mesh](https://okimesh.org/) — Ohio, Kentucky, and Indiana regional information
- [OKI Mesh Discord](https://discord.okimesh.org/)

### Maps

- [MeshMapper](https://meshmapper.net/)
- [OKI Mesh live map](https://map.okimesh.org/)

---

## Quick reference

```text
BEFORE POWER
✓ Pigtail seated
✓ External antenna attached
✓ Battery wrapper undamaged
✓ Battery polarity verified
✓ No pinched wires

FLASH
XIAO USB-C
flasher.meshcore.io
Device: Seeed Studio XIAO nRF52 WIO
Role: Companion Bluetooth

CONNECT
Identify your Bluetooth device carefully
Assign a unique node name
Select USA/Canada (Recommended)
Select 2-byte path hash

CLASS TEST
Add Channel → Scan QR Code
Join The Maker's Space
Send: test
Receive an instructor reply

CHARGE
TP4056 USB-C
Monitor the device while charging
```

## Final check before leaving

- [ ] I know which USB port flashes the device.
- [ ] I know which USB port charges the battery.
- [ ] I know the antenna must be attached before power or transmission.
- [ ] I can identify my companion in the Bluetooth list.
- [ ] I recorded my node name and settings.
- [ ] I sent and received a class-channel message.
- [ ] I know where to find local help and current firmware information.
