# Powershell-Cheetsheet

## Get-Content 
- Read the contents of a file and display them on the screen: `Get-Content -Path "C:\Powershell\test.txt" | Write-Output`
- Read the contents of a file and save the output to another file `Get-Content -Path "C:\example.txt" | Out-File -FilePath "C:\example_copy.txt"`
- Set a variable to the file `$websites = Get-Content test.txt`
- Read the contents of a file and filter the output`Get-Content -Path "C:\example.txt" | Where-Object {$_ -like "*error*"}`
- Read the contents of a file with a specific encoding  `Get-Content -Path "C:\example.txt" -Encoding UTF8`

## ForEach-object
- To show content of the file with foreach objects.

```powershell
$hosts = Get-Content -Path C:\Powershell\hosts.txt
$hosts | ForEach-Object {
      $_    
}
```
![2](https://user-images.githubusercontent.com/86381942/214986304-9c233583-5cfb-48af-b681-f24339ab2662.png)


- To ping each host in the list and check if it is online:

```powershell
$hosts = Get-Content -Path C:\Powershell\hosts.txt
$hosts | ForEach-Object {
      Test-Connection -ComputerName $_ -Count 1 -ErrorAction SilentlyContinue
}
```
![3](https://user-images.githubusercontent.com/86381942/214986336-3ff0a6f1-c942-4d69-bc81-154cdee337c8.png)






