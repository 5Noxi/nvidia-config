# nvidia-config
Trimmed Driver, NVCPL (NPI) &amp; further configuration.


# NVIDIA Control Panel Configuration
⠀
Enables `Enable Developer Settings`, disables `Add Dekstop Context Menu` and `Show Notification Tray Icon`:
```ps
reg add "HKCU\Software\NVIDIA Corporation\Global\NvCplApi\Policies" /v ContextUIPolicy /t REG_DWORD /d 0 /f
reg add "HKLM\SYSTEM\CurrentControlSet\Services\nvlddmkm\Global\NVTweak" /v NvDevToolsVisible /t REG_DWORD /d 1 /f
reg add "HKLM\SOFTWARE\NVIDIA Corporation\NvTray" /v StartOnLogin /t REG_DWORD /d 0 /f
```
![](?raw=true)
```h
//Profile info related
#define NV_REG_CPL_PERFCOUNT_RESTRICTION  "RmProfilingAdminOnly"
#define NV_REG_CPL_DEVTOOLS_VISIBLE       "NvDevToolsVisible"
```

`NVDisplay.Container.exe` is required for nvcpl to start. [`NV-nvcpl.ps1`]() (included in `NVIDIA-Tool.ps1`) starts them, waits till you close the program, and then terminates them.

`3D Settings > Adjust image settings with preview`
![](?raw=true)
