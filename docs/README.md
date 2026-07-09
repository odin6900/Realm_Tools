# 👑 Realm Tools

A premium, high-performance, standalone desktop utility suite. Optimized for native execution, zero-dependency deployment, and advanced memory operations.

---

## 📸 Showcase

![Realm Tools Premium UI](./image/Screenshot%202026-07-07%20003639.png)

---

## ✨ Premium UI & Aesthetics

- **Custom Interactive Backgrounds**: Uses dynamic, high-performance particle simulation backends supporting:
  - **Dot particles**: Soft-glowing, smooth floating points.
  - **Triangle particles**: Ambient floating geometric shapes with controlled density.
  - **Network Line (Matrix) particles**: Interactive networking nodes that dynamically form link connections as they float close to each other.
- **Glassmorphic Theme**: Dark mode panels with glowing neon borders, subtle accent outlines, and smooth fade-in tab transitions.
- **Perfect Dragging Experience**: Custom non-blocking Win32 window movement handles dragging seamlessly without stalling or freezing rendering frames or animations.
- **Dynamic Accent Color Picker**: Fully customize the primary theme accent and hover colors directly inside the interface. Select your favorite custom shade using the integrated color spectrum wheel under Settings.

---

## 🛠️ Feature Modules & How to Use

### 1. AimBot (Memory Scanner & Modifier)
- **Normal Mode (One-Shot)**: Performs an AoB scan on the target process memory, reads values at `Address + Read Offset`, and automatically writes the modification values to `Address + Write Offset`. Stored original values are tracked for safe reversion when deactivating.
- **Loop Mode (Continuous)**: Continuously updates target addresses in a high-speed background thread.
- **State Control**: The **ACTIVATE** button switches dynamically to **DEACTIVATE** when running. Clicking it while active stops the loop thread or safely reverts the memory changes made during normal mode.
- **How to Use**:
  1. Input the target process name (e.g., `HD-Player`) or click **SELECT** to choose from active processes.
  2. Input your AoB Code sequence (supports standard hexadecimal wildcards like `??`).
  3. Enter Read/Write offsets (hex format `0xFA` or decimal `250`).
  4. Select scan Type (**Normal** or **Loop**).
  5. Click **ACTIVATE**. You will hear a success beep when the scanner finds and modifies the matching memory blocks.

### 2. Code Replace
- **How to Use**:
  1. Specify the target process name.
  2. Input the search pattern (original bytes) in the **Search Code** box.
  3. Input the modification bytes in the **Replace Code** box.
  4. Click the swap button (`⇆`) if you want to invert the search and replace values.
  5. Click **REPLACE** to apply. A beep sound will confirm the successful replacement.

### 3. AoB Refiner / Pattern Comparer
Automatically generates a refined wildcard AoB pattern by reading and cross-comparing raw memory bytes from multiple locations. It accepts two input modes:

- **Address Mode**: Paste a list of Cheat Engine-style memory addresses (one per line, e.g., `0x1A2B3C4D5E6F`). The tool reads a configurable block of bytes at each address from the live process, then compares all blocks side-by-side — bytes that are identical across all addresses are kept, differing bytes are automatically replaced with `??`.
- **AOB Pattern Mode**: Paste an existing AoB search pattern (hex bytes optionally containing `?` / `??` wildcards). The refiner scans the target process memory for all instances of that pattern, reads a byte block the same length as the pattern at every matching address, and performs the same cross-comparison to produce a tighter, more unique wildcard signature.

**Configuration Options**:
- **Read Length** (Address Mode): How many bytes to read at each address — `32`, `64`, `128`, `256`, or `512` bytes.
- **Line Width**: Display width of the generated pattern output — `16` or `32` bytes per row (cosmetic, does not affect the exported pattern).

**How to Use**:
1. Input the target process name or click **SELECT** to pick from the active process list.
2. Paste your memory addresses or existing AoB pattern into the **Byte Sequences / AOB Input** box.
3. Select the desired **Read Length** and **Line Width** from the dropdowns.
4. Click **REFINE AOB**. The tool processes in a background thread and shows a notification when done.
5. The generated wildcard pattern appears in the **Generated Wildcard AOB** output box (read-only, fully selectable and copyable).
6. Optionally click **EXPORT** to save the raw single-line pattern to `output.txt` next to the executable. File Explorer will automatically open and highlight the exported file.

### 4. DLL Injector
- **How to Use**:
  1. Choose your target process.
  2. Click **ADD DLL**. This launches the native Windows File Explorer dialog.
  3. Select your `.dll` file.
  4. Toggle DLLs inside the list box using the control buttons (**ENA/DISA**, **REMOVE**, **CLEAR**, **RESET**).
  5. Click **INJECT**. Successful injection plays a confirmation beep.

---

## ⚡ Technical Features

- **Full Clipboard Integration**: Native Win32 integration supports **Ctrl+A** (Select All), **Ctrl+C** (Copy), **Ctrl+V** (Paste), and **Ctrl+X** (Cut) across all text input fields.
- **Administrative Privileges**: Requests standard elevation (`requireAdministrator`) automatically on launch.
- **Always On Top**: Checkbox option to lock the utility window z-order above other applications.
- **Task Manager Details Process Search**: Click **SELECT** on any tab to show all active window processes and background services, populated with matching application icons extracted dynamically from executable files.

---

## 🚀 How to Run
To run the application, download the standalone release containing `Realm Tools.exe` and execute it on a 64-bit Windows environment.

> [!IMPORTANT]
> Since this tool performs memory scanning, reading/writing offsets, and injecting DLLs, it requires administrative privileges to access target process memory. It will automatically prompt for elevated permissions on launch.

Output package structure:
```
├── Realm Tools.exe
├── LICENSE.txt
└── README.md
```
