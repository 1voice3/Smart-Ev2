SMART E — SMART EQUIPMENT CONTROLLER SIMULATOR
================================================

CONTENTS
- Smart E.html: self-contained, offline-capable training simulator with embedded data from the supplied controller workbooks.
- README.txt: setup, coverage, references, and safety guidance.

QUICK START
1. Extract the ZIP.
2. Open “Smart E.html” in a current desktop or mobile browser. The simulator has no server, build step, or internet dependency.
3. Choose a controller release from the digital Rolodex.
4. Option 1 uses the simulated LCD/joystick/buttons. Use the on-screen controls or keyboard arrows; ENTER opens a menu/starts editing and CANCEL returns.
5. For a writable workbook point, select it to open the inline editor. The editor enforces the workbook’s writeable flag and provides enumerated choices or the documented data type/IP range. Changes are local training values only.
6. Enter a unit model and serial number if desired. The browser stores these and edited values in local storage for the selected release.
7. Use the left navigation for alarms, backup/firmware lessons, wiring/A2L, settings export, and references.

GITHUB PAGES
Upload the extracted files to a repository. For a repository-root landing page, rename or copy “Smart E.html” to “index.html”. In GitHub, open Settings → Pages and publish from the desired branch/folder. If you keep the requested filename, open its “Smart E.html” URL (the space is URL-encoded). This is a static site with no server-side component.

CONTROLLER RELEASES AND WORKBOOK COVERAGE
The Rolodex includes manual-map cards for SSE 3.2, 3.3, and 3.4, plus all 14 exact Excel releases:
- 4.0.0.1051, 4.0.0.1094, 4.0.1.14, 4.0.2.7
- 4.1.0.3
- 4.2.0.71, 4.2.3.3
- 4.3.0.15, 4.3.1.24, 4.3.2.18
- 4.4.0.31, 4.4.1.3
- 5.0, 5.1.0.235

The Excel workbooks contribute 11,328 version-specific Value records, including 6,123 points marked write-able; 2,051 Trend records; and 3,588 version-specific Events entries. Menus preserve each workbook’s ViewDef short labels/paths, hierarchy, long property names, writeability, data type, precision, IP/SI units and ranges, enumerated choices, presence indicators, and source row citations. Large menus scroll in pages rather than truncating after the first items.

Important import note: the 4.2.0.71 and 4.3.0.15 workbooks declare their worksheet dimensions as ending at row 5 even though their raw worksheet XML contains the full data beneath those blank-looking sections. The simulator imports the underlying rows, including each release’s 10 views, hundreds of point records, and 276 Events entries; they are not partial data sets.

All workbook FactConf sheets contain no populated default-value rows. Accordingly, the simulator does not invent controller readings or factory defaults. Unread points show “Not sampled”; learner changes are marked simulated. The settings worksheet exports all Value records for the selected release, with both IP/SI metadata and an exact workbook/row citation. Only explicitly documented manual baselines are highlighted yellow: #RefrigSys = 4 for release 4.0.0.1051 and OccMode = Schedule for release 5.0. Other baselines are unprovided and remain unhighlighted.

OPTION 2 AND CONNECTION LEARNING
- Legacy 3.x/4.x releases offer an illustrative MAP Gateway 1810 session and the selected workbook’s menu paths. The app does not reproduce vendor screenshots or connect to a Gateway.
- Release 5.0 and 5.1.0.235 offer a simulated Bluetooth/CWa pairing panel. The supplied BLE procedure is specifically documented for Release 5.0; the 5.1 app pairing path is illustrative and must be verified in a matching manual.
- The wiring panel explains the supplied physical connection functions and safety references. Where a workbook has a P2P worksheet, the simulator includes its logical inter-controller signal/object map (101 records for 4.2.3.3, 4.3.1.24, 4.3.2.18, 4.4.0.31, and 4.4.1.3). A P2P map is not a terminal/pin wiring diagram. The other supplied workbooks have no P2P worksheet.
- No complete physical terminal diagrams for every board revision and unit model are supplied. Use the model/serial-specific unit wiring diagram for actual wiring; do not wire from this simulator.
- The detailed RDS jumper note is documented for Release 5.0 only. The supplied replacement-board instructions say to attach the provided jumper to the RDS input when no refrigerant detection sensor is installed. If an RDS is installed, wire it per the exact unit diagram; never fit the no-sensor jumper as a substitute.

ALARM SEARCH
Search uses the selected release’s complete Events worksheet plus the supplied manual alarm text. Workbook results cite the exact file and Events row and show severity, source attribute, event state, identifiers, auto-clear, and cross-line metadata. The Events sheet does not provide full alarm trigger logic for every entry; manual excerpts provide documented trigger conditions where available. Search terms/selections are highlighted red.

BACKUP, RESTORE, AND FIRMWARE TRAINING
The interactive lessons teach preparation, backup-before-update, package verification, USB format/capacity checks, safe update sequencing, and post-update validation. Source instructions include FAT/FAT32, the 4.0 procedure’s 16 GB maximum, accessory disconnect/reconnect timing, and newer-board FAT32 guidance. Exact requirements vary by release; follow the exact manual. The app cannot format a real drive, read/write controller files, restore settings, or install firmware. Package names shown are references only; firmware binaries are not embedded.

SOURCE REFERENCES (PRINTED PAGE NUMBERS)
- 1136326-USG-E-0117, Smart Equipment Controls Quick Start Guide 3.2, pp. 8–19: legacy LCD/menu maps and example settings.
- S1-03527190000-A-0118, Smart Equipment Version 3.3.1.186 update kit, pp. 1–2: firmware update and MAP Gateway instructions.
- Smart Equipment Firmware Update 4.0 Instructions, pp. 1–5: FAT/FAT32, 16 GB maximum in that procedure, SA Bus/J15 accessory sequence, update phases/reboots.
- SSE Alarms, Smart Equipment Unit Controls Sequence of Operation Overview, pp. 63–71: alarm severity, names, and trigger descriptions.
- Updated Instructions for Replacing SSE Board 1, pp. 1–2: backup/restore and 4.0 #RefrigSys note.
- LIT-12011938, Smart Equipment Controls Quick Start Guide Release 5.0, pp. 2–5: USB backup/restore/update and BLE/CWa.
- LIT-12011998, Smart Equipment Controls Technical Bulletin Release 5.0, pp. 5–10: menu taxonomy and controller structure.
- LIT-12011950, Smart Equipment Controls Sequence of Operation Technical Bulletin Release 5.0, p. 64 and pp. 89–94: A2L/RDS operation, alarms, and BLE enablement (p. 94).
- S1-03526539001 A-0824, Replacement Board Factory Configuration, pp. 1–3: RDS jumper, FAT32, backup/restore, and Bluetooth enablement.
- SSE Board – SD / Low Input Alarms, pp. 1–2: low-voltage/smoke-detector checks and safety note.
- VFD Control Wiring due to Brand Changes, pp. 1–6: Mitsubishi-specific VFD signal example only.
- Each workbook’s ViewDef, Events, and P2P sheets (where available): see the source file/worksheet-row citations inside the simulator and exported XLSX.

SAFETY AND LIMITS
Smart E is an educational simulator—not an HVAC controller, service tool, diagnostic device, certified wiring diagram, firmware updater, or source of approved settings. It cannot read a live UCB, operate outputs, clear alarms, discover/connect a Gateway, scan/pair Bluetooth, validate a real USB drive, or update equipment. All downloads are labeled simulated examples. Never defeat safety circuits. Confirm all service steps, wiring, firmware compatibility, and settings against current manufacturer documentation for the exact unit, model, serial, board revision, and accessories.
