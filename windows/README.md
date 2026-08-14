# Windows

## Firmware & Drivers

- [MoKiChU Drivers/Firmware/Software](https://rog-forum.asus.com/t5/hardware-build-advice/index-all-my-drivers-firmware-software-threads/m-p/827232)

## Sudo

```sh
sudo config --enable normal
```

- [Sudo for Windows](https://learn.microsoft.com/en-us/windows/advanced-settings/sudo/)

## Dev Drive

```sh
Mount-VHD -Path 'C:\Dev.vhdx'
```

```sh
fsutil devdrv trust D:
```

- [Set up a Dev Drive on Windows 11](https://learn.microsoft.com/en-us/windows/dev-drive/)

## WinGet

- [Installing the App Installer](https://learn.microsoft.com/en-us/windows/msix/app-installer/install-update-app-installer)

```sh
sudo winget upgrade --all
```

```sh
sudo winget import winget-packages.json
```

```sh
winget export winget-packages.json
```

Sort packages.json

```pwsh
& {
    $ErrorActionPreference = 'Stop'

    $path = (Resolve-Path -LiteralPath 'winget-packages.json').Path
    $json = Get-Content -LiteralPath $path -Raw | ConvertFrom-Json

    foreach ($source in $json.Sources) {
        $source.Packages = @(
            $source.Packages | Sort-Object -Property PackageIdentifier
        )
    }

    $json |
        ConvertTo-Json -Depth 100 |
        Set-Content -LiteralPath $path -Encoding utf8
}
```

## Store

```sh
wsreset -i
```

```sh
# Microsoft Store
winget install 9WZDNCRFJBMP
```

```sh
store updates
```

```sh
# Dolby Access
store install 9N0866FS04W8
# DTS Sound Unbound
store install 9PJ0NKL8MCSJ
# Dolby Vision Extensions
store install 9PLTG1LWPHLF
# Dolby Digital Plus decoder for PC OEMs
store install 9NVJQJBDKN97
# Dolby AC-4 decoder for PC OEMs
store install 9P7646QPH1Q0
# HEVC Video Extensions from Device Manufacturer
store install 9N4WGH0Z6VHQ
# HEVC Video Extensions
store install 9NMZLZ57R3T7
# JPEG XL Image Extension
store install 9MZPRTH5C0TB
# Windows HDR Calibration
store install 9N7F2SM5D1LR
# Xbox Accessories
store install 9NBLGGH30XJ3
```

- [Microsoft Store - Generation Project](https://store.rg-adguard.net/)

## Softwares not managed

- [Starward](https://github.com/Scighost/Starward/releases)
- [PKHeX](https://projectpokemon.org/home/files/file/1-pkhex/)
- [DaVinci Resolve](https://www.blackmagicdesign.com/products/davinciresolve)
- [像素蛋糕](https://www.pixcakeai.com/)
- [glslang](https://github.com/KhronosGroup/glslang/releases)
- [NVIDIA Nsight Graphics](https://developer.nvidia.com/nsight-graphics/get-started)

## Clipboard

Press **Windows + V** to open clipboard history.

- [Using the clipboard](https://support.microsoft.com/en-us/windows/apps/using-the-clipboard)

## Keyboard

Turn off **Keyboard shortcut for Sticky keys** under **Settings > Accessibility > Keyboard > Sticky keys**.

Turn off **Keyboard shortcut for Filter keys** under **Settings > Accessibility > Keyboard > Filter keys**.

## Mouse

Turn off **Enhance pointer precision** under **Settings > Bluetooth & devices > Mouse**.

## Windows Security

Turn off **Recent activity and scan results** under **Settings > Manage notifications > Virus & threat protection notifications**.

## OneDrive

- [Change the location of your OneDrive folder](https://support.microsoft.com/en-us/onedrive/change-the-location-of-your-onedrive-folder)

## PowerShell

```sh
code $PROFILE
```

## Python

```sh
uv python install --default
```

- [Installing and managing Python with uv](https://docs.astral.sh/uv/guides/install-python/)

## Global Package Executables

```env
%AppData%\npm
%USERPROFILE%\.bun/bin
%USERPROFILE%\.local\bin
```

- [npm folders](https://docs.npmjs.com/cli/v12/configuring-npm/folders/)
- [Bun global packages](https://bun.sh/docs/pm/cli/add#--global)
- [uv tools](https://docs.astral.sh/uv/concepts/tools/)

## Repair

```sh
DISM.exe /Online /Cleanup-image /Restorehealth
```

```sh
sfc /scannow
```

- [Use the System File Checker tool to repair missing or corrupted system files](https://support.microsoft.com/en-US/Windows/Experience/Backup-Recovery/use-the-system-file-checker-tool-to-repair-missing-or-corrupted-system-files)

## Noble Scarlet

- [原版雅黑、修正版雅黑、鸿蒙替换雅黑](https://bbs.pcbeta.com/forum.php?mod=viewthread&tid=1960120)
