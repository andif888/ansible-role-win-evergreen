# ansible-role-win-evergreen

Role to install apps on windows using Evergreen powershell module (https://github.com/aaronparker/evergreen) to get Evergreen download url.

Checkout [test.yml](./tests/test.yml) for example usage.

## Table of content

- [Default Variables](#default-variables)
  - [win_evergreen_app_name](#win_evergreen_app_name)
  - [win_evergreen_download_dir](#win_evergreen_download_dir)
  - [win_evergreen_download_force](#win_evergreen_download_force)
  - [win_evergreen_get_app_command](#win_evergreen_get_app_command)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Default Variables

### win_evergreen_app_name

Name of the app

#### Default value

```YAML
win_evergreen_app_name: SomeApp
```

### win_evergreen_download_dir

Download directory

#### Default value

```YAML
win_evergreen_download_dir: C:\windows\temp\evergreen
```

### win_evergreen_download_force

Force download, also when file already exists

#### Default value

```YAML
win_evergreen_download_force: false
```

### win_evergreen_get_app_command

Powershell command to get app information

https://stealthpuppy.com/evergreen/use/

#### Default value

```YAML
win_evergreen_get_app_command: Get-EvergreenApp -Name "{{ win_evergreen_app_name }}"
  | Where-Object { $_.Architecture -eq "x64" -and $_.Ring -eq "General" -and $_.Type
  -eq "msi" }
```



## Dependencies

None.

## License

license (GPL-2.0-or-later, MIT, etc)

## Author

andif888
