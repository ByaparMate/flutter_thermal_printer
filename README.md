# Flutter Thermal Printer (@flutter_thermal_printer)

**Production-ready ESC/POS thermal printing for Flutter — Android & iOS.**

`flutter_thermal_printer` provides a unified API for connecting and printing to compatible ESC/POS thermal printers over:

- 🔵 Bluetooth / BLE
- 🌐 Wi-Fi / Ethernet
- 🔌 USB

Designed for **POS systems, restaurants, retail, invoicing, kiosks, delivery applications, and business software**.

---

## ✨ Features

- Bluetooth / BLE printing
- Wi-Fi / Ethernet printing
- USB printing
- Automatic printer discovery
- Printer connection management
- Automatic reconnect
- Connection status monitoring
- Receipt and invoice printing
- Text formatting
- Multiple font sizes
- Bold, underline, and alignment
- Columns and tables
- Barcode printing
- QR code printing
- Image and logo printing
- Paper feeding
- Paper cutting where supported
- Cash drawer control where supported
- 58mm and 80mm paper support
- Printer capability profiles
- Print queue management
- Connection timeout handling
- Error handling

---

## 📱 Platform Support

| Connection | Android | iOS |
|:---|:---:|:---:|
| Bluetooth | ✅ | ✅ |
| BLE | ✅ | ✅ |
| Wi-Fi / TCP/IP | ✅ | ✅ |
| USB | ✅* | ⚠️ Platform dependent |

> **USB:** Android USB OTG is supported on compatible devices and printer interfaces. iOS has additional restrictions around direct USB communication. Always test your target hardware before production deployment.

---

## 🖨️ Printer Brands & Models

`flutter_thermal_printer` is designed for **ESC/POS-compatible thermal printers**.

The following brands and models represent common ESC/POS printer families that may be suitable for integration.

### Epson

- TM-T20 series
- TM-T88 series
- TM-m30 series
- TM-P20 series

### Xprinter

- XP-58 series
- XP-80 series
- XP-Q200 series
- XP-Q260 series

### Rongta

- RP58 series
- RP80 series
- RP326 series

### BIXOLON

- SRP-350 series
- SRP-330 series
- SRP-E300 series

### Star Micronics

- TSP100 series
- TSP143 series
- mC-Print series

### Other ESC/POS Printers

Many generic and OEM thermal printers support ESC/POS commands and may work with the package.

> **Important:** Compatibility depends on the exact printer model, firmware, connection method, ESC/POS implementation, and platform. A printer being ESC/POS-compatible does not guarantee that every feature is supported.

---

## 🚀 Installation

Add the package to your `pubspec.yaml`:

```yaml
dependencies:
  flutter_thermal_printer: ^1.0.0
```

Then run:

```bash
flutter pub get
```

---

## 🔵 Bluetooth / BLE

Discover nearby printers:

```dart
final printers = await printerManager.discover(
  type: PrinterType.bluetooth,
);
```

Connect and print:

```dart
await printerManager.connect(printer);

await printerManager.print(
  printer,
  bytes,
);
```

Disconnect:

```dart
await printerManager.disconnect(printer);
```

---

## 🌐 Wi-Fi / Ethernet

Create a network printer using its IP address:

```dart
final printer = ThermalPrinter.network(
  ip: '192.168.1.100',
  port: 9100,
);

await printerManager.connect(printer);

await printerManager.print(
  printer,
  bytes,
);
```

Most ESC/POS network printers commonly use raw TCP printing through port `9100`.

> The port and network configuration depend on the printer model.

---

## 🔌 USB

Discover compatible USB printers:

```dart
final printers = await printerManager.discover(
  type: PrinterType.usb,
);

if (printers.isNotEmpty) {
  await printerManager.connect(printers.first);
}
```

> USB support depends on the device, USB interface, operating system, OTG support, and available platform APIs.

---

## 🧾 ESC/POS Printing

The package works with ESC/POS printer data and supports common thermal printing operations such as:

- Text
- Bold
- Underline
- Alignment
- Font sizes
- Columns
- Tables
- Barcodes
- QR codes
- Images
- Logos
- Paper feed
- Paper cut
- Cash drawer control

Printer capabilities vary by model.

---

## 📏 Paper Sizes

Common supported paper sizes include:

- **58mm**
- **80mm**

The actual printable width depends on the printer model, print density, font configuration, and paper mechanism.

---

## ⚠️ Compatibility

ESC/POS is not implemented identically by every manufacturer.

The following features may vary between printers:

- QR codes
- Barcodes
- Images
- Fonts
- Character encoding
- Paper cutting
- Cash drawer control
- Printer status
- Bluetooth protocols
- BLE services
- USB interfaces
- Manufacturer-specific commands

**Always test the exact printer model before deploying to production.**

---

## 🎯 Use Cases

- 🧾 POS systems
- 🍽️ Restaurants
- ☕ Cafes
- 🛍️ Retail stores
- 🏪 Supermarkets
- 🚚 Delivery applications
- 💳 Invoice applications
- 📦 Inventory systems
- 💊 Pharmacy systems
- 🖥️ Kiosks
- 📱 Mobile ordering
- 🎟️ Ticket printing
- 🏷️ Label printing

---

## 🔐 Commercial License

`flutter_thermal_printer` is a **commercial package**.

A commercial license may be required for production and commercial use.

The complete licensing terms are provided in the `LICENSE` file.

Unauthorized redistribution, resale, or publication of the package source code is prohibited unless explicitly permitted by the applicable license.

### Commercial & Enterprise Support

For:

- Commercial licensing
- Enterprise licensing
- Custom printer integration
- Printer compatibility
- Priority support
- Dedicated technical assistance

Contact:

**📧 byaparmate@gmail.com**

---

## 📞 Support

For technical support, licensing, or printer compatibility:

**Email:** `byaparmate@gmail.com`

When reporting a printer issue, please include:

- Printer brand
- Printer model
- Connection type
- Android/iOS version
- Flutter version
- Package version
- Error message
- Relevant logs
- Expected behavior
- Actual behavior

---

## 📄 License

Copyright © 2026

`flutter_thermal_printer` is distributed under a commercial license.

See the [`LICENSE`](LICENSE) file for the complete licensing terms.

---

<div align="center">

## Flutter Thermal Printer

**Reliable ESC/POS printing for Flutter applications.**

**POS • Retail • Restaurants • Invoicing • Kiosks • Business Applications**

📧 **byaparmate@gmail.com**

</div>
