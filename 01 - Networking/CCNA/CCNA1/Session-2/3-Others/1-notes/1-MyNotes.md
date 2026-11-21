# Cisco Switches and Basic Configuration

## 1. Switch Interfaces and Console Port

### 1.1. Switch Interfaces (Ethernet Ports)

- Switch interfaces (also called ports) are the physical connections where network devices, such as computers, printers, and other switches, are connected.
    
- These interfaces allow connected devices to communicate with each other within the same Local Area Network (LAN).
    
- Ordinary Ethernet interfaces are primarily used to forward network traffic. They are not normally used for initial switch configuration.
    
- Each interface has specific characteristics, such as speed, duplex mode, and operational status.
    

### 1.2. Interface Naming and Speeds

Cisco uses different abbreviations to identify Ethernet interface speeds:

|Abbreviation|Technology|Speed|
|---|---|---|
|`Fa`|Fast Ethernet|100 Mbps|
|`Gi`|Gigabit Ethernet|1 Gbps (1000 Mbps)|
|`Te`|Ten-Gigabit Ethernet|10 Gbps|

Examples of Cisco interface names:

- `FastEthernet0/1`
    
- `GigabitEthernet0/1`
    
- `TenGigabitEthernet1/0/1`
    

**Note:** Interface naming conventions and available speeds depend on the switch model.

### 1.3. Console Port (Line Console)

- The console port is a special physical interface used to access and configure a switch or router locally.
    
- Unlike ordinary Ethernet interfaces, the console port does not carry normal network traffic.
    
- It provides out-of-band management access, meaning that an administrator can configure the device without requiring an operational network connection.
    
- Both switches and routers have a console line, commonly identified as `line console 0` in Cisco IOS.
    
- The physical console port is connected to a computer using a console cable.
    
- The console connection is especially useful during initial configuration, troubleshooting, and network recovery.
    

**Terminology:**

- Console port: The physical connection on the device.
    
- Console line: The logical configuration line associated with console access.
    
- Ethernet interface: A physical network interface used to transmit and receive network traffic.
    

### 1.4. Connecting to a Switch Through the Console Port

To configure a switch for the first time, we can connect a computer to its console port.

Required equipment and software:

- A computer.
    
- A console cable (USB-to-console or serial-to-console, depending on the equipment).
    
- Terminal emulation software, such as PuTTY or Tera Term.
    

**Configuration steps using PuTTY:**

1. Connect the computer to the switch's console port using a console cable.
    
2. Open PuTTY.
    
3. Select `Serial` as the connection type.
    
4. Identify the COM port assigned to the console connection:
    
    - Open Windows Device Manager.
        
    - Expand `Ports (COM & LPT)`.
        
    - Identify the assigned COM port.
        
5. Enter the COM port in PuTTY under `Serial line`.
    
6. Configure the serial connection settings according to the switch requirements (commonly 9600 baud, 8 data bits, no parity, 1 stop bit, and no flow control).
    
7. Click `Open` to establish the connection.
    
8. Press Enter if necessary to display the Cisco IOS command-line interface (CLI).
    

**Note:** The console port is a common initial configuration method, but it is not the only way to manage a Cisco device. After configuring the appropriate network interfaces and management settings, administrators can also access devices remotely through methods such as SSH.

---

## 2. Cisco IOS Command-Line Interface (CLI) Modes

Cisco devices use different CLI modes to control access to commands and configuration settings.

This is an example of privilege separation: different users can be granted different levels of access depending on their responsibilities.

### 2.1. User EXEC Mode

- This is the initial CLI mode users normally enter after connecting to a Cisco device.
    
- It provides limited access to basic monitoring and troubleshooting commands.
    
- Users cannot make configuration changes from this mode.
    
- It is identified by the `>` symbol.
    

Example:

```
Switch>
```

### 2.2. Privileged EXEC Mode

- This mode provides access to advanced monitoring, troubleshooting, and device management commands.
    
- It allows administrators to enter Global Configuration Mode.
    
- It is identified by the `#` symbol.
    
- We access it from User EXEC Mode using the `enable` command.
    

