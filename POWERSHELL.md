
$files = Get-Content -Path D:\PS-Tutorial\file-with-numbers.txt


$files | ForEach-Object {
   New-Item -Name $_ -Path "D:\PS-Tutorial\ForEach-ObjectEx" -ItemType "directory" | Out-Null 
}



$servers = Get-Content C:\Temp\Servers.txt

$servers | foreach-Object -parallel{
   Write-output "Working on $_"
}




ForEach -Parallel ($<item> in $<collection>)
{
    [<Activity1>]
    [<Activity2>]
    ...
}
-throttlelimit
