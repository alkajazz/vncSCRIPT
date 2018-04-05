# vncSCRIPT
powershell script for vnc settings


Remove-ItemProperty -Path "HKLM:\SOFTWARE\TightVNC\Server\" -Name "Password"
$regpath = "HKLM:\SOFTWARE\TightVNC\Server\"
$Name = "UseVncAuthentication"
$value = "0"
New-ItemProperty -Path $regpath -Name $Name -Value $value -PropertyType DWORD -Force | Out-Null
& 'C:\Program Files\TightVNC\tvnserver.exe' -controlservice -reload
