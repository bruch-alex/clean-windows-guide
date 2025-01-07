
## Способ 1: Winget

Winget - консольная программа Windows, которая может использоваться как для установки, так и для удаления некоторых программ. Все команды ниже выполняюстя через PowerShell.

### Получить список установленных приложений

``` cmd
winget list
```
??? note "Пример вывода команды"

    ```
    Name                                    Id                                      Version             Available    Source
    -----------------------------------------------------------------------------------------------------------------------
    Mozilla Firefox (x64 ru)                Mozilla.Firefox                         133.0.3                          winget
    Mozilla Maintenance Service             ARP\Machine\X64\MozillaMaintenanceServ… 133.0.3
    Microsoft Clipchamp                     MSIX\Clipchamp.Clipchamp_3.1.11920.0_n… 3.1.11920.0
    Microsoft Teams                         Microsoft.Teams                         24295.605.3225.8804              winget
    ```

### Удалить приложение

Нужно **заменить** `app-id` ниже на нужный айдишник приложения или на часть названия приложения. Winget сможет найти натболее подходящее приложение.

``` cmd
winget remove app-id
```

??? note "Пример для Microsoft Clipchamp"

    ```
    winget remove Clipchamp
    ```

## Способ 2: Remove-AppxPackage

### Показать все установленные приложения списком

```
Get-AppxPackage | select Name, PackageFullName | Format-List
```

??? note "Пример вывода команды"

    ```
    Name                                           PackageFullName
    ----                                           ---------------
    Microsoft.AV1VideoExtension                    Microsoft.AV1VideoExtension_1.3.4.0_x64__8wekyb3d8bbwe
    Microsoft.VP9VideoExtensions                   Microsoft.VP9VideoExtensions_1.2.2.0_x64__8wekyb3d8bbwe
    Microsoft.WindowsCamera                        Microsoft.WindowsCamera_2024.2408.1.0_x64__8wekyb3d8bbwe
    Microsoft.ZuneMusic                            Microsoft.ZuneMusic_11.2410.8.0_x64__8wekyb3d8bbwe
    ```

### Удалить приложение

Нужно **заменить** `PackageFullName` ниже на нужное название пакета приложения.

``` cmd
winget remove PackageFullName
```

??? note "Пример для Microsoft ZuneMusic "

    ```
    Remove-AppxPackage Microsoft.ZuneMusic_11.2410.8.0_x64__8wekyb3d8bbwe
    ```

## Особенные программы

### Microsoft Edge
