## fix permissions in windows
Either create a `.ps1` file or run the bellow script in powershell directly by setting `$path` manually.
```powershell
# Source: https://stackoverflow.com/a/43317244
$path = $args[0]
# Reset to remove explict permissions
icacls.exe $path /reset
# Give current user explicit read-permission
icacls.exe $path /GRANT:R "$($env:USERNAME):(R)"
# Disable inheritance and remove inherited permissions
icacls.exe $path /inheritance:r
```

## copy a folder from host machine to remote using pem file
```
 scp -r -i pemfile.pem ./source ubuntu@<IP or domain>:/home/ubuntu/destination
```
