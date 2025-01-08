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
## Windows maskinen 
- Installer Python, husk marker "Add Python to PATH"
  
- Aktivere 'Audit Process Creation': 
Enable Audit Process Creation, i secpol.msc under Security Settings > Advanced Audit Policy Configuration > System Audit Policies - Local Group Policy Object > Detailed Tracking.
 
- Aktivere 'Include Command Line in Process Creation Events': 
Enable Include Command Line in Process Creation Events, i gpedit.msc under Computer Configuration > Administrative Templates > System > Audit Process Creation.

Windows Wazuh XDR Agent installation:

Kør denne kommando i Powershell med administartor rettigheder.

Husk at skifte værdierne for følgende placeholders:

WAZUH_MANAGER='Wazuh_Server_IP'

WAZUH_AGENT_NAME='Agent_Name'

```sh
Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/windows/wazuh-agent-4.9.2-1.msi -OutFile $env:tmp\wazuh-agent; msiexec.exe /i $env:tmp\wazuh-agent /q WAZUH_MANAGER='Wazuh_Server_IP' WAZUH_AGENT_NAME='Agent_Name'
```

## Konfiguration
For at opsætte konfigurationen skal filerne fra mappen "Configuration_files" erstatte, de tilsvarende filer på Wazuh serveren:

Husk at tilføj eget Virus Total API i ossec.conf. 

Filernes tilhørende mapper:

> agent.conf > /var/ossec/etc/shared/default/
> 
> local_rules.xml > /var/ossec/etc/rules/
> 
> ossec.conf > /var/ossec/etc/

## Active Response
For at kunne eksekvere Active Response scripts til opsatte regler, skal indsættes på scriptsne ligge lokalt på Wazuh agente i følgende fil sti:

```sh
C:\Program Files (x86)\ossec-agent\active-response\bin\
```

Det er følgende filer der skal indsættes: (Filerne findes her i mappen "Active-Response")

> remove-threat.exe
> 
> disable-account.exe


## Attack Scripts

