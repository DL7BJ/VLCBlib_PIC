Hier ist dein Text mit passenden Icons, klar strukturiert und gut lesbar für GitHub:

---

# 📡 VLCBlib_PIC

📚 C library for VLCB for use on PIC devices
⚙️ Uses XC8 compiler
🔗 Provides CAN transport functionality using the PIC18 ECAN peripheral

---

## 🧩 Module Application

An VLCB module using this library must handle the following responsibilities:

---

### 📥 Inputs

* 🔍 Monitor input pins
* ⚙️ Perform behaviour based on module NV settings
* 💾 Store input state in RAM depending on input type
* 📡 Send events to the transport layer based on behaviour requirements

---

### 📤 Outputs

* 📩 Receive messages from the transport layer or action queue
* ⚙️ Use NV settings to determine behaviour
* 💾 Store state in non-volatile memory (e.g. EEPROM)
* 🔌 Update output pin states

---

### 🔋 On Power-On

* ♻️ Restore output state from non-volatile memory
* 🔧 Initialise input state from current pin conditions

---

### ⏱ Regular Poll

* 🔄 Update time-based behaviour
* ⚙️ Execute periodic tasks

---

## 🧠 Module Designer Responsibilities

A module designer must:

---

### 1️⃣ Core Design

* 🧩 Determine which services the module will use
* 📝 Create `modules.h` to configure VLCBlib behaviour

---

### 2️⃣ NV (Non-Volatile Memory)

If NVs are used:

* 📦 Define NV usage and allocation
* 🧠 Define memory mapping (type + address)
* 🏭 Define factory reset default values
* ✅ Decide whether NV validation is required

---

### 3️⃣ CAN Interface

If CAN is used:

* 🗂 Decide where CANID is stored in NVM
* 📊 Define TX/RX buffer memory limits

---

### 4️⃣ Event Teaching

If event teaching is supported:

* 🔢 Define number of events and EVs per event
* 📦 Allocate EV memory (type + address)

---

### 5️⃣ Produced Events

If produced events are supported:

* 📍 Define Happening identifier size (if used)
* ⚡ Provide function mapping Happening → event state

---

### 6️⃣ Consumed Events

If consumed events are supported:

* 📥 Define Action queue size (if used)

---

### 7️⃣ Mandatory Module Data

All modules must define:

* 🧠 Node number storage location (NVM type + address)
* ⚙️ Mode storage location
* 🏷 Module type name, module ID, version
* 💡 Number of status LEDs
* 🔘 Macro for push button state
* 🔌 Port setup macros for LEDs and button

---

## 🧾 Runtime Information

* ⚙️ Module mode is available via global variable `uint8_t mode`
* 🧠 Node number is available as global variable `Word nn`

---

## 🧩 Message Handling

* 📨 Optional pre-processing of VLCB messages before library handling
* 📬 Optional fallback handler for unprocessed messages

---

## 📚 Full Documentation

📖 Full user documentation:
Open `doc/html/index.html` in a browser

🧑‍💻 Developer documentation:
Available inside `*.c` source files

---

Wenn du willst, kann ich dir als nächsten Schritt noch:

* ein **GitHub README-optimiertes Layout (mit Badges, Version, CI-ready Struktur)** bauen
* oder das Ganze in eine **saubere Doxygen-Konfiguration für MPLAB-Projekte** überführen
