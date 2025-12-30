# Papyrix User Guide

Welcome to the **Papyrix** firmware. This guide outlines the hardware controls, navigation, and reading features of
the device.

## 1. Hardware Overview

The device utilises the standard buttons on the Xtink X4 in the same layout:

### Button Layout
| Location        | Buttons                                    |
|-----------------|--------------------------------------------|
| **Bottom Edge** | **Back**, **Confirm**, **Left**, **Right** |
| **Right Side**  | **Power**, **Volume Up**, **Volume Down**  |

---

## 2. Power & Startup

### Power On / Off

To turn the device on or off, **press and hold the Power button for half a second**. In **Settings** you can configure
the power button to trigger on a short press instead of a long one.

### First Launch

Upon turning the device on for the first time, you will be placed on the **Home** screen.

> **Note:** On subsequent restarts, the firmware will automatically reopen the last book you were reading.

---

## 3. Screens

### 3.1 Home Screen

The Home Screen layout can be configured in Settings (see **Home Layout** setting):

#### Grid Layout (default)
A **2x2 grid** with four options:
- **READ** (top-left) — Continue reading your last book (shows "N/A" if no book loaded)
- **FILES** (top-right) — Browse and select books from the SD card
- **SYNC** (bottom-left) — File transfer via WiFi web server
- **SETUP** (bottom-right) — Device settings

#### List Layout
A vertical menu with:
- **Continue: [Book Name]** — Resume reading (only shown if a book is open)
- **Browse** — Browse and select books from the SD card
- **File transfer** — Upload files via WiFi web server
- **Settings** — Device settings

**Navigation:**
* Use **Left/Right** or **Volume Up/Down** to move between options
* Press **Confirm** to select an option

### 3.2 Book Selection (Files)

The Files screen acts as a folder and file browser.

* **Navigate List:** Use **Left** (or **Volume Up**), or **Right** (or **Volume Down**) to move the selection cursor up
  and down through folders and books.
* **Open Selection:** Press **Confirm** to open a folder or read a selected book.

> **Note:** Both EPUB (.epub) and XTC (.xtc, .xtch) file formats are supported. The device supports both FAT32 and exFAT formatted SD cards.

### 3.3 Reading Screen

See [4. Reading Mode](#4-reading-mode) below for more information.

### 3.4 File Transfer (Sync)

The Sync screen allows you to upload new e-books to the device over WiFi.

When you enter the screen, you'll be prompted to choose a network mode:

* **Join Network:** Connect to an existing WiFi network. You'll see a list of available networks and can enter passwords as needed. Previously saved networks will connect automatically.
* **Create Hotspot:** The X4 creates its own WiFi network that you can connect to directly from your computer or phone.

Once connected, your X4 will start hosting a web server. See the [webserver docs](./docs/webserver.md) for more
information on how to connect and upload files.

### 3.5 Settings

The Settings screen allows you to configure the device's behavior:

- **Sleep Screen** (default: Dark)
  - Options: Dark, Light, Custom, Cover
  - Which image to display when the device sleeps

- **Status Bar** (default: Full)
  - Options: None, No Progress, Full
  - Status bar display during reading

- **Extra Paragraph Spacing** (default: ON)
  - Add vertical space between paragraphs (OFF uses first-line indentation instead)

- **Font Size** (default: Normal)
  - Options: Small (14pt), Normal (16pt), Large (18pt)
  - Text size for reading

- **Show Book Cover** (default: ON)
  - Display the book cover image as the first page when reading

- **Short Power Button Click** (default: OFF)
  - Whether to trigger power on a short press (ON) or long press (OFF)

- **Sleep Timeout** (default: 10 min)
  - Options: 5 min, 10 min, 15 min, 30 min
  - Time of inactivity before the device automatically sleeps

- **Home Layout** (default: Grid)
  - Options: Grid, List
  - Home screen layout style (2x2 grid or vertical list)

- **Reading Orientation** (default: Portrait)
  - Options: Portrait, Landscape CW, Inverted, Landscape CCW
  - Screen orientation for reading

- **Front Button Layout** (default: Default)
  - Options: Default (Back/Confirm/Left/Right), Swapped (Left/Right/Back/Confirm)

- **Check for updates**
  - Check for and install firmware updates via WiFi

### 3.6 Sleep Screen

You can customize the sleep screen by placing custom images in specific locations on the SD card:

- **Single Image:** Place a file named `sleep.bmp` in the root directory.
- **Multiple Images:** Create a `sleep` directory in the root of the SD card and place any number of `.bmp` images
  inside. If images are found in this directory, they will take priority over the `sleep.bmp` file, and one will be
  randomly selected each time the device sleeps.

> [!NOTE]
> You'll need to set the **Sleep Screen** setting to **Custom** in order to use these images.

#### Image Parameters

| Parameter | Recommended Value |
|-----------|-------------------|
| Resolution | 480 × 800 pixels (portrait mode) |
| Color depth | 8-bit grayscale or 24-bit color |
| Format | BMP, uncompressed (BI_RGB) |
| Display levels | 4 grayscale (black, dark gray, light gray, white) |

> [!TIP]
> - Use 8-bit grayscale for best results - it's widely supported by image editors
> - Larger images will be automatically scaled down while preserving aspect ratio
> - All color images are converted to 4-level grayscale on the e-ink display

> [!TIP]
> The **Cover** sleep screen option displays the cover of the currently open book when the device sleeps.

---

## 4. Reading Mode

Once you have opened a book, the button layout changes to facilitate reading.

### Page Turning
| Action            | Buttons                              |
|-------------------|--------------------------------------|
| **Previous Page** | Press **Left** _or_ **Volume Up**    |
| **Next Page**     | Press **Right** _or_ **Volume Down** |

### Chapter Navigation
* **Next Chapter:** Press and **hold** the **Right** (or **Volume Down**) button briefly, then release.
* **Previous Chapter:** Press and **hold** the **Left** (or **Volume Up**) button briefly, then release.

### System Navigation
* **Return to Home:** Press **Back** to close the book and return to the Book Selection screen.
* **Chapter Menu:** Press **Confirm** to open the Table of Contents/Chapter Selection screen.

---

## 5. Chapter Selection Screen

Accessible by pressing **Confirm** while inside a book.

1.  Use **Left** (or **Volume Up**), or **Right** (or **Volume Down**) to highlight the desired chapter.
2.  Press **Confirm** to jump to that chapter.
3.  *Alternatively, press **Back** to cancel and return to your current page.*

---

## 6. Current Limitations & Roadmap

Please note that this firmware is currently in active development. The following features are **not yet supported** but
are planned for future updates:

* **Images:** Embedded images in e-books will not render.
