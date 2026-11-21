
# Cisco IOS – Basic Switch & Router Commands

## 1. CLI Navigation

```
enable
disable
configure terminal
exit
end
```

## 2. Basic Device Configuration

```
hostname SW1
```

## 3. Privileged EXEC Password

```
enable secret PASSWORD
enable password PASSWORD
```

## 4. Console Line Password

```
line console 0
password PASSWORD
login
exit
```

## 5. Password Encryption

```
service password-encryption
```

## 6. Configuration Verification

```
show running-config
show startup-config
```

## 7. Saving Configuration

```
copy running-config startup-config
write memory
wr
```

## 8. Restarting the Device

```
reload
```

## 9. Interface Identification

```
interface FastEthernet0/1
interface GigabitEthernet0/1
interface TenGigabitEthernet1/0/1
```

## 10. Useful Command Combinations

### Initial Device Configuration

```
enable
configure terminal
hostname SW1
enable secret PASSWORD
service password-encryption
```

### Configure Console Password

```
enable
configure terminal
line console 0
password PASSWORD
login
exit
```

### Save Configuration

```
enable
copy running-config startup-config
```

### Display Configurations

```
show running-config
show startup-config
```

### Restart Device

```
reload
```

---

## Quick Reference

|Command|Purpose|
|---|---|
|`enable`|Enter Privileged EXEC Mode|
|`disable`|Return to User EXEC Mode|
|`configure terminal`|Enter Global Configuration Mode|
|`hostname SW1`|Change device hostname|
|`enable secret PASSWORD`|Set privileged EXEC password|
|`enable password PASSWORD`|Set legacy privileged EXEC password|
|`line console 0`|Enter console line configuration|
|`password PASSWORD`|Set line password|
|`login`|Enable line password authentication|
|`service password-encryption`|Encrypt supported plaintext passwords (Type 7)|
|`show running-config`|Display active configuration|
|`show startup-config`|Display saved configuration|
|`copy running-config startup-config`|Save active configuration|
|`write memory`|Alternative save command|
|`wr`|Abbreviated save command|
|`reload`|Restart device|
|`exit`|Exit current mode|
|`end`|Return to Privileged EXEC Mode|
|`Ctrl + Z`|Return to Privileged EXEC Mode|