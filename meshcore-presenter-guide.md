# MeshCore 101 Companion Workshop

## Presenter Guide

**Class length:** 2 hours  
**Audience:** Beginners and makers; no prior MeshCore, LoRa, or firmware experience required  
**Class format:** Short presentation, no-solder assembly, firmware flashing, app setup, and a private-channel message test  
**Class hardware:** Seeed Studio XIAO nRF52840, Wio-SX1262, antenna pigtail and external antenna, protected TP4056 charging module, single 18650 holder, power switch, and printed enclosure

> [!IMPORTANT]
> This guide matches the current class plan and presentation. All soldering is completed before class. Students connect and install the removable components, flash Companion Bluetooth firmware, configure the app, join The Maker's Space private channel, and send `test`.

---

## 1. Class outcome

Each attendee should leave with a companion that they have:

1. Inspected and identified.
2. Connected to its antenna pigtail.
3. Assembled by joining the Wio-SX1262 and XIAO nRF52840.
4. Placed into the prepared enclosure.
5. Fitted with its external antenna and 18650 battery.
6. Closed using all six enclosure screws.
7. Flashed with MeshCore Companion Bluetooth firmware.
8. Connected to the MeshCore app.
9. Configured for the class radio settings.
10. Joined to The Maker's Space private channel.
11. Used to send `test` and receive an instructor acknowledgment.

### Minimum successful outcome

An attendee has succeeded when the node:

- has the antenna path connected before power;
- has the battery installed in the correct direction;
- flashes successfully as a Bluetooth companion;
- connects to the MeshCore app;
- uses the class radio preset and path-hash setting; and
- sends and receives a message in the class private channel.

The supplied batteries may arrive without a usable charge. Battery-powered operation is not required to complete the firmware portion. The XIAO can receive firmware through its USB-C connection while the power switch remains off.

---

## 2. Learning objectives

By the end of the workshop, attendees should be able to:

- Explain what MeshCore is and why someone might use it.
- Explain the difference between Bluetooth and LoRa in the class system.
- Describe how channel messages flood through repeaters and how direct messages can learn a route.
- Distinguish companion, repeater, room-server, and Observer functions.
- Identify the major components of the class companion.
- Distinguish DIY hardware from commercially packaged MeshCore options.
- Explain the factors that make a repeater location useful.
- Assemble the remaining no-solder companion components safely.
- Identify the XIAO USB-C port and the TP4056 charging port.
- Flash Companion Bluetooth firmware.
- Identify the correct device in a room full of Bluetooth companions.
- Apply the instructor-designated radio settings.
- Join a private channel from an invitation and complete a message test.
- Locate official documentation and the Indiana, NEI Mesh, and OKI Mesh communities.

---

## 3. Presenter preparation

Complete the following work before attendees arrive.

### 3.1 Prepare the soldered assemblies

For every kit:

- Install and solder the protected TP4056 charging module.
- Install the 18650 holder and power switch.
- Complete and inspect all wiring inside the enclosure.
- Confirm that both USB-C connections remain accessible through the case:
  - `XIAO — FLASH / DATA`
  - `TP4056 — BATTERY CHARGE`
- Install the case-mounted antenna connector if the design uses one.
- Confirm that the antenna pigtail can reach the Wio-SX1262 without a sharp bend.
- Leave the XIAO and Wio-SX1262 available for the student to join and place in the case.
- Leave the external antenna available for student attachment.
- Leave the front cover and six hex screws separate.
- Inspect for solder bridges, loose strands, exposed conductors, and pinched wiring.
- Verify battery polarity through the holder, charger, switch, and board power connection.
- Confirm that the switch functions correctly.
- Assign a visible kit number to the enclosure and loose parts.

> [!CAUTION]
> Validate the completed power circuit before class. Use a current-limited supply when practical. Do not rely only on a visual inspection.

### 3.2 Build and test reference units

Prepare at least two instructor-owned companions and one demonstration sample:

- one complete working reference unit;
- one second companion for message testing;
- one unassembled sample or enlarged demonstration setup for the pigtail and board-stacking steps.

Test the entire student sequence before class, including:

- antenna attachment;
- firmware flashing;
- Bluetooth discovery;
- the radio preset and path-hash setting;
- joining the private channel; and
- sending and receiving the test message at the venue.

### 3.3 Prepare the batteries

