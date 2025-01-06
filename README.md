<h1 align="center">IT-Sikkerhed Bachelor Projekt 2025</h1>
<h3 align="center">Open Source vs licens baseret XDR programmer for små virksomheder</h3>


## Wazuh Opsætning

Linux Wazuh Server installation: 
```sh
curl -sO https://packages.wazuh.com/4.9/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
```
Windows Wazuh XDR Agent installation:
```sh
Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/windows/wazuh-agent-4.9.2-1.msi -OutFile $env:tmp\wazuh-agent; msiexec.exe /i $env:tmp\wazuh-agent /q WAZUH_MANAGER='Wazuh_Server_IP' WAZUH_AGENT_NAME='Agent_Name'
```

## Costum Rules

## Active Response

## Attack Scripts
