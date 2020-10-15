How to install/uninstall DNS Feature, create DNS zones and add/remove records


```powershell
## Add role and management tools
Add-WindowsFeature DHCP -IncludeManagementTools

Add-DhcpServerInDC -DNSName contoso.adds -IPAddress 10.211.55.11

Add-DhcpServerV4Scope -name "Etendu_101-110" -StartRange 10.211.55.101 -Endrange 10.211.55.110 -SubnetMask 255.0.0.0 -State Active

Add-DhcpServerv4ExclusionRange -StartRange 10.211.55.101 -Endrage 10.211.55.110 -ScopeId 10.0.0.0

Set-DhcpServerV4OptionValue -ComputerName contoso.adds -ScopeID 10.211.55.11 -DNSServer 10.211.55.11 -Router 10.211.55.1

Add-DhcpServerv4Reservation -ScopeID 10.0.0.0 -IPaddress 10.211.55.101 -ClientID "00-15-5d-56-9e-04" -Description "Reservation for MEL-SVR2"
```