# PowerView.ps1

### https://raw.githubusercontent.com/ZeroDayLab/PowerSploit/master/Recon/PowerView.ps1

## Find operating systems in network
```powershell
Get-NetComputer -fulldata | select operatingsystem
```
### List users
```powershell
Get-NetUser | select cn
```