- Use only the intended single-cell 18650 chemistry and form factor.
- Inspect every wrapper for tears, dents, corrosion, leakage, or heat damage.
- Measure and record the cell voltage.
- Isolate any questionable cell.
- Protect battery terminals during transport.
- Keep loose cells away from screws, tools, and other conductive objects.
- Charge the cells before class if time permits.
- Plan for some or all cells to arrive without a usable charge.

### 3.4 Prepare the flashing stations

Each station should have:

- a computer with a current supported browser;
- access to [flasher.meshcore.io](https://flasher.meshcore.io/);
- a known-good USB data cable;
- any required USB adapters;
- access to the XIAO reset control if DFU recovery is needed;
- the current MeshCore app on a phone or tablet; and
- Bluetooth enabled with app permission granted.

Bring several spare USB data cables. Charge-only or unreliable cables are a common source of failure.

### 3.5 Prepare the class settings

Shortly before class, verify the current local settings with the relevant community. The presentation currently uses:

- **Preset:** USA/Canada (Recommended)
- **Path hash:** 2 byte for the OKI regional network

Record the current stable firmware version and the exact device name shown by the live flasher. The expected target is **Seeed Studio XIAO nRF52 WIO**, but the displayed wording can change.

### 3.6 Prepare the Bluetooth identification plan

A room full of identical companions can produce a confusing device list. Use all of the following:

- Give each kit a visible number.
- Flash and connect one table or small group at a time.
- Keep devices off until their connection group is called.
- Have students watch which Bluetooth entry disappears and reappears when their node is switched off and on.
- Assign a unique node name immediately after the first successful connection.
- Use a naming pattern such as `MS-FirstName` or `MS-KitNumber`.

For this class, students flash through USB and perform initial companion setup through Bluetooth. Do not imply that the Bluetooth companion can be configured as a repeater through the USB repeater setup screen.

### 3.7 Prepare the private-channel exercise

- Create **The Maker's Space** private channel before class.
- Test the invitation with another device.
- Print a separate QR invitation for every student or table.
- Keep the QR code and secret out of the public GitHub guides.
- Keep one instructor companion connected to the channel throughout class.
- Ask a co-leader to help acknowledge incoming messages.
- Reply to every exact `test` message so students verify both sending and receiving.

Anyone with the QR code or secret can participate in the channel. Treat the printed invitations according to the access level you want for the group.

### 3.8 Prepare offline and hardware fallbacks

- Download the correct current firmware before class.
- Save official app and documentation links.
- Bring a computer that has already flashed a test device successfully.
- Bring spare XIAO boards, Wio-SX1262 boards, pigtails, antennas, batteries, and screws.
- Bring extra USB data cables and correct hex drivers.
- Bring parts trays for the six screws.
- Keep the complete working reference unit unchanged during class.

---

## 4. Safety briefing

Deliver the safety briefing before hardware assembly begins.

### 4.1 Antenna-before-power rule

> **The antenna path must be connected before the radio is powered or allowed to transmit.**

The required path is:

```text
Wio-SX1262 socket → pigtail → case connector → external antenna
```

Verify the pigtail and external antenna before moving the power switch to `ON`.

### 4.2 Battery safety

- Use one approved 18650 cell.
- Do not use a cell with damaged wrapping.
- Keep metal tools away from exposed terminals.
- Use the polarity marks printed on the holder.
- Do not infer polarity from spring position alone.
- Require instructor or assistant verification before first power.
- Stop if a cell or board becomes hot, swells, smells unusual, or makes noise.
- Never leave a charging lithium-ion cell unattended.

### 4.3 USB and power safety

| Connection | Purpose |
|---|---|
| XIAO USB-C | Firmware flashing, USB data, and controller power |
| TP4056 USB-C | Charging the installed 18650 battery |

The protected TP4056 module provides the battery charging connection and protection functions. In this build, the switch connects the TP4056 `OUT+` terminal to the XIAO `BAT+` pad. The battery can charge with the switch on or off. With the switch off, the companion electronics are disconnected from the charger output. With the switch on, the tested class hardware can operate while charging and still reaches charge completion. Keep the antenna attached whenever the switch is on.

Do not connect both USB ports simultaneously unless that operating condition has been validated on the finished circuit.

### 4.4 Mechanical safety

- Align the pigtail connector before pressing it.
- Do not pry the small RF connector sideways.
- Check board headers before joining the boards.
- Keep the pigtail free from sharp bends and pinches.
- Start all six cover screws loosely.
- Apply steady downward pressure while tightening so the screws grip the printed plastic.
- Tighten evenly until there is no visible gap.
- Stop before stripping the holes or crushing the cover.

---

## 5. Two-hour run of show

| Time | Duration | Segment |
|---|---:|---|
| 0:00–0:10 | 10 min | Welcome, outcome, and safety |
| 0:10–0:25 | 15 min | What MeshCore is, why it exists, and realistic expectations |
| 0:25–0:38 | 13 min | Message routing and MeshCore roles |
| 0:38–0:50 | 12 min | Hardware options, repeater placement, and local resources |
| 0:50–1:15 | 25 min | Companion assembly |
| 1:15–1:35 | 20 min | Flash Companion Bluetooth firmware |
| 1:35–1:48 | 13 min | Bluetooth identification and app setup |
| 1:48–1:57 | 9 min | Join the private channel and send `test` |
| 1:57–2:00 | 3 min | Review and next steps |

> [!TIP]
> Protect the flashing, connection, and channel-test portions of the schedule. If assembly runs long, assistants can finish individual case closures after the student's firmware and message test.

---

## 6. Presenter flow and teaching notes

### Segment 1 — Welcome, outcome, and safety

**Time:** 0:00–0:10

#### Say

> MeshCore sends short messages through small, low-power LoRa radios without depending on cellular service, Wi-Fi, or the internet. Today we will learn how the system works, finish a prepared companion, install its firmware, connect it to an app, and send a message through our private class channel.

Clarify that this is a no-solder workshop. The charging module, battery holder, switch, and wiring have already been installed. Students will complete the removable radio assembly and enclosure.

#### Cover

- Antenna attached before power or transmission.
- Battery polarity taken from the holder markings.
- XIAO USB-C for flashing; TP4056 USB-C for charging.
- Switch off during assembly and flashing.
- Six screws started loosely, then tightened with downward pressure.

#### Check for understanding

Ask:

1. Which USB port flashes the device?
2. Which USB port charges the battery?
3. What must be attached before the radio transmits?
4. Where should students look for battery polarity?

### Segment 2 — What MeshCore is and what it is not

**Time:** 0:10–0:25

#### Explain

- The app provides the user interface.
- Bluetooth connects the app to the nearby companion.
- LoRa connects radios over the air.
- Repeaters can extend useful paths.
- MeshCore manages contacts, channels, routing, and messages.

#### Set expectations

MeshCore is a good fit for:

- short text messages;
- local groups and contacts;
- low-power field communication; and
- community-built coverage.

MeshCore does not provide:

- voice or video;
- high-speed internet;
- guaranteed delivery; or
- automatic emergency response.

Do not promise a particular range. Antenna quality, terrain, height, buildings, interference, settings, and available repeaters all affect performance.

### Segment 3 — Message routing and roles

**Time:** 0:25–0:38

#### Basic path

```text
Phone ──Bluetooth── Companion ──LoRa── Repeaters ──LoRa── Companion ──Bluetooth── Phone
```

#### Channel messages

The Maker's Space private channel uses flood routing. Eligible repeaters may forward the message through several possible paths. Companion nodes receive messages but do not repeat them.

#### Direct messages

The first direct message can flood to find the recipient. A delivery report can return the successful repeater path. Later messages can carry that learned path so only matching repeaters retransmit. If the route fails, the system can retry and flood again to find another path.

Keep this conceptual. Packet formats and advanced path controls are outside a 101 class.

#### Four useful roles

| Role | Beginner explanation |
|---|---|
| Companion | Pairs with a phone or computer and carries the user's messages |
| Repeater | Forwards eligible mesh traffic and usually operates as infrastructure |
| Room server | Provides persistent shared-room behavior |
| Observer | Reports what it hears to a mapping or network-analysis service |

Explain that Observer is commonly an added function associated with a repeater rather than a separate student build in this class.

### Segment 4 — Hardware options, repeaters, and community resources

**Time:** 0:38–0:50

#### DIY versus ready-built

DIY hardware offers customization, repairability, and a better view of how the system works. It requires assembly, firmware, and testing. Ready-built hardware integrates more of the case, battery, controls, and antenna. It usually costs more and offers less flexibility.

Start with the intended role and environment, then choose hardware.

#### Companion examples

| DIY or modular | Ready-built or packaged |
|---|---|
| XIAO nRF52840 with Wio-SX1262 | Wio Tracker L1 Pro |
| RAK4631 WisBlock | SenseCAP T1000-E |
| Supported Heltec LoRa boards | WisMesh Pocket or WisMesh Tag |

#### Repeater examples

| DIY or modular | Ready-built or packaged hardware |
|---|---|
| RAK4631 WisBlock | SenseCAP Solar Node P1 Pro |
| Supported Heltec v3 or v4 boards | RAK WisMesh repeater hardware |
| XIAO nRF52 with Wio-SX1262 | Vendor-built outdoor nodes using supported boards |

Commercial hardware can ship with firmware other than MeshCore. Verify the exact board, regional band, and supported flasher target before purchase.

#### Repeater placement tips

- Fill a real coverage gap rather than duplicating a nearby site.
- Seek height and a clear horizon.
- Keep the antenna vertical and away from metal or noisy electronics.
- Provide battery reserve for low-sun periods at solar sites.
- Weatherproof the enclosure and the complete RF path.
- Test settings, remote management, and useful links before permanent mounting.
- Obtain site permission and plan safe maintenance access.

#### Community resources

- Indiana Mesh serves Central Indiana and provides local support.
- NEI Mesh covers Northeast Indiana through [neimesh.net](https://neimesh.net/) and the `#northeast` channel in the Indiana Mesh Discord.
- OKI Mesh supports the broader Ohio, Kentucky, and Indiana region.
- MeshMapper and the OKI live map provide useful observations, not guaranteed coverage.

### Segment 5 — Companion assembly

**Time:** 0:50–1:15

Keep the room in lockstep. Demonstrate each step, pause, and inspect before proceeding.

#### Identify the components

| Component | Purpose |
|---|---|
| XIAO nRF52840 | Firmware platform, Bluetooth, and USB |
| Wio-SX1262 | LoRa radio board |
| Pigtail and external antenna | Complete the radio-frequency path |
| 18650 battery and holder | Portable power |
| Protected TP4056 module | Battery charging and protection |
| Power switch | Controls battery power |
| Printed enclosure and six screws | Holds and protects the assembly |

#### Step 1: Connect the pigtail

1. Align the tiny connector directly over the Wio-SX1262 socket.
2. Press straight down until it seats.
3. Do not lever sideways or pull on the cable.

Inspect any unit that does not seat with gentle pressure.

#### Step 2: Join the boards

1. Align every header pin.
2. Confirm the boards are not offset by one position.
3. Support both boards and press evenly.

#### Step 3: Place the assembly

1. Place the board stack in its assigned case position.
2. Align the XIAO USB-C port with the case opening.
3. Route the pigtail without sharp bends or pinches.

#### Step 4: Attach the external antenna

1. Verify the pigtail remains seated.
2. Thread the external antenna onto the case connector.
3. Tighten it finger-snug.

This is the stop point before any power is allowed.

#### Step 5: Install the battery

1. Inspect the wrapper.
2. Find the `+` and `−` marks on the holder.
3. Match the cell ends to those marks.
4. Require instructor or assistant verification.

Do not describe polarity from memory or spring position.

#### Step 6: Close the case

1. Check that no wire crosses the case edge or screw holes.
2. Position the cover.
3. Start all six screws loosely.
4. Apply steady downward pressure while tightening.
5. Tighten evenly around the cover.
6. Stop when there is no visible gap.

If a screw spins without gripping, stop and assist. Do not solve it with excessive torque.

#### Assembly checkpoint

- [ ] Pigtail seated
- [ ] External antenna attached
- [ ] Boards aligned and secure
- [ ] Battery wrapper undamaged
- [ ] Battery polarity verified
- [ ] No pinched wires
- [ ] Six screws seated evenly
- [ ] Switch off

### Segment 6 — Flash Companion Bluetooth firmware

**Time:** 1:15–1:35

Demonstrate the complete process once before students begin.

1. Confirm antenna attached and switch off.
2. Connect to the **XIAO USB-C** port using a data cable.
3. Open [flasher.meshcore.io](https://flasher.meshcore.io/).
4. Select **Seeed Studio XIAO nRF52 WIO**.
5. Select **Companion Bluetooth**.
6. Select the current stable version.
7. Choose the correct USB device.
8. Enter DFU mode only when the flasher directs it.
9. Start flashing.
10. Do not disconnect until the flasher reports success.

#### Explain while flashing

- Hardware selection matters because board pin assignments differ.
- Companion Bluetooth is the role required for the class app workflow.
- Repeater firmware would create a different type of node.
- A full erase can remove an existing MeshCore identity and saved settings.

#### Flashing checkpoint

- [ ] Correct hardware target
- [ ] Companion Bluetooth role
- [ ] Flash completed successfully
- [ ] Device restarted

### Segment 7 — Identify the companion and configure the app

**Time:** 1:35–1:48

Connect one table or small group at a time.

1. Open the MeshCore app and allow Bluetooth permission.
2. Turn on only the companions in the active group.
3. Open the connection screen.
4. Power-cycle one node if needed and watch which entry disappears and reappears.
5. Connect to that entry.
6. Assign the unique class node name immediately.
7. Select **USA/Canada (Recommended)**.
8. Select the **2-byte path hash** setting used by the OKI network.
9. Save and reboot if prompted.

#### Configuration checkpoint

Each student should show an instructor or assistant:

- the connected node name;
- the selected preset;
- the 2-byte path-hash setting; and
- the app's connected status.

Remind students that publishing a node or precise location to an internet map is optional and is not required for radio communication.

### Segment 8 — Join the private channel and send `test`

**Time:** 1:48–1:57

Distribute the separate printed QR invitations.

1. Open the app menu.
2. Choose **Add Channel**.
3. Choose **Scan QR Code**.
4. Scan the printed invitation.
5. Continue to **The Maker's Space**.
6. Send the exact message `test`.

The instructor or co-leader replies to each message. A student completes the exercise after receiving the acknowledgment.

Do not have students create separate private channels. Separate channel creation produces different secrets that cannot communicate with one another.

### Segment 9 — Review and next steps

**Time:** 1:57–2:00

Ask:

1. What connects the phone to the companion?
2. What connects MeshCore radios to one another?
3. Which firmware role did we install?
4. What must be attached before the radio transmits?
5. Which USB port charges the battery?
6. Why must the class share compatible radio settings?

Point students to the local communities and maps. Remind them that maps show observations rather than guaranteed coverage.

---

## 7. Troubleshooting guide

### The XIAO does not appear in the flasher

1. Confirm the cable is connected to the XIAO port, not the TP4056 port.
2. Try a known-good USB data cable.
3. Try another USB port or adapter.
4. Close any serial monitor or browser tab using the device.
5. Reload the flasher.
6. Follow the reset or DFU procedure shown by the flasher.
7. Move to the instructor's known-good station.

### Flashing fails

- Confirm **Seeed Studio XIAO nRF52 WIO**.
- Confirm **Companion Bluetooth**.
- Re-enter DFU mode when directed.
- Change the USB data cable.
- Use the downloaded firmware fallback if the online workflow is unavailable.

### Students cannot identify their Bluetooth device

- Stop other groups from powering devices.
- Use the visible kit number.
- Refresh the Bluetooth list.
- Switch one node off and on and watch which entry changes.
- Connect and rename the node immediately.
- Use an instructor phone to separate a phone issue from a node issue.

### The app connects, but nodes cannot communicate

- Confirm the antenna is attached.
- Confirm the USA/Canada preset on every device.
- Confirm the 2-byte path-hash setting.
- Send a fresh advertisement if needed.
- Separate nodes by several feet.
- Test each student against the known-good instructor node.

### The node works on USB but not on battery

- The battery may not be charged.
- Confirm battery polarity.
- Confirm the power-switch position.
- Inspect the TP4056 and protection circuit.
- Test with a known-good battery only after inspecting the device.
- Do not bypass the charging or protection circuitry.

### The case will not close

- Do not force the cover.
- Check for pinched wiring or a displaced board.
- Confirm the battery is fully seated.
- Confirm the switch and connectors align with their openings.
- Loosen all screws, press the cover into place, and tighten evenly.

### The private channel does not appear or messages do not match

- Confirm the student scanned the instructor's invitation.
- Confirm the channel name is **The Maker's Space**.
- Remove an incorrectly created channel only with the student's permission.
- Scan the printed invitation again.
- Verify that the student sends the exact word `test`.

---

## 8. Charging guidance

The batteries may require charging after class.

1. Disconnect the XIAO USB cable.
2. Keep the antenna attached.
3. Choose the switch position:
   - `OFF` charges the battery without powering the companion.
   - `ON` allows the tested class companion to operate while charging; keep the antenna attached.
4. Connect the charger to the **TP4056 USB-C** port.
5. Show the charging-status and completed-charge indications.
6. Place the device on a nonflammable surface where it can be monitored.
7. Disconnect it if the battery or electronics become hot or abnormal.

Do not promise a full charge during the two-hour class. Do not leave charging lithium-ion cells unattended.

---

## 9. Time-recovery options

If the class falls behind, reduce content in this order:

1. Shorten the commercial-hardware examples.
2. Move detailed repeater-placement discussion to the closing resources.
3. Demonstrate learned direct-message routing rather than expanding on it.
4. Assign an assistant to finish difficult case closures after the student flashes.
5. Let a struggling student use the known-good companion for the app and channel exercise while an assistant repairs the student's unit.

Do not remove:

- the antenna and battery safety checks;
- the device-target and firmware-role check;
- Bluetooth identity verification;
- the radio-preset check; or
- the private-channel send-and-receive test.

---

## 10. Presenter equipment checklist

### Hardware

- [ ] Prepared soldered enclosures
- [ ] XIAO and Wio-SX1262 boards for every kit
- [ ] Pigtails and external antennas
- [ ] Inspected 18650 cells
- [ ] Covers and six screws per kit
- [ ] One complete known-good reference node
- [ ] One additional instructor companion
- [ ] Spare boards, pigtails, antennas, batteries, and screws
- [ ] USB data cables and adapters
- [ ] Correct hex drivers
- [ ] Parts trays or cups
- [ ] Multimeter
- [ ] Current-limited supply, if available
- [ ] Battery-safe transport materials

### Software and class network

- [ ] Web flasher tested
- [ ] Current firmware downloaded locally
- [ ] MeshCore app installed on instructor devices
- [ ] Venue internet tested
- [ ] USB permission tested
- [ ] USA/Canada preset verified
- [ ] 2-byte path-hash setting verified
- [ ] Unique node-naming pattern selected
- [ ] The Maker's Space private channel tested
- [ ] Separate QR invitations printed
- [ ] Instructor and co-leader acknowledgment plan confirmed

### Teaching materials

- [ ] Current slide deck
- [ ] Updated presenter guide
- [ ] Student guide
- [ ] Separate private-channel invitation handouts
- [ ] USB-port identification graphic
- [ ] Battery-polarity graphic
- [ ] Kit-success checklist
- [ ] Resource links

---

## 11. Student success checklist

Record completion by kit number.

| Kit | Assembly | Flash | Bluetooth | Settings | Sent `test` | Reply received |
|---|---|---|---|---|---|---|
| | | | | | | |
| | | | | | | |
| | | | | | | |
| | | | | | | |
| | | | | | | |

---

## 12. Resources

### Official MeshCore

- [MeshCore official site](https://meshcore.io/)
- [MeshCore documentation](https://docs.meshcore.io/)
- [MeshCore FAQ](https://docs.meshcore.io/faq/)
- [MeshCore Web Flasher](https://flasher.meshcore.io/)
- [MeshCore firmware repository](https://github.com/meshcore-dev/MeshCore)

### Indiana and regional communities

- [Indiana Mesh](https://www.cimesh.net/)
- [Indiana Mesh Discord](https://discord.gg/tm7wh7RjD7)
- [NEI Mesh](https://neimesh.net/)
- [OKI Mesh](https://okimesh.org/)
- [OKI Mesh Discord](https://discord.okimesh.org/)

### Maps

- [MeshMapper](https://meshmapper.net/)
- [OKI Mesh live map](https://map.okimesh.org/)

> [!NOTE]
> MeshCore changes quickly. Shortly before class, verify the live flasher's device name, current stable firmware, app menus, radio preset, path-hash recommendation, and bootloader instructions.

---

## 13. Presenter quick-reference card

```text
BEFORE CLASS
✓ Soldered assemblies inspected
✓ Pigtails, boards, antennas, batteries, covers, and screws staged
✓ Firmware and flasher tested
✓ Class channel tested
✓ Separate QR invitations printed

BEFORE POWER
✓ Pigtail seated
✓ External antenna attached
✓ Battery wrapper undamaged
✓ Battery polarity verified
✓ No pinched wires
✓ Six screws seated

FLASH
XIAO USB-C
Device: Seeed Studio XIAO nRF52 WIO
Role: Companion Bluetooth
Wait for success

CONNECT
Work in small groups
Power-cycle to identify the Bluetooth entry
Assign a unique node name immediately
USA/Canada (Recommended)
2-byte path hash

TEST
Scan the separate private-channel invitation
Open The Maker's Space
Send: test
Instructor replies

CHARGE
Disconnect XIAO USB
Use TP4056 USB-C
Switch may be on or off
If on, keep the antenna attached
Monitor the battery while charging
```