Example:

```
Switch> enable
Switch#
```

To return to User EXEC Mode:

```
Switch# disable
Switch>
```

### 2.3. Global Configuration Mode

- This mode allows administrators to modify the device's global configuration.
    
- It is accessed from Privileged EXEC Mode using the `configure terminal` command.
    
- It is identified by `(config)#`.
    
- From this mode, administrators can configure the hostname, passwords, interfaces, console access, and other device settings.
    

Example:

```
Switch# configure terminal
Switch(config)#
```

### 2.4. CLI Mode Navigation

The basic CLI mode hierarchy is:

```
User EXEC Mode
      |
      | enable
      v
Privileged EXEC Mode
      |
      | configure terminal
      v
Global Configuration Mode
      |
      | interface / line / other commands
      v
Specific Configuration Submodes
```

To return to Privileged EXEC Mode:

```
Switch(config)# end
Switch#
```

Alternatively, press `Ctrl + Z`.

**Important:** Global Configuration Mode is not the only submode available from Privileged EXEC Mode. It contains several configuration submodes, such as Interface Configuration Mode and Line Configuration Mode.

### 2.5. Common CLI Navigation Commands

|Command|Purpose|
|---|---|
|`enable`|Enter Privileged EXEC Mode.|
|`disable`|Return to User EXEC Mode.|
|`configure terminal`|Enter Global Configuration Mode.|
|`exit`|Leave the current mode or close the current session when used at the appropriate level.|
|`end`|Return directly to Privileged EXEC Mode.|
|`Ctrl + Z`|Return directly to Privileged EXEC Mode.|
|`reload`|Restart the device.|

**Understanding access levels:**

- User EXEC Mode: Limited access, suitable for basic monitoring.
    
- Privileged EXEC Mode: Higher privileges, suitable for advanced monitoring and device administration.
    
- Global Configuration Mode: Used to modify the device configuration.
    

For example, a network technician responsible for auditing network status may only need limited access, while a network administrator requires higher privileges to manage and configure the device.

---

## 3. Basic Switch Configuration

### 3.1. Displaying the Current Configuration

To display the configuration currently running on the switch:

```
Switch# show running-config
```

This command displays the active configuration stored in RAM.

### 3.2. Changing the Switch Hostname

The hostname identifies the device in the CLI.

To change the switch hostname:

```
Switch> enable
Switch# configure terminal
Switch(config)# hostname SW1
SW1(config)#
```

The prompt changes immediately after the hostname is modified.

**Note:** The hostname command does not configure passwords. Password configuration is a separate process.

---

## 4. Password Configuration

Cisco IOS provides different methods to protect access to the device.

### 4.1. Configuring the Privileged EXEC Password

There are two commonly introduced commands:

**Method 1:** `**enable secret**`

```
Switch> enable
Switch# configure terminal
Switch(config)# enable secret MyPassword123
```

- Configures a password required to access Privileged EXEC Mode.
    
- Stores the password using a secure one-way hash rather than as clear text.
    
- Preferred over `enable password`.
    

**Method 2:** `**enable password**`

```
Switch(config)# enable password MyPassword123
```

- Configures a password for Privileged EXEC Mode.
    
- By default, this password is stored in a reversible or clear-text form, depending on the configuration and platform.
    
- It is less secure than `enable secret`.
    

**Important:** If both `enable secret` and `enable password` are configured, Cisco IOS uses `enable secret` for Privileged EXEC authentication.

### 4.2. Configuring a Console Line Password

A console password protects local access through the physical console connection.

Configuration steps:

```
Switch> enable
Switch# configure terminal
Switch(config)# line console 0
Switch(config-line)# password Console123
Switch(config-line)# login
Switch(config-line)# exit
```

Explanation:

- `line console 0`: Enters Console Line Configuration Mode.
    
- `password Console123`: Defines the console password.
    
- `login`: Enables password authentication when accessing the console line.
    
- `exit`: Returns to the previous configuration mode.
    

**Note:** The `login` command is necessary for the configured line password to be requested during console access.

### 4.3. Encrypting Line Passwords in the Configuration

