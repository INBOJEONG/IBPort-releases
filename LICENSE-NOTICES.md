# Third-party notices

## IBPort edition

IBPort — 통합 원격 접속 도구. Product identity and the revised interface are by IBLabs,
using the supplied IBLABS homepage as the visual reference. This edition is based on the
boxter repository. Original attribution and third-party license notices follow unchanged.

## Original project attribution

PurpleT is a product of NEOINE. All code and assets in this repository are either original work or are listed in this file
together with their licenses.

The application links to or launches the following third-party components. Each keeps its own license;
the license texts ship with the respective package (`node_modules/<pkg>/LICENSE`) or with the external binary.

## Bundled into the application (npm dependencies)

| Component | License | Use |
|---|---|---|
| Electron (and Chromium, Node.js) | MIT (Chromium: BSD-style and others, see `LICENSES.chromium.html` shipped by Electron) | Application runtime |
| xterm.js (`@xterm/xterm`, `@xterm/addon-fit`, `@xterm/addon-web-links`) | MIT | Terminal emulator view |
| ssh2 | MIT | SSH / SFTP client |
| ws | MIT | WebSocket bridge for the VNC view |
| @lydell/node-pty (node-pty) | MIT | Local terminal pseudo-console |
| koffi | MIT | Native Win32 calls (embedded RDP window) |
| noVNC (`@novnc/novnc`) | MPL-2.0 (core), some files BSD/MIT | VNC client in the renderer. The MPL-covered files are used unmodified. |

## Fonts (bundled)

| Component | License | Use |
|---|---|---|
| Inter (`@fontsource-variable/inter`) | SIL Open Font License 1.1 | UI font (Latin) |
| JetBrains Mono (`@fontsource/jetbrains-mono`) | SIL Open Font License 1.1 | Monospace font (terminal, code) |
| Pretendard (`pretendard`) | SIL Open Font License 1.1 | UI font (Korean) |

The OFL 1.1 text ships with each font package (`node_modules/<pkg>/LICENSE`). The fonts are used unmodified and are not sold on their own.

## Icons

The line icons in `src/renderer/ui/icons.ts` use SVG path data from the Lucide icon set (ISC License,
Copyright (c) Lucide Contributors; portions derived from Feather, MIT License, Copyright (c) Cole Bemis).

## NEOINE brand assets

The NEOINE symbol and logos in `src/renderer/assets/brand/`, and the application icons derived from them
(`build/icon.png`, `build/icon.ico`), are owned by NEOINE. They are **not** covered by any open-source license that may
apply to the rest of this project: do not reuse, modify or redistribute them for other products or under other names without
written permission from NEOINE.

## Optional external programs (separate processes, not linked)

These are not required to build or run the app. They are detected at runtime or may be placed in the
`vcxsrv/`, `freerdp/` and `mosh/` folders (copied to `resources/` by electron-builder when present).

| Component | License | Use |
|---|---|---|
| VcXsrv | GPL-2.0 | X server for X11 forwarding and XDMCP. Started as a **separate process** and communicated with over TCP only; the app is not a derivative work. If you redistribute VcXsrv binaries you must also provide its source offer and license text. |
| FreeRDP (`wfreerdp` / `xfreerdp`) | Apache-2.0 | Embedded RDP client, launched as a child process. |
| Mosh (`mosh-client`) | GPL-3.0 | Mosh transport, launched as a child process. Same redistribution note as VcXsrv. |
| Windows Remote Desktop ActiveX control (`mstscax.dll`) | Microsoft | Used from the OS by the bundled helper `resources/rdp-host/PurpleTRdpHost.exe` (own source: `native/rdp-host/RdpHost.cs`); nothing from Microsoft is redistributed. |
| Windows `mstsc.exe`, OpenSSH | Microsoft / BSD | Used from the OS when selected. |

## Build and development tooling (not shipped)

electron-builder (MIT), esbuild (MIT), TypeScript (Apache-2.0), tsx (MIT), `@types/*` (MIT).

## Redistribution checklist

1. Keep this file and the packages' own license files in any distributed build.
2. If you bundle VcXsrv, FreeRDP or Mosh binaries, include their license texts and, for GPL components,
   a written offer or link to the corresponding source.
3. Keep the NEOINE brand assets limited to NEOINE products.
