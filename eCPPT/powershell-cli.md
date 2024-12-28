# PowerShell CLI Commands Cheat Sheet

## Summary
- Launch PowerShell:
  ```cmd
  powershell
  ```
- PowerShell executable locations:
  - 64-bit: `C:\windows\system32\WindowsPowerShell`
  - 32-bit: `C:\windows\SysWOW64\WindowsPowerShell`
- Check if running 64-bit:
  ```ps
  [Environment]::Is64BitProcess
  ```
- Launch as Administrator for full access.

---

## Commands

### Change Execution Policy
Run scripts by bypassing or removing restrictions.
```cmd
powershell.exe -ExecutionPolicy Bypass .\script.ps1
powershell.exe -ExecutionPolicy Unrestricted .\script.ps1
```

### Hide Window
Run scripts without showing the PowerShell window.
```cmd
powershell.exe -WindowStyle Hidden .\script.ps1
```

### Run Commands
Run single commands or script blocks.
```cmd
powershell.exe -Command Get-Process
powershell.exe -Command "& { Get-EventLog -LogName Security }"
```

### Run Encoded Commands
Run base64-encoded commands.
```cmd
powershell.exe -EncodedCommand <encoded-command>
```

### No Profiles
Disable PowerShell profiles when running scripts.
```cmd
powershell.exe -NoProfile .\script.ps1
```

### Downgrade Version
Run PowerShell in a specific version (if available).
```cmd
powershell.exe -Version 2
```

---

## Abbreviations
| **-ExecutionPolicy Bypass** | **-EncodedCommand**    | **-WindowStyle Hidden** |
| --------------------------- | ---------------------- | ----------------------- |
| `powershell.exe -ep Bypass` | `powershell.exe -enco` | `powershell.exe -W h`   |
| `powershell.exe -ex by`     | `powershell.exe -ec`   | `powershell.exe -Wi hi` |

---

## Help Commands

### View Help
```ps
Get-Help <cmdlet>
```

### Detailed Help
```ps
Get-Help <cmdlet> -Full
```

### Examples
```ps
Get-Help <cmdlet> -Examples
```

### Online Help
```ps
Get-Help <cmdlet> -Online
```

### Update Help
```ps
Update-Help
```

---

## List Commands
Find all available cmdlets, functions, and modules.
```ps
Get-Command
```

### Filter Commands
Search for specific commands (e.g., firewall-related).
```ps
Get-Command -Name *Firewall*
```