By default, passwords configured using commands such as `password` under a console line may appear in clear text in the running configuration.

To obfuscate these passwords:

```
Switch# configure terminal
Switch(config)# service password-encryption
```

This command applies reversible Type 7 encryption to supported plaintext passwords in the configuration.

To verify:

```
Switch# show running-config
```

**Security note:** `service password-encryption` provides weak encryption and should not be considered strong password protection. Prefer stronger authentication methods and secure password hashing where supported.

---

## 5. Saving and Managing Configurations

Cisco devices maintain two important configuration files.

### 5.1. Running Configuration

- Represents the configuration currently active on the device.
    
- Stored in RAM (Random Access Memory).
    
- Changes made through the CLI are generally applied immediately.
    
- It is volatile, meaning it is lost when the device loses power or restarts unless saved.
    

### 5.2. Startup Configuration

- Contains the configuration that the device loads during startup.
    
- Stored in NVRAM (Non-Volatile Random Access Memory), or equivalent non-volatile storage depending on the platform.
    
- It is retained after the device is powered off or restarted.
    
- During startup, Cisco IOS loads the startup configuration into the running configuration.
    

### 5.3. Differences Between Running and Startup Configurations

|Feature|Running Configuration|Startup Configuration|
|---|---|---|
|Purpose|Current active configuration|Configuration loaded at startup|
|Storage|RAM|NVRAM|
|Volatile|Yes|No|
|Changes|Updated when configuration commands are applied|Updated when configuration is explicitly saved|

**Important:** If we modify the running configuration but do not save it, those changes will normally be lost after a restart.

### 5.4. Saving the Running Configuration

There are several equivalent commands for saving the current running configuration into startup configuration.

**Method 1:**

```
Switch# write memory
```

**Method 2:**

```
Switch# wr
```

**Method 3 (recommended for learning):**

```
Switch# copy running-config startup-config
```

All three methods save the current configuration so that it is retained after restarting the switch.

To verify the saved configuration:

```
Switch# show startup-config
```

**Important:** Restarting the switch is not necessary after every configuration change. Cisco IOS applies most configuration commands immediately. Save the configuration when you want the changes to persist after a restart.

### 5.5. Restarting the Switch

To restart the switch:

```
Switch# reload
```

Cisco IOS may ask whether you want to save the configuration before restarting.

- If you have already saved your configuration, you can proceed.
    
- If you have unsaved changes that you want to keep, save them first.
    
- If you do not want to keep the unsaved changes, do not save them.
    

---

## 6. Applying Basic Configuration to Routers

Most of the basic configuration commands introduced in this section also apply to Cisco routers.

Examples include:

- Changing the hostname.
    
- Configuring the Privileged EXEC password.
    
- Configuring the console line password.
    
- Navigating between CLI modes.
    
- Displaying the running configuration.
    
- Saving the running configuration.
    
- Restarting the device.
    

However, switches and routers have different interface types and additional device-specific configuration commands.

---

## 7. Quick Command Reference

|Command|Description|
|---|---|
|`enable`|Enter Privileged EXEC Mode.|
|`disable`|Return to User EXEC Mode.|
|`configure terminal`|Enter Global Configuration Mode.|
|`hostname SW1`|Change the device hostname.|
|`enable secret PASSWORD`|Configure a secure Privileged EXEC password.|
|`enable password PASSWORD`|Configure a legacy Privileged EXEC password.|
|`line console 0`|Enter Console Line Configuration Mode.|
|`password PASSWORD`|Configure a line password.|
|`login`|Require password authentication on a line.|
|`service password-encryption`|Obfuscate supported plaintext passwords in the configuration.|
|`show running-config`|Display the active configuration.|
|`show startup-config`|Display the saved startup configuration.|
|`copy running-config startup-config`|Save the active configuration.|
|`write memory`|Alternative command to save the configuration.|
|`reload`|Restart the device.|
|`exit`|Leave the current configuration level.|
|`end`|Return directly to Privileged EXEC Mode.|

**Final reminder:** Always save your configuration using `copy running-config startup-config` when you want your changes to survive a restart.