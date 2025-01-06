<h1 align="center">IT-Sikkerhed Bachelor Projekt 2025</h1>
<h3 align="center">Open Source vs licens baseret XDR programmer for små virksomheder</h3>


## Wazuh Opsætning
Wazuh server skal installeret på en maskine med linux baseret OS.

Wazuh server kræver for dette miljø minimum: 

CPU: 4 vCPU 

RAM: 8 GiB 

Storage (90 days): 50 GB 

Husk at updatere og upgradere din linux maskine inden installation.

Linux Wazuh Server installation: 
```sh
curl -sO https://packages.wazuh.com/4.9/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```
Windows Wazuh XDR Agent installation:

Kør denne kommando i Powershell med administartor rettigheder.

Husk at skifte værdierne for følgende placeholders:

WAZUH_MANAGER='Wazuh_Server_IP'

WAZUH_AGENT_NAME='Agent_Name'

```sh
Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/windows/wazuh-agent-4.9.2-1.msi -OutFile $env:tmp\wazuh-agent; msiexec.exe /i $env:tmp\wazuh-agent /q WAZUH_MANAGER='Wazuh_Server_IP' WAZUH_AGENT_NAME='Agent_Name'
```

## Costum Rules

## Active Response

## Attack Scripts
