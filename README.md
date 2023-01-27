# Powershell-Cheetsheet

## Get-Content 
- Read the contents of a file and display them on the screen: `Get-Content -Path "C:\Powershell\test.txt" | Write-Output`
- Read the contents of a file and save the output to another file `Get-Content -Path "C:\example.txt" | Out-File -FilePath "C:\example_copy.txt"`
- Set a variable to the file `$websites = Get-Content test.txt`
- Read the contents of a file and filter the output`Get-Content -Path "C:\example.txt" | Where-Object {$_ -like "*error*"}`
- Read the contents of a file with a specific encoding  `Get-Content -Path "C:\example.txt" -Encoding UTF8`

## ForEach-object
```powershell
$hosts = Get-Content -Path C:\Powershell\hosts.txt
$hosts | ForEach-Object {
      $_    
}
```







