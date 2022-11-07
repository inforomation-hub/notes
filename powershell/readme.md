### Refresh evn path:
```
$env:Path = [System.Environment]::GetEnvironmentVariable("Path","Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path","User")
```

### Run as admin:
```
Start-Process powershell -Verb runAs
```
