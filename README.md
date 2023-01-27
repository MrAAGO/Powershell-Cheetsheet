# Powershell-Cheetsheet

## Get-Content 
- Read the contents of a file and display them on the screen: `Get-Content -Path "C:\Powershell\test.txt" | Write-Output`
- Read the contents of a file and save the output to another file `Get-Content -Path "C:\example.txt" | Out-File -FilePath "C:\example_copy.txt"`
- Set a variable to the file `$websites = Get-Content test.txt`
- Read the contents of a file and filter the output`Get-Content -Path "C:\example.txt" | Where-Object {$_ -like "*error*"}`
- Read the contents of a file with a specific encoding  `Get-Content -Path "C:\example.txt" -Encoding UTF8`

## ForEach-object
- To print each line of the test.txt file to the console:

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


- To convert the content of test.txt file to uppercase:

```powershell
$test = Get-Content -Path C:\Powershell\test.txt
$test | ForEach-Object {
      $_.ToUpper()
}
```
![4](https://user-images.githubusercontent.com/86381942/214986789-11d707c9-0d3e-44c7-80d6-01cf892894f6.png)

- To change the background color and foreground color of the text

```powershell
$test = Get-Content -Path C:\Powershell\test.txt
$test | ForEach-Object {
      Write-Host $_ -BackgroundColor Blue -ForegroundColor White
}
```
![5](https://user-images.githubusercontent.com/86381942/214987862-54d11985-01ea-4a13-97a2-75dfd4b2ef2e.png)

- To add the hostname to each line of the file test.txt

```powershell
$test = Get-Content -Path C:\Powershell\test.txt
$test | ForEach-Object {
      Write-Host "$env:COMPUTERNAME : $_" -BackgroundColor Blue -ForegroundColor White
}
```

![6](https://user-images.githubusercontent.com/86381942/214988666-f73a337d-84d6-484f-96b2-08f6307f81d5.png)

- To add the current date and time to each line of the test.txt file:

```powershell
$test = Get-Content -Path C:\Powershell\test.txt
$test | ForEach-Object {
      Write-Host (Get-Date) + " : $_" -BackgroundColor Blue -ForegroundColor White
}
```
![7](https://user-images.githubusercontent.com/86381942/214989827-41034f8e-b196-485e-b609-2f593edd8385.png)



