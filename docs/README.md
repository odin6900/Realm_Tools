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

### 3. DLL Injector
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